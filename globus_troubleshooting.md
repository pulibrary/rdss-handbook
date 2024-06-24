# Globus Troubleshooting

## Restarting Globus

Find the box ip address by [logging into aws](https://www.princeton.edu/aws) and then locate the box inquestion under [running EC2 insatnces](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Instances:instanceState=running).

### Connecting to the box
  1. Open the VPN
  1. ssh pulsys@<ip address>

### Individual processes
  Individual processes can be restarted to reset the gridftp processes.
  ```
  sudo systemctl restart apache2
  sudo systemctl restart globus-gridftp-server
  ```
### Rebooting the box
  If the system is particlularly unstablle a system reboot might be needed
  ```
  sudo /sbin/reboot
  ```

## self-diagnostic
When troubleshooting Globus it's useful to SSH to the machine were Globus is running
([instructions](https://github.com/pulibrary/rdss-handbook/blob/main/globus.md#monitoring))
and run the `globus-connect-server self-diagnostic` command:

There are two key pieces of information on the output of the self-diagnostic.

The *first one* is about the `contact_info_uri()`. If the endpoint is up and running you should see an output similar to this:

```
== diagnostic: func:contact_info_uri() ==
xx.xx.xx.xx: {
  "DATA_TYPE": "info#1.0.0",
  "api_version": "1.24.0",
  "client_id": "...",
  "domain_name": "....data.globus.org",
  "endpoint_id": "...",
  "manager_version": "5.4.70"
}
```

but if the Globus endpoint is not available the output of the self-diagnostic will show something like this:

```
== diagnostic: func:contact_info_uri() ==
Error accessing GCS Manager at xx.xx.xx.xx: HTTPSConnectionPool(host='xx.xx.xx.xx', port=443): Read timed out. (read timeout=1)
```

The *second piece of information* that is useful on the self-diagnostic output is the one related to the `globus-gridftp-server`.
This section lists the GridFTP processes that are running and it looks more or less like this:

```
== diagnostic: systemctl status globus-gridftp-server --no-pager --lines 10 ==
● globus-gridftp-server.service - Globus Connect GridFTP Service
     Loaded: loaded (/lib/systemd/system/globus-gridftp-server.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-12-19 16:03:16 UTC; 1 day 2h ago
    Process: 474 ExecStart=/usr/sbin/globus-gridftp-server -S -c /etc/gridftp.conf -C /etc/gridftp.d -pidfile /run/globus-gridftp-server.pid (code=exited, status=0/SUCCESS)
   Main PID: 546 (globus-gridftp-)
      Tasks: 106 (limit: 9384)
     Memory: 202.0M
     CGroup: /system.slice/globus-gridftp-server.service
             ├─ 546 /usr/sbin/globus-gridftp-server -c /etc/gridftp.conf -C /etc/gridftp.d -pidfile ...
             ├─2878 /usr/sbin/globus-gridftp-server -c /etc/gridftp.conf -C /etc/gridftp.d -pidfile ...
             ... many more processes go here ...
             └─4749 /usr/sbin/globus-gridftp-server -c /etc/gridftp.conf -C /etc/gridftp.d -pidfile ...
```

We have seen that when our Globus endpoint goes down the number of tasks on this section is very large. The
example above shows `106` tasks, but we have seen the number go has high as `2000+` when we have problems.

From what we understand these are processes waiting for some sort of I/O operation to complete. You can view
the processes with `ps aux`, the output looks more or less like this:

```
gcsweb     11758  0.0  0.3 511144 26760 ?        Sl   Dec16   0:01 /usr/sbin/globus-gridftp-server -c /etc/gridftp.conf ...
```

The `Sl` status of these processes [means](https://askubuntu.com/a/360253/237654) that they are waiting for I/O.

```
S    interruptible sleep (waiting for an event to complete)
l    is multi-threaded (using CLONE_THREAD, like NPTL pthreads do)
```

We've been recommended to run `lsof -u gcsweb` to see if can see what files and collection these processes are writing
to as a way to figure out what user/collection might be causing the issue. The output of this command is not easy
to parse, but it might come in handy for troubleshooting in the future.

*Rebooting the box has fixed the issue in this case. But this is not a long term solution.*


## AWS EC2 network monitoring

It seems that when we have a large number of `globus-gridftp-server` processes waiting on I/O it is because we have
large spike in network traffic to the Globus machine. You can see these spikes in the AWS EC2 Dashboard.

* Login to AWS
* Select EC2 Services
* Click on "Instances running"
* Click on the instance ID of the machine that is having issues (e.g. `pdc-globus-prod-postcuration`)
* Click on Monitoring at the bottom of the screen
  * Click on Network in and Network out to see the network traffic to this machine

## Colecting data for globus support
Globus support has asked for the following data to be collected when contacting them.  Capture the output of the commands in a text file and attach them to the email along with the tar of the log files.

### Before rebooting or restarting the processes
```
curl -vk --resolve f0ad1.36fe.data.globus.org:443:127.0.0.1 https://f0ad1.36fe.data.globus.org/api/info
curl -vk --resolve f0ad1.36fe.data.globus.org:443:44.197.15.236 https://f0ad1.36fe.data.globus.org/api/info
sudo --user=www-data curl --unix-socket /run/gcs_manager.sock http://f0ad1.36fe.data.globus.org/api/info
ls -Zlah /run/gcs_manager.sock
systemctl -l --no-pager status gcs_manager.socket
systemctl -l --no-pager status gcs_manager.service
systemctl -l --no-pager status apache2.service
systemctl -l --no-pager status gcs_manager_assistant.service
systemctl -l --no-pager status globus-gridftp-server.service
sudo netstat -tpn | grep -i grid
sudo free -m
sudo dmesg -T
sar -A -f /var/log/sysstat/sa$(date '+%d')
sar -A -f /var/log/sysstat/sa$(date -d "yesterday" '+%d')
sar -A -f /var/log/sysstat/sa15
```

### After restarting the system
```
journalctl --no-pager --since="1 day ago" --unit gcs_manager.socket
journalctl --no-pager --since="1 day ago" --unit gcs_manager.service
journalctl --no-pager --since="1 day ago" --unit apache2.service
journalctl --no-pager --since="1 day ago" --unit gcs_manager_assistant.service
journalctl --no-pager --since="1 day ago" --unit globus-gridftp-server.service
```

### Gather up log files
```
sudo cp /var/log/apache2/error.log error.log.$(date '+%Y-%m-%d')
sudo cp /var/log/apache2/access.log access.log.$(date '+%Y-%m-%d')
sudo cp /var/log/apache2/other_vhosts_access.log other_vhosts_access.log.$(date '+%Y-%m-%d')
sudo cp /var/log/globus-connect-server/gcs-manager/gcs.log gcs.log.$(date '+%Y-%m-%d')
sudo cp /var/log/gridftp.log gridftp.log.$(date '+%Y-%m-%d')
sudo chown pulsys *.$(date '+%Y-%m-%d')
tar -cvf $(date '+%Y-%m-%d')-logs.tar *.log.$(date '+%Y-%m-%d')
```

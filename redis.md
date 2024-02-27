# Redis
We utilize redis locally running on some of our servers.  
The service that runs redis is `redis-server`
Log files can be found in `/var/log/redis/redis-server.log`

## Status
To get the status of the redis on any server run
```
sudo systemctl status redis-server
```

## restart
To restart of the redis on any server run
```
sudo systemctl restart redis-server
```

## Enable restart on reboot
To enable redis to be restarted on reboot, on any server run
```
sudo systemctl enable redis-server
```

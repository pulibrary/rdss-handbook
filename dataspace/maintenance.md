# Dataspace and OAR maintenance
Every Monday and Tuesday AM, the Operations team patches the Operating Systems for the [Dataspace](https://dataspace.princeton.edu) and [OAR](https://oar.princeton.edu). On some occasions the update process will require a reboot. The DSpace applications do not always launch on restart, or will launch but be in an unreliable state. The following steps will ameliorate the problem:

For Dataspace:

  ```bash
  ssh -J pulsys@bastion-prod.princeton.edu pulsys@10.244.0.2
  ```
For OAR:

  ```bash
   ssh -J pulsys@bastion-prod.princeton.edu pulsys@10.244.0.3
   ```

In both cases we will need to switch to the `dspace` user and bounce the application as the first troubleshooting step with the following:

  ```bash
  sudo su - dspace
  dsbounce
  ```
This will "bounce" the respective applications. Check the URI for both and make sure it is running. 

Occasionally (especially dataspace) will lose it's connection to the [Google Cloud SQL Dataspace](https://console.cloud.google.com/sql/instances/pul-prod-db/overview?project=pul-gcdc). It is important to note that this is a Google Service and not an actual VM. It is thus very unlikely that this is down (it is designed for high availability) the connections a significant number of times based on our Monit alerts.

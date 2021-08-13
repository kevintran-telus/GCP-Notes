# **Google Cloud Platform Shell Commands**

### Launching a Google Cloud Engine Instance
- Get the list of instances - `gcloud compute instances list` 
- Creates the SSH infastructure to login to VM `gcloud compute ssh istanceNameHere --zone zoneNameHere` 

- Update packages & refresh packages. It will also help speed up installing the Apache Web servers - `sudo apt-get update`

- Install Apache2 - `sudo apt-get install -y apache2`

- Start Apache service - `sudo systemctl start apache2`

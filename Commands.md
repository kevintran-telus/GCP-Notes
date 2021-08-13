# **Google Cloud Platform Shell Commands**

- Get the list of instances - `gcloud compute instances list` 
- Creates the SSH infastructure to login to VM `gcloud compute ssh istanceNameHere --zone zoneNameHere` 
- Update packages & refresh packages. It will also help speed up installing the Apache Web servers - `sudo apt-get update`
- Install Apache2 - `sudo apt-get install -y apache2`
- Start Apache service - `sudo systemctl start apache2`
- Connecting to DB - `gcloud sql connect nameOfDb` (TESTING ONLY)
- Docker version in shell - `docker version`
- Images locally - `docker images`
- Pulling images - `docker pull imageName`
- Create Dockerfile with VIM - `vim dockerfile`
- Build custom Docker image - copy the created command in Docker file, should be something like `docker build ....`




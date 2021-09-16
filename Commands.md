# **Google Cloud Platform Shell Commands**

## Common Commands
- Most used commands are `gcloud` and `gsutil`
- BigQuery `bq`
- Cloud Big Table `cbt`

## GCloud Commands
- List of instances help - `gcloud compute instances`
- Create instance - `gcloud compute instances create nameOfInstance --zone=nameOfZone --machine-type=nameOfMachineType --boot-disk-size=16GB` (CLI way)
- List of disks help - `glcoud compute disks`
- Get the list of instances - `gcloud compute instances list`
- Creates the SSH infastructure to login to VM `gcloud compute ssh istanceNameHere --zone zoneNameHere`

## Gsutil Commands
- List of gsutil commands - `gsutil help`
- List all buckets in current project - `gsutil ls`


## BigQuery Commands
- List of commands - `bq help`

## Cloud BigTable Commands
- List of commands `cbt help`
 
- Update packages & refresh packages. It will also help speed up installing the Apache Web servers - `sudo apt-get update`
- Install Apache2 - `sudo apt-get install -y apache2`
- Start Apache service - `sudo systemctl start apache2`
- Connecting to DB - `gcloud sql connect nameOfDb` (TESTING ONLY)

---
## Docker
- Docker version in shell - `docker version`
- Images locally - `docker images`
- Pulling images - `docker pull imageName`
- Create Dockerfile with VIM - `vim dockerfile`
- Build custom Docker image - copy the created command in Docker file, should be something like `docker build ....`




# **GCP-Notes**
> - These are the notes on Google Cloud Platform that I want to remember. 
> - This is based off the "Google Cloud Platform (GCP) Fundamentals for Beginners" course that is on Udemy.
---
## **Key Takeaways**
### **Essential Buidling Blocks**
- Compute
- Storage
- Network
- Identity Management
### Addtional Services 
- Databases
- Data & Analytics
- AI & ML
- DevOps
---
## **Big Picture**
![gcp](/images/big-picture.png)
- Everything is based off the foundations (bottom layer)

### Compute Services
  - Computer engine, App engine, Kubernetes Engine, Container regristry, Cloud functions

### Storage & Database Services
  - Cloud storage, Cloud Bigtable, Cloud Datastore, Cloud SQL, Cloud Spanner, Persistent Disk

### Network Services
  - Cloud Virtual Network, Cloud Load Balancing, Cloud CDN, Cloud Interconnect, Cloud DNS

### Security & Identity Services
  - Cloud IAM, Cloud Resource Manager, Cloud Security Scanner, Cloud Platfom Security

### AI & ML Services
  - Cloud ML, Vision API, Speech API, Natural Language API, Translation API, Jobs API


### DevOps Tools
  - Cloud SDK, Deploy Manager, Cloud Source Repos, Cloud Tools for Android Studio, Cloud Tools

## **GCP Resources**
- Resources are the fundamental compoents of GCP
- Resources belong to a project
- Projects may be organized into folders
- The project represents a billable unit
- When the resource is made, billing must be attached to the resource

## **Interacting with GCP resources**
- We can interact with the resources with:
  - Web Console, Cloud Shell/Cloud SDK, Mobile App, REST API
- For the average user, web console should be enough
- For administrator usage, there is a built in shell
- Mobile app is for convienece
- Can also create REST APIs in a language.

### **Accessing GCP Shell**
- Interactive shell environment for GCP that is available from web browser.
- Comes preloaded with IDE, gcloud SDK and other tools
- Built-in web preview functionality

## **Overview of Compute Services**
- **App Engine** - **PaaS, Managed Runtime** - Fully managed platform for deploying web apps at scale automatically
  - **Good for not having to configure/manage resources, just want to run application**
  - Supports multiple langs/frameworks/libraries
  - Available in two environments:
    - Standard: runs in a sandbox, has some restrictions
    - Flexible: uses Docker containers to deploy & scale apps. Flexible has more control over settings than Standard
---
- **Compute Engine** - **IaaS, Virutal Machines** - Enables Linux & Windows VM to run on global infrastructure
  - **Good for highly customizable workloads**
  - Based on machine types with CPU & RAM configurations
  - To bring in Persistence, we must bring in a SSD
  - VMs are charged a minimum of 1 minute, and 1 second increments after that
  - There are discounts offered for running VMs for long periods of time.
  - There are also commited discounts on 1 or 3 year contracts
---
- **Kubernetes** - **CaaS - Containerized & Microservices** - GKE is a manage environment for deploying containerized applications
  - **Good for containerized workloads**
  - VMs are slowly getting replaced by containerized environments
  - Kubernetes have control plane and worker nodes
    - Control plane manages data plane, which manages the multiple worker nodes
  - GKE provison worker nodes as GCE VMs
  - Node pools enable mixing and matching different VM configurations
  - The service is tightly intergrated with GCP resources such as networking, storage and monitoring
  - Auto scaling, auto uopdates, node auto-repair are some features of GKE
---
- **Cloud Functions** - **FaaS, Functions** -  Serverless engine that doesn't require a VM or containerization
  - **It is good for just executing code**
  - Serverless compute environments executes code in aresponse to an event
  - Supports JS, Py, Go
  - GCP events fire a Cloud Function through at trigger
  - Eg. event includes adding an object to a storage bucket
  - Trigger connects the event to the function

## **The choice of Compute on GCP**

- From the top: Highly Customizable, to the Bottom: Highly Managed:
  - Google Compute Engine 
  - Google Kubernetes Engine
  - Google App Engine
  - Google Cloud Functions 
---
## **GCP Storage Services**
- Storage services add persistence and durability to applications
- Classfied into three types: object storage, block storage, and file system
- GCP storage services can be used to store unstructured data, folders and files

## **Google Cloud Storage**
- Unified object storage for a variety of applications
- Applications can store and retrieve objects through single API
- Very scalable, and high durability(not prone to loss of data)
- Data can be stored within single, dual or multi region
### **Storage Classes**
- There are three different types of storage classes:
 - **High Frequency Access - Standard**
   - Most common storage class used by developers
   - Optimized for reduced latency
 - **Low Frequency Access - Nearline**
   - Meant for data accessed less frequency
   - Chosen for data accessed less than **once a month**
 - **Lowest Freqeuency Access - Coldline**
   - Meant for data accessed least frequency
   - Chosen for data accessed less than **once a year**
  
### **Persistent Disks**
 - PD provides reliable block storage for GCE VM's
 - Disks are independent of Compute Engine VM's
 - Each disk can be up to 64TB in size
 - PD can have 1 writer and multiple readers
 - Supports HDD and SSD
 - Offers three storage types: zonal, regional, local


### **Google Cloud Filestore**
- Managed file storage service for applications
- Centralized, available filesystem for GCE and GKE
- Has UNIX permissions
- Data is always encrypted in transit
- It allows legacy applications to continue to run while transitioning from on-prem to the cloud
- Buckets are used as the container that allows us to create folders that have the store objects

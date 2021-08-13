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
---
### **Google Cloud Network Services**
- GCP uses Google's global network for connectivity
-  Standard of premimium tiers
- Load balancers route traffic evenly to multiple endpoints
- Virtual private cloud offers private nad hybrid networking
- Customers can extend their data center to GCP through hybrid connectivity
- GCP defaults to premium tier, which uses Google's premium backbone
---
### **Idenety Access Manangement**
- For Identity - Google account, service account, google group, gsuite domain, cloud identity domain are available for IAM users
- Permissions are directly mapped to each REST API
- Primitive Roles: 
  - Owner
  - Editor
  - Viewer
- There are also predefined roles, and custom roles
- Key elements of Cloud IAM are: 
  - Resource - any GCP resource
  - Permissions - Determines operations allowed on resource
  - Roles - collection of permissions
  - Users - identity
---

## **Database Services**
- In memory DB used for accelerating performance on apps.
- Supports MySQL, Postgres, MSSQL
- **Cloud SQL** - Tradtional SQL db service
- **Cloud BigTable** is a NoSQL db service for large scale apps
- **Cloud Spannner** is a RDBMS for regional and global app data
  - Utilizes features from sql and no sql dbs
- **Cloud Memorystore** is a fully manage data store service for Redis. It can be used to accelerate retrivel of frequently accessed data
---
## **GCP Data Analytics Services**
- Data analytics include ingestion, colletion, processing, analyzing, and visualizing data
- **Cloud Pub/Sub**  
  - ingesting data by scale
  - based off publishing/subscription pattern
  - global entry point to GCP based analytic services
  - acts as a simple and reliable staging location for data
  - tightly intergrated with Cloud Storage and Cloud Dataflow
  - End-end encryption, IAM, and aduit logging
- **Cloud Dataflow** 
  - managed service for transforming and enhancing data in stream and batch modes
  - based off APache Bean open source project
  - Serverless approach automates provisoning and management
  - Incoming data can be queried, processed and extracted for target environment
  - Tightly intergarted with Pub/Sub, Bigquery, Cloud ML
  - 
- **Cloud Dataproc** 
  - Big Data service for running Hadoop and Spark jobs.
  - Automated cluster management
  - Clusters can be created and resized 3-100's of nodes
  - Move existing Big Data projects to GCP without redevelopment
  - Intergrates with Dataflow and BigQuery
- **BigQuery** 
  - Serverless, scalable data warehouse for the cloud
  - Built in business intelligence and ML services
  - Can pull data from Cloud Storage, Cloud BigTable, Spreadsheets
  - Has 7 day history of changes
- **Cloud Datalab** - used for analyzing and visualizing data
  - Runs on GCE and can connect to multiple cloud services
  - Enables data on Bigquery, Cloud ML engine, and cloud storage
  - Supports Python, SQL, and JS languages
---

## **AI and ML Serivces**
- **AI Building Blocks** - provide AI throgh REST calls
  - Some of the building blocks are sight, conversation, language, structued data
- **Cloud AutoML** - enables models on custom datasets
  - Custom ML models without any code
- **AI platform** -  provides end-end ML pipelines on-prem and cloud
- **AI Hub** is a hosted repo to discover, share and deploy ML models
---
## **GCP DevOps Services**
- Provides tools and frameowkrs for automation
- **Cloud Source Repositories** - stores and tracks source code
  - Acts as a scalable, private git repo
  - Extends standard Git workflow, to CloudBuild, Pub/Stub, and Compute services
  - Unlimited repos that can mirror Github & Bitbucket repos
  - Triggers to auto build, test, deploy code
  - Intergration of RegEx based code search
  - Singular source of code deployments across GCE,GAE,GKE,Cloud Functions
- **Cloud Build** - Managed service for source code build management
  - CI/CD tool running with GCP
  - Supports any programming language
  - Custom workflow to deploy across multiple target environments
  - Tight intergration with Cloud Source Repo, Git, Bitbucket
  - Supports native Docker intergration with auto deployment to Kubernetes and GKE
  - ID's vulnerabilities through efficient OS package scanning
- **Container Registry** -  acts as the centeral repo for storing, securing, and managing Docker container images
  - Stores GCE, GKE, and Kubernetes clusters
  - Secure, private, scalable Docker registry within GCP
  - Detects vulnerabilities in early stages of software deployment
  - Auto lockdown of vulnerable container images
  - Automated container build process based on code or tag changes
- **Developer Tools** - has built in tools for popular IDE's (VS code, IntelliJ, Eclipse)
 - Automates generation of config files and deploy scripts
 - Makes GCP libraries and SDK's available within the IDE's

### **Google Cloud API Management**
- Apigee API platform
- API Analytics
- Cloud endpoints


## **Anthos**
- Google's multi-cloud and hybrid playform based on Kubernetes
- Enables customers to run manage Kubernetes service (GKE) in a variety of environments
- Can be deployed in Gcloud, vSphere(onprem), AWS, Azure
- Non GKE Kubernetes clusters can be attached to Anthos
- Provides centeralized location for management of the clusters

### **Migration Tools**
- Transfier appliance, migrate for Compute Engine, BigQuery data transfer service

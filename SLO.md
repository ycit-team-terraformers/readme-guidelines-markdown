# SLO Analysis
The goal of this document is to provided overview of the SLO anaylis for the RealWorld blogging platform.

## Part 1: Evaluating the Underlaying Availibility
### 1.1)  Case:
RealWorld application shows how a real-world blogging platform is build, builders have the choice of using React/Angular/ using Node/Django as database adhered to the same API. A blog. One of the most simple inventions that never would have existed without the web itself. And it takes full advantage of the web too: querying & persisting data to a database, an authentication system, session management, full CRUD for resources:
Key CX notes:
- Application must be available at all time for reader: perma-connected
- Allow readers interations with bloggers information (liking, commenting, etc):  
- Querying & persisting data to a database, an authentication system, session management, full CRUD ( Create, read, upload and delete) for resources
- Bloggers must have the history of their blogs and able to correct past indformation
- Users (readers and bloggers) needs to be authenticated (with a valid e-mail account) and security must ensure only owners of blogs are allow for modifications 
- Information must be monitor to reject offensive, hateful and unlawful content
- Timeout monitoring is important to block users to upload big files and choose a different method of uploading contect (FTP,etc)

### 1.2) List of underlaying infrastructure:
- Cloud Provider: GCP
- Network: VPC, Subnet, Natting, DNS, network rules, Firewalls and Load Balancers
- Intergration: IDEs, APIs, GCP/GKE console
- Interaction: Push and pull data requests
- Cloud: Kubernetes, Docker, key vaults.
- Cloud services: Web/App services, Databse services and network
- Cloud storage: database, buckets, cloud infrastructure
- External Repos" Docker hubm Github, external e-mail

### 1.3) 


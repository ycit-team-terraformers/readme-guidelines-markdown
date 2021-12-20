# SLO Analysis
The goal of this document is to provided overview of the SLO anaylis for the RealWorld blogging platform.

## Part 1: Evaluating the Underlaying Availibility
### 1.1)  Case:
RealWorld application shows how a real-world blogging platform is build, builders have the choice of using React/Angular/ using Node/Django as database adhered to the same API. A blog. One of the most simple inventions that never would have existed without the web itself. And it takes full advantage of the web too: querying & persisting data to a database, an authentication system, session management, full CRUD for resources:
Key CX notes:
- Application must be available at all time for the readers: perma-connected
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
- Cloud services: Web/App services, secrets, Databse services and network
- Cloud storage: database, buckets, cloud infrastructure
- External Repos" Docker hubm Github, external e-mail

### 1.3) Research on the availibility numbers:
Key Items for our solution and GCP
- Coud Run SLA: at least 99.95% 
- Cloud DNS 100% of SLO
- App Engine: 99.95%
- Cloud Storage Standard >= 99.95%
- Cloud Archive >= 99.0%
- Compute Engne/LB: Multizone >=99.99%, Single >=99.5%, LB >=99.99%
- GKE: Regional Cluster 99.95%
- Secret Manager 99.95%


References
- Google slis/slas/slos 
https://cloud.google.com/blog/products/devops-sre/sre-fundamentals-slis-slas-and-slos
- Google SLAs  
https://cloud.google.com/terms/sla
- Example of  SLO document from google : 
https://sre.google/workbook/slo-document/

### 1.4) Estimation of Downtime:

![image](https://user-images.githubusercontent.com/72282458/146695435-ba395046-7253-4c92-9ad2-7e4e78304f58.png)

- On Avarge 99.95% is around 4h 22m 48s

## Part 2: Define SLI:
### 2.1) Who are the users for the application?
- Bloggers: users that will put content in the application (CURD users)
- Visitors: users that will visit the applications to review content without subscribing
- Subscribers: regular visitors or blogger that will upload or comment on the content 
- Admins: adminstrators of the appliation
- Developpers: Update the code, version control and bug-fixing 
- Services Accounts: to manage automation, API connections, etc.

### 2.2) Define the common tasks that the majority of your users will perform using your application:
Conduit app, basic user activities :
- Authentication (login)
- Display articles (pull request)
- Search articles (pull request)
- follow a user (pull request)
- like an article (pull/push request)
- post a comment (push request)
- publish an article (push request)
- Modify user settings and profile (pull/push request)

### 2.3) High-level architecture diagram of the app: underlying infrastructure; key components, the request flow, the data flow, and the critical dependencies.

![image](https://user-images.githubusercontent.com/72282458/146695819-e071e214-aa50-4cff-af33-ca3039477fa6.png)

### 2.4) The selected three different metrics that are critical to confirm the app is healthy. 
goal: Define SLIs for these metrics (these should be defined as a ratio of the number of good events divided by the total number of events). Note data was changed after lab 12 results

![image](https://user-images.githubusercontent.com/72282458/146696129-b1b4dd8c-7209-4ea8-8fb8-7f20abf675de.png)

#### Class Notes:
![image](https://user-images.githubusercontent.com/72282458/146696165-c45449f6-276b-4751-9690-69ae414607fa.png)

#### Mural link: 
https://app.mural.co/t/terraformers3352/m/terraformers3352/1634078797996/929a5d5727848df4bd7fc6d33225e0abbf556343?wid=0-1634255849217

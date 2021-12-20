## Terraformers - YCIT021 class

![Logo](https://ycit-team-terraformers.github.io/favicon.png)

[Terraformers' Landing page](https://ycit-team-terraformers.github.io/)

# Tools

## Required Software
Here is the minimum recommended software you'll need to interface with the products and scripts used by the team

## Workstation software
This should be installed on your Windows workstation for maximum compatibility with Linux tooling and scripts. 
If you can't install software on your workstation (corporate or otherwise controlled environment), one possible substitute is [Google Cloud Shell](https://cloud.google.com/shell), though you should be aware that you may run into limitations in the Cloud Shell environment.
- [Windows Subsystem for Linux (WSL) with Ubuntu Linux](https://ubuntu.com/wsl)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Microsoft Visual Studio Code](https://code.visualstudio.com/download)
- [Tutorial: Get started using Visual Studio Code with Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode)

## Linux software
This should be installed where you run Linux (inside your WSL Ubuntu VM).
- [Google Cloud SDK components](https://cloud.google.com/sdk/docs/install#linux)
- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli) _installed locally or running from a container_
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
- (optional - if you want to beautify and customize your shell prompt) [powerline-go](https://github.com/justjanne/powerline-go)

### Helpful scripts
See the **scripts** directory inside the **ycit-team-terraformers-dotfiles** repository for some helpful scripts.

- [backup_wsl.bash](https://github.com/ycit-team-terraformers/ycit-team-terraformers-dotfiles/blob/main/scripts/backup_wsl.bash): Can be used to configure a backup of your HOME inside the WSL virtual machine, to a location on your physical host PC (including OneDrive, which may serve as a quick disaster recovery method).


# Configuration

## Install WSL

There are two ways to have WSL installed on Windows, it depends on the Windows version. 

### Windows 10 version 2004 or higher

Prerequisites: 
You must be running Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11

**Install**
You can now install everything you need to run Windows Subsystem for Linux (WSL) by entering this command in PowerShell or Windows Command Prompt and then restarting your machine.

```
wsl --install
```

This command will enable the required optional components, download the latest Linux kernel, set WSL 2 as your default, and install a Linux distribution for you (Ubuntu by default, see below to change this).
*The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for files to de-compress and be stored on your machine. All future launches should take less than a second.*

### WSL manual installation steps for older Windows versions 

Open PowerShell as Administrator and run the following commands

1. Enable WSL feature

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

2. Enabled Virtual machine

```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

3. Restart the machine

4. Download WSL 

```
https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
```

5. Run the WSL installer

6. Set WSL as 2 by default

```
wsl --set-default-version 2
```

7. Check distro installed 

```
wsl --list --verbose
```

## Install Linux distribution Ubuntu 20.04 LTS 

Download Ubuntu
```
invoke-webrequest -outfile "$home\downloads\ubuntu_20_04.appx" -uri https://aka.ms/wslubuntu2004
```
Install downloaded package

```
add-appxpackage "$home\downloads\ubuntu_20_04.appx"
```

*The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for files to de-compress and be stored on your machine.*
*All future launches should take less than a second.*

## Run the Distribution and create the user.

Run the following command from PowerShell or Windows Terminal

```
ubuntu2004.exe
```

## Exit the linux distribution

Type exit

```
exit
```

# Minikube

To install Minikube, run the linux distribution and execute the following commands:

```
ubuntu2004.exe
```

## Download the latest version of Minikube

Once in the Linux terminal style, run the following command

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```

## Make the binary executable

```
chmod +x ./minikube
```

## Move the binary to your executable path

```
sudo mv ./minikube /usr/local/bin/
```
## Run Minikube

Open the Linux Distribution and type minikube 

```
minikube
```

## Value Stream Mapping
Improvements:
  1. Splitting infrastructure and application code into two repositories. This will simplify the workflow actions.
  2. Ensure defining the provided version to all Terraform files. This ensures we are running the same version as we were having issues with code running different versions ot Terraform.
  3. Approval process was taking too long. Assign two people per week for the approval process. We will also use better comments on the pull requests to make it easier for the approver to understand the changes.

# Conventions

- [Repository Naming Conventions](https://github.com/ycit-team-terraformers/readme-guidelines-markdown/blob/main/Repository_Naming_Conventions.md)
- [Repository Commits Conventions](https://github.com/ycit-team-terraformers/readme-guidelines-markdown/blob/main/Repository_Commits_Conventions.md)

# Resource Center

- [Docker Sample application](https://docs.docker.com/get-started/02_our_app/)

- [Best practices for writing Dockerfile](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

- [Configure GitHub actions](https://docs.docker.com/ci-cd/github-actions/)

- [Docker file library](https://github.com/jessfraz/dockerfiles)

# Team

- Antonio M
- Camilo M
- Christian B
- Devon P
- Diego P
- Mohammad B


# Projects

- Project 1 DevOps Infrastructure

# Project 11: SLO Analysis
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


## About GitHub Pages

You can use the [editor on GitHub](https://github.com/Vidinci/vidinci.github.io/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

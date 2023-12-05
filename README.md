# AzureDevOps-Zero-to-Hero with real-time projects

Welcome to our comprehensive course on Azure DevOps, where we'll dive deep into concepts, demos, and real-time projects to help you master Azure DevOps and bolster your DevOps skills.
**This playlist will be published on my YouTube channel and is free for anyone to use and follow.**

### Day 0: Introduction to the Course 👇
[![Course Introduction](https://img.youtube.com/vi/A_N5oHwwmTQ/sddefault.jpg)](https://youtu.be/A_N5oHwwmTQ)


### Day 1: Introduction to Azure DevOps and Basic Concepts 🌟
**Status**: Video is live, check out 👉 [Day1](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day1) 👈 folder for notes and useful links ✅

- What is Cloud Computing
- IaaS VS PaaS VS SaaS
- What is a Shared Responsibility Model
- What is a Traditional Build and Deployment workflow
- What is a Waterfall model in SDLC
- Problems with the traditional software development life cycle (SDLC)
- What is Agile, and how it solves the above challenges 
- What is DevOps and Why It Matters
- What is CI/CD
- What is Azure DevOps and a quick walkthrough
- Creating an Azure DevOps Organization
- Creating an Azure DevOps Project
- Azure DevOps Pricing
- Azure DevOps hosting options : Azure DevOps Services VS Azure DevOps Server

### Day 2: Azure Boards and Agile Project Management 📊
**Status**: Video is live, check out 👉 [Day2](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day2) 👈 folder for notes and useful links ✅

- What are Azure DevOps Boards 
- What are Azure board processes, agile, scrum, basic, and CMMI
- Managing work items in Azure boards
- Azure board implementation using basic process
- Working with teams, areas, and iterations
- Filters in backlogs and boards
- Azure board implementation using the scrum process
- Sprint planning and capacity planning
- Product backlog and taskboard
- Customizing Kanban boards
- Customizing dashboards
- Work item query
- Customizing team process

### Day 3: Mastering Git and Source Control in Azure DevOps 🌿
**Status**: Video is live, check out 👉 [Day3](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day3) 👈 folder for notes and useful links ✅

- Introduction to Source Control and Azure Repos
- Git vs TFVC
- Configure Visual Code
- Cloning the repo
- Commit changes
- Reviewing history
- Working with branches
- Tagging a release
- Managing repository
- Managing Pull requests
- Sample application code

### Day 4: Build Pipeline 🚀
**Status**: Video is live, check out 👉 [Day4](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day4) 👈 folder for notes and useful links ✅


#### Note: For the demo, we will be using the YouTube Clone website 

- Provision Azure App Service to host the website.
- Creating Build Pipelines using the classic editor
- Creating build pipeline using YAML
- YAML pipeline structure, the difference between jobs, stages, steps, and tasks
- Creating a multi-stage CICD pipeline
- variables, triggers, Build properties, agents
- Publishing and Download Build Artifacts


### Day5: 🚀 Continuous Delivery with Azure DevOps Release Pipeline
**Status**: Video is live, check out 👉 [Day5](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day5) 👈 folder for notes and useful links ✅

#### Note: this is a continuation of the previous video.

- Automating Deployment with a multi-stage Release Pipelines
- Continuous Deployment Triggers
- Continuous delivery using deployment slots to enable **Blue-Green deployment**
- Deployment gates such as Query Work Items and Approvals before the prod deployment
- Update the code to test the entire CICD process with the Build and Release pipeline


### Day 6: Azure Test Plans and Testing 🧪
**Status**: Video is live, check out 👉 [Day6](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day6) 👈 folder for notes and useful links ✅

#### Note: We will be using the Youtube Clone website to implement the below steps
- Azure Test Plan Overview
- Features of Azure test plan
- Managing Test Plans, Suites and Cases
- Subscribe to the test plan free trial
- Authoring, Running, and Analyzing Manual Tests
- Azure Test and Feedback extension

### Day 7: Basic Project Artifacts with Azure Artifacts 📦
**Status**: Video is live, check out 👉 [Day7](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day7) 👈 folder for notes and useful links ✅

#### Note: In this video, we will use a ✔ Nike Landing page as a sample application for CICD using Azure Artifacts

- Overview of Azure Artifacts
- Create the Azure DevOps project and check out the application code
- Set up the infra using Azure Web App
- Create Azure Artifacts feed to host the packages
- Create the CI pipeline that builds the package and pushes it to the feed
- Create the CD pipeline that consumes the package
- Promote the package to trigger the release pipeline
- Upstream packages in Azure Artifacts

### Day 8: Infrastructure as Code (IaC) with Terraform and Azure DevOps🚀

**Status**: Video is live, check out 👉 [Day8](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day8) 👈 folder for notes and useful links ✅

- Introduction to IaC and Tools
- Various Terraform commands and workflow
- Creating Terraform configuration files
- Setting up terraform backend with Azure storage
- Executing Terraform commands using CLI
- Azure DevOps CI Pipeline to init, plan, and archive the plan file
- Azure DevOps CD pipeline to apply the changes


### Day9: Self Hosted agents on Azure Virtual machine scale sets

- What is a Virtual machine scale set
- Microsoft-hosted vs. self-hosted agents
- Use case of self-hosted agents
- Ways to setup self-hosted agents: VM, VMSS, container
- Set up a self-hosted agent using VMSS
- Register the agent on an agent pool
- Install custom utilities on the agent
- Use the self-hosted agent on a pipeline
- Comparison between self-hosted and Microsoft-hosted agents
- work folder walkthrough on agent

### Day 10 Managing Containers with Azure DevOps

- What is a container
- Understanding Virtual machine V/s Containers.
- Containerize a sample To-Do list web app written in React JS.
- What are Azure container instances(ACI)
- Azure DevOps CICD Pipeline to deploy to ACI


### Day 11  Implementing end-to-end CICD using Azure DevOps on Kubernetes.

- Difference between Monolithic and Microservice architecture
- 12 Factor App
- Basic Introduction of Kubernetes
- Deploying Microservices
- Overview of GitOps
- Azure DevOps CICD Pipeline for a web app running on Kubernetes
- Sample application: GitOps Pipeline for deploying a sample application(TBD)

### Day 12  Security and Permissions in Azure DevOps 🔐

- Managing Access and Security Settings
- Implementing Basic Security Practices
- Protecting Sensitive Data in Pipelines
- Include static code analysis and vulnerability scanning
- Sample Application: DevSecOps Pipeline for an Online Banking Application - Bank of Anthos

### Day 13: Serverless app CICD 🐳

- Introduction to Azure functions
- Build and release pipeline for building and deploying the code to Azure Functions
- Sample Application: Serverless QR Code Generator

### Day 14: Azure DevOps wiki 

- Overview of wiki
- Introduction to MarkDown
- How we can use Azure DevOps wiki to collaborate on a project


### Day 15: Creating Architectural diagrams

- Importance of documentation
- How to create effective architectural diagrams using multiple tools
- How to create animated architectural diagrams for blogs/social media

### Day 16: Advanced CI/CD Pipelines and Deployment Strategies 🚢

- Building Multi-Stage CI/CD Pipelines
- Implementing Canary deployment using Azure DevOps
- Managing Pipeline Variables and Environments
- Sample application: To be decided



### Contributions are welcome:
You can just raise the pull request to contribute to the course material; please remember to star the repository.
 
## 🔗 Join our community 👇  


<a href="https://youtube.com/@techtutorialswithpiyush"><img src="https://www.freeiconspng.com/thumbs/youtube-icon/video-youtube-icon--14.png" height="60px"></img></a>
<a href="https://discord.com/invite/FMtJ2bVRUE"><img src="https://img.icons8.com/color/2x/discord--v2.png" height="60px"></img></a>
<a href="https://github.com/piyushsachdeva/"><img src="https://user-images.githubusercontent.com/91791257/235086411-9ec7aa5e-c095-44ce-b9e6-57b3bc3fead2.png" height="60px"></img></a>
<a href="https://twitter.com/thecloudopscomm"><img src="https://i.postimg.cc/pVqVTNJd/X-logo.png" height="60px"></img></a>
<a href="https://www.linkedin.com/company/thecloudopscomm/"><img src="https://img.icons8.com/fluency/2x/linkedin.png" height="60px"></img></a>
<a href="https://www.instagram.com/techtutorialswithpiyush/"><img src="https://user-images.githubusercontent.com/91791257/235086447-47658b7b-71fa-4baf-830a-3ba9b3a76a47.png" height="60px"></img></a>


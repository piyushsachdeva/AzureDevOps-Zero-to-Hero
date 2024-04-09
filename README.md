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
- What is Agile, and how it solve the above challenges 
- What is DevOps and Why It Matters
- What is CI/CD
- What is Azure DevOps and a quick walkthrough
- Creating an Azure DevOps Organization
- Creating an Azure DevOps Project
- Azure DevOps Pricing
- Azure DevOps hosting options: Azure DevOps Services VS Azure DevOps Server

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


### Day9: Self Hosted agents 👨‍🔧 on Azure Virtual machine scale sets 🧑‍💻

**Status**: Video is live, check out 👉 [Day9](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day9) 👈 folder for notes and useful links ✅

- Microsoft-hosted vs. self-hosted agents
- Use case of self-hosted agents
- Ways to setup self-hosted agents: VM, VMSS, container
- What is a Virtual machine scale set
- Set up a self-hosted agent using VMSS
- Register the agent on an agent pool
- Install custom utilities on the agent
- Use the self-hosted agent on a pipeline
- Comparison between self-hosted and Microsoft-hosted agents
- work folder walkthrough on agent

### Day 10 Managing Containers with Azure DevOps
**Status**: Video is live, check out 👉 [Day10](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day10) 👈 folder for notes and useful links ✅

- What is a container
- Understanding Virtual machine V/s Containers.
- Challenges with the non-containerized applications
- Docker Architecture
- Containerize a sample To-Do list web app written in React JS.
- Benefits of a multi-stage docker file
- What are Azure container instances(ACI)
- Azure DevOps CICD Pipeline to deploy to ACI


### Day 11  Implementing end-to-end CICD using Azure DevOps on Kubernetes.
**Status**: Video is live, check out 👉 [Day11](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day11) 👈 folder for notes and useful links ✅

- Basic Introduction of Kubernetes and its benefits
- Kubernetes Architecture
- What is the control plane and its components
- What are Nodes and types of Nodes
- What is a Pod/Deployment/Service
- Azure DevOps CICD Pipeline for a web app running on Kubernetes
- Sample application: My Health Care - Microservices-based Healthcare management app


  
### Day 12  Security and Permissions in Azure DevOps 🔐
**Status**: Video is live, check out 👉 [Day12](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day12) 👈 folder for notes and useful links ✅

- Enabling advanced security in Azure DevOps
- Dependency Scanning
- Secret scanning and managing alerts
- How to use secrets in your pipeline
- Code scanning for vulnerabilities
- Sample Application: My Health Care - Microservices-based Healthcare management app

### Day 13: Serverless app CICD 🐳
**Status**: Video is live, check out 👉 [Day13](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day13) 👈 folder for notes and useful links ✅

- Introduction to Azure functions
- Use case and benefits of an Azure function
- Introduction to the sample app to be used for this demo: Serverless QR Code Generator
- Demo creating the Azure function and deploying locally
- Publishing the function to Azure using CLI tools
- Build and release pipeline for building and deploying the code to Azure Functions

  
### Day 14: Azure DevOps wiki
**Status**: Video is live, check out 👉 [Day14](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day14) 👈 folder for notes and useful links ✅

- Overview of wiki
- Creating and editing a project Wiki
- Publishing code as Wiki
- How we can use Azure DevOps wiki to collaborate on a project


### Day 15: Azure DevOps Security best practices 🚢
**Status**: Video is live, check out 👉 [Day15](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day15) 👈 folder for notes and useful links ✅

- Azure DevOps Access Control
- Organization Settings
- Agent pools Management
- Pipeline settings
- Project-level Settings
- Pipeline security
- Repo settings
- Authentication and Authorization
- Secrets and credentials access


### Day 16: Issue and troubleshooting Azure DevOps
- In this video, we will discuss the most common issues you have faced throughout the series and solutions to those.
**Status**: Video is live, check out 👉 [Day16](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/Day16) 👈 folder for notes and useful links ✅
  
### Day 17: Bonus Video: Azure DevOps Scenario-based Interview Questions
- In this video, we will discuss the most asked scenario-based interview questions and answers for Azure DevOps
**Status**: Video is live, check out 👉 [InterviewQuestions](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/tree/main/InterviewQuestions) 👈 folder for notes and useful links ✅

### Contributions are welcome:
You can raise the pull request to contribute to the course material; please remember to star the repository.
 
## 🔗 Join our community 👇  


<a href="https://youtube.com/@techtutorialswithpiyush"><img src="https://www.freeiconspng.com/thumbs/youtube-icon/video-youtube-icon--14.png" height="60px"></img></a>
<a href="https://discord.com/invite/FMtJ2bVRUE"><img src="https://img.icons8.com/color/2x/discord--v2.png" height="60px"></img></a>
<a href="https://github.com/piyushsachdeva/"><img src="https://user-images.githubusercontent.com/91791257/235086411-9ec7aa5e-c095-44ce-b9e6-57b3bc3fead2.png" height="60px"></img></a>
<a href="https://twitter.com/thecloudopscomm"><img src="https://i.postimg.cc/pVqVTNJd/X-logo.png" height="60px"></img></a>
<a href="https://www.linkedin.com/company/thecloudopscomm/"><img src="https://img.icons8.com/fluency/2x/linkedin.png" height="60px"></img></a>
<a href="https://www.instagram.com/techtutorialswithpiyush/"><img src="https://user-images.githubusercontent.com/91791257/235086447-47658b7b-71fa-4baf-830a-3ba9b3a76a47.png" height="60px"></img></a>


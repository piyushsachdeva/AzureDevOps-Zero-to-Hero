# Day3 - Azure Repos

# Checkout the video below for Day3

[![Azure DevOps Repos](https://img.youtube.com/vi/vN6iY5y4h9Y/sddefault.jpg)](https://youtu.be/vN6iY5y4h9Y)

## What is Azure repos?

**Azure Repos is a set of version control tools that you can use to manage your code, just like GitHub**. Whether your software project is large or small, using version control as soon as possible is a good idea.

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/552cf47f-77cc-467f-82e4-6ef8b59c252a)


Version control systems are software that help you track changes you make in your code over time. As you edit your code, you tell the version control system to take a snapshot of your files. The version control system saves that snapshot permanently, so you can recall it later if you need it. Use version control to save your work and coordinate code changes across your team.

Even if you are working on a personal project, version control helps you stay organized as you fix bugs and develop new features. Version control keeps your development history so you can quickly review and even roll back to any code version.

- Helps you track changes in the codebase
- Maintains the history of your codebase, who made the changes, what changes were made, why the changes were made, etc
- Helps you stay organized
- Gives you the ability to rollback the changes as needed

## Azure DevOps Demo Generator
**Use these steps to load dummy data into your Azure DevOps project. We will use this data in the demo.**

1. Navigate to https://azuredevopsdemogenerator.azurewebsites.net. This utility site will automate the creation of a new Azure DevOps project within your account that is prepopulated with content (work items, repos, etc.) required for the lab. 

2. Sign in using the Microsoft account associated with your Azure DevOps subscription.

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/33feacfa-47bb-4861-b87d-d026e1eb36ee)

3. Accept the permission requests for accessing your subscription.

4. Select the PartsUnlimited template and click Select Template.

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/9bb9e1bd-cee1-4f18-ac5d-36163b36552e)

5. Click Create Project and wait for the process to complete.

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/b27fc6a5-0c6c-4cde-8ad9-8d11d935d7f5)


## Git vs. TFVC

Azure Repos supports two types of Version Control:
- Git
- TFVC ( Team Foundation Version Control)

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/25b0ec44-7542-4fb6-af47-9f3d59ebc9a3)


### Git
Git is the most popular distributed version control system, which allows developers to download the entire code repository locally with all the versions and make the changes remotely/offline. Changes can be synced to the remote server afterward.

To interact with Git, you can make use of Git clients such as Git for Windows, VSCode, etc
Git provides a version control system, but you need a hosting service to host your codebase(repositories). You can use git hosting services such as GitHub, Azure Repos, Bitbucket, Gitlab, etc.

### TFVC
Another type of version control system is TFVC, a centralized version control. In TFVC, only a single codebase version is downloaded locally, historical data is maintained on the central server. You can host TFVC on hosting services such as Perforce, SVC, Azure Repos, etc.


## Working with branches

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/b39d56b3-19e7-49f1-9c42-99c183f01bbf)


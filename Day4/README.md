
# 🚀 Azure DevOps Build Pipeline - Build and Deploy a YouTube Clone 

## Check out the video below for Day4 👇

[![Day4/16 - Azure DevOps Build Pipeline](https://img.youtube.com/vi/3Nv-FzzrqYU/sddefault.jpg)](https://youtu.be/3Nv-FzzrqYU)

## Steps to set the infrastructure
- Login to VSCode or any other IDE of your choice
- Run the below commands to download the application code
  ```
  mkdir day4_youtube_clone; cd day4_youtube_clone
  git init
  git clone https://github.com/piyushsachdeva/Youtube_Clone
  ```
- Create a project in Azure DevOps for Day4 and push the code by running the below commands on VSCode:
  ```
  git remote add origin $YOURAZUREREPO
  git push -u origin all
  ```
  Note: Make sure to update your Azure repo in the above command

- Go to the Azure Portal and Create the Azure App Service by following the instructions in the video

- Implement the build pipeline using the classic editor

- Understand the use of service connection and service principal

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/9c20aa32-3932-4d1c-b3a9-0abdcd93f5c7)


**Note: You must set the app settings WEBSITE_DYNAMIC_CACHE=0 and WEBSITE_LOCAL_CACHE_OPTION=Never to disable all file caching**


## Structure of Azure DevOps build Pipeline

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/d812d598-9f2e-4e64-80b7-893653f8eadd)


*  A trigger tells a Pipeline to run. It could be CI or Scheduled, manual(if not specified), or after another build finishes.
*  A pipeline is made up of one or more stages. A pipeline can deploy to one or more environments.
*  A stage organizes jobs in a pipeline, and each stage can have one or more jobs.
*  Each job runs on one agent, such as Ubuntu, Windows, macOS, etc. A job can also be agentless.
*  Each agent runs a job that contains one or more steps.
*  A step can be a task or script and is the smallest building block of a pipeline.
*  A task is a pre-packaged script that performs an action, such as invoking a REST API or publishing a build artifact.
*  An artifact is a collection of files or packages published by a run.

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/9930aa48-91e9-4370-8f85-406ad0e8df9c)


## Pipeline code used in the demo

``` YAML
trigger: 
- main

stages:
- stage: Build
  jobs:
  - job: Build
    pool:
      vmImage: 'ubuntu-latest'
    steps:
    - task: Npm@1
      inputs:
        command: 'install'
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'run build'

    
    - task: PublishBuildArtifacts@1
      inputs:
        PathtoPublish: 'build'
        ArtifactName: 'drop'
        publishLocation: 'Container'

- stage: Deploy 
  jobs:
  - job: Deploy
    pool:
      vmImage: 'ubuntu-latest'
    steps:
    - task: DownloadBuildArtifacts@1
      inputs:
        buildType: 'current'
        downloadType: 'single'
        artifactName: 'drop'
        downloadPath: '$(System.ArtifactsDirectory)'
    - task: AzureRmWebAppDeployment@4
      inputs:
        ConnectionType: 'AzureRM'
        azureSubscription: 'Tech Tutorials With Piyush (9e9c27ce-e0c8-4171-a368-ad16977ec849)'
        appType: 'webAppLinux'
        WebAppName: 'TechTutorialsWithPiyush'
        packageForLinux: '$(System.ArtifactsDirectory)/drop'
        RuntimeStack: 'STATICSITE|1.0'
```



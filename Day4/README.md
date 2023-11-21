
# Work in progress
# 🚀 Checkout the below video for Da4 - Azure DevOps Build pipeline 

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

**Note: You must set the app settings WEBSITE_DYNAMIC_CACHE=0 and WEBSITE_LOCAL_CACHE_OPTION=Never to disable all file caching**


## Structure of Azure DevOps build Pipeline

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



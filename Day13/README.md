# Day 13/16 - Azure Functions CI CD With Azure DevOps | What is Azure Function 🚀
## Check out the video below for Day12 👇

[![Day 13/16 - Azure Functions CI CD With Azure Devops | What is Azure Function](https://img.youtube.com/vi/3D-e-G-zPc4/sddefault.jpg)](https://youtu.be/3D-e-G-zPc4)

## To publish the Azure function from your CLI to Azure, follow the instructions given in the below repo:

```bash
https://github.com/rishabkumar7/azure-qr-code
```

## Azure DevOps CI/CD Process diagram:

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/f4eb0308-2f3b-4987-8ef3-62b5f8204bda)


## Azure DevOps pipeline code:

```YAML
# Node.js Function App to Linux on Azure
# Build a Node.js function app and deploy it to Azure as a Linux function app.
# Add steps that analyze code, save build artifacts, deploy, and more:
# https://docs.microsoft.com/azure/devops/pipelines/languages/javascript

trigger:
- iac-implementation

variables:

  # Azure Resource Manager connection created during pipeline creation
  azureSubscription: '<Your subscription ID>'

  # Function app name
  functionAppName: '<Function App Name>'

  # Environment name
  environmentName: '<Function App Name>'
  system.debug: true

  # Agent VM image name
  vmImageName: 'ubuntu-latest'

stages:
- stage: Build
  displayName: Build stage
  jobs:
  - job: Build
    displayName: Build
    pool:
      vmImage: $(vmImageName)

    steps:
    - task: NodeTool@0
      inputs:
        versionSpec: '18.x'
      displayName: 'Install Node.js'

    - script: |
        cd qrCodeGenerator
        npm install
        npm run build --if-present
        npm run test --if-present
      displayName: 'Prepare binaries'

    - task: CopyFiles@2
      inputs:
        SourceFolder: '$(System.DefaultWorkingDirectory)/qrCodeGenerator/GenerateQRCode/'
        Contents: '**'
        TargetFolder: '$(System.DefaultWorkingDirectory)/qrCodeGenerator/'
    - task: ArchiveFiles@2
      displayName: 'Archive files'
      inputs:
        rootFolderOrFile: '$(System.DefaultWorkingDirectory)/qrCodeGenerator/'
        includeRootFolder: false
        archiveType: zip
        archiveFile: $(Build.ArtifactStagingDirectory)/qrCodeGenerator/$(Build.BuildId).zip
        replaceExistingArchive: true

    - upload: $(Build.ArtifactStagingDirectory)/qrCodeGenerator/$(Build.BuildId).zip
      artifact: drop

- stage: Deploy
  displayName: Deploy stage
  dependsOn: Build
  condition: succeeded()
  jobs:
  - deployment: Deploy
    displayName: Deploy
    environment: $(environmentName)
    pool:
      vmImage: $(vmImageName)
    strategy:
      runOnce:
        deploy:
          steps:
          - task: AzureFunctionApp@2
            inputs:
              connectedServiceNameARM: '<Your service connection>'
              appType: 'functionApp'
              appName: '$(functionAppName)'
              package: '$(Pipeline.Workspace)/drop/$(Build.BuildID).zip'
              deploymentMethod: 'zipDeploy'

```

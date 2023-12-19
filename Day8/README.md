# Day 8/16 - Azure DevOps with Terraform 🏗

## Check out the video below for Day8 👇

[![Day8/16 - Azure DevOps with Terraform](https://img.youtube.com/vi/wq_sn9ey4KM/sddefault.jpg)](https://youtu.be/wq_sn9ey4KM)

## How Terraform works

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/943c9ea1-a6db-4ff7-9a2b-d91abe43acef)

## Initialize the Terraform repo

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/ed1c07c6-8ce0-40cb-bae2-49e981b163d0)

## Run Terraform plan

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/9f578a21-e132-43e8-817b-0d2724ee6b00)

## Run Terraform apply

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/6b27d254-eca3-4953-aa12-766cef1f9943)


### Import the below repository into Azure DevOps for Terraform configuration

https://github.com/piyushsachdeva/Terraform-AzureDevOps-Sample.git

## Let's implement this using Azure DevOps

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/a8395bd1-ee47-4b41-ba73-2f4bca714fd2)


### You can use the below Azure cli commands to set the terraform remote backend, or you can do it via the portal

``` shell
#!/bin/bash
## The Storage account name must be unique, and the values below should match your backend.tf
RESOURCE_GROUP_NAME=demo-resources
STORAGE_ACCOUNT_NAME=techtutorialswithpiyush
CONTAINER_NAME=prod-tfstate

# Create resource group
az group create --name $RESOURCE_GROUP_NAME --location canadacentral

# Create storage account
az storage account create --resource-group $RESOURCE_GROUP_NAME --name $STORAGE_ACCOUNT_NAME --sku Standard_LRS --encryption-services blob

# Create blob container
az storage container create --name $CONTAINER_NAME --account-name $STORAGE_ACCOUNT_NAME
```

## Azure DevOps CICD Pipeline

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/6f3ae577-750a-4eab-81ec-7c3b8630f6e9)


## YAML Code for Build pipeline

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
    - task: TerraformTaskV4@4
      displayName: Tf init
      inputs:
        provider: 'azurerm'
        command: 'init'
        backendServiceArm: '${SERVICECONNECTION}'
        backendAzureRmResourceGroupName: 'demo-resources'
        backendAzureRmStorageAccountName: 'techtutorialswithpiyush'
        backendAzureRmContainerName: 'prod-tfstate'
        backendAzureRmKey: 'prod.terraform.tfstate'
    - task: TerraformTaskV4@4
      displayName: Tf validate
      inputs:
        provider: 'azurerm'
        command: 'validate'
    - task: TerraformTaskV4@4
      displayName: Tf fmt
      inputs:
        provider: 'azurerm'
        command: 'custom'
        customCommand: 'fmt'
        outputTo: 'console'
        environmentServiceNameAzureRM: '${SERVICECONNECTION}'
      
    - task: TerraformTaskV4@4
      displayName: Tf plan
      inputs:
        provider: 'azurerm'
        command: 'plan'
        commandOptions: '-out $(Build.SourcesDirectory)/tfplanfile'
        environmentServiceNameAzureRM: '${SERVICECONNECTION}'
      
    - task: ArchiveFiles@2
      displayName: Archive files
      inputs:
        rootFolderOrFile: '$(Build.SourcesDirectory)/'
        includeRootFolder: false
        archiveType: 'zip'
        archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip'
        replaceExistingArchive: true
    - task: PublishBuildArtifacts@1
      inputs:
        PathtoPublish: '$(Build.ArtifactStagingDirectory)'
        ArtifactName: '$(Build.BuildId)-build'
        publishLocation: 'Container'
```

## Release pipeline

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/a492d66d-ed3e-468c-b68e-7d06891a8e92)


![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/7a0c53ea-0b7c-4098-b264-c66bb778fddf)

### Deployment stage

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/66fe7d5d-b665-496a-b43b-e85a88f7271d)

### Destroy stage

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/5d17e417-8a7d-49a6-8c9d-b120e236fde8)





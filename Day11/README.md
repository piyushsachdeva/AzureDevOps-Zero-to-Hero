# Day 11/16 - Azure DevOps CICD Pipeline on Azure Kubernetes Services 🛳️ 🐳

## Check out the video below for Day11 👇

[![Day10/16 - Azure DevOps CICD Pipeline on Azure Container Instances](https://img.youtube.com/vi/mv8qJzyZggE/sddefault.jpg)](https://youtu.be/mv8qJzyZggE)


## Kubernetes Architecture

<img width="820" alt="image" src="https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/e15fe0dc-afc0-4aec-b69f-b7e296df0b07">

## Kubernetes components

### Kube APiServer

<img width="746" alt="image" src="https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/808131a2-e8b5-4b89-af47-5f1040c64544">

### Kube Scheduler

<img width="745" alt="image" src="https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/7e394ee3-37c9-4ade-82b0-95da0b0318ef">

### Kube Controller Manager

<img width="853" alt="image" src="https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/4dffd765-559c-4839-8152-7f15ab753adf">

### ETCD

<img width="817" alt="image" src="https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/f50887ea-28d0-40b3-968d-1e923f2177a4">


## Pre-requisites

### Infrastructure provisioning

**Using the below script, you can provision infra for this demo**

The following resources will be provisioned:

* A Resource Group
* An AKS Kubernetes Cluster
* An Image container registry
* A SQL Server
* A SQL Database

``` bash

#!/bin/bash
REGION="westus"
RGP="day11-demo-rg"
CLUSTER_NAME="day11-demo-cluster"
ACR_NAME="day11demoacr"
SQLSERVER="day11-demo-sqlserver"
DB="mhcdb"


 #Create Resource group
 az group create --name $RGP --location $REGION

#Deploy AKS
az aks create --resource-group $RGP --name $CLUSTER_NAME --enable-addons monitoring --generate-ssh-keys --location $REGION

#Deploy ACR
az acr create --resource-group $RGP --name $ACR_NAME --sku Standard --location $REGION

#Authenticate with ACR to AKS
az aks update -n $CLUSTER_NAME -g $RGP --attach-acr $ACR_NAME

#Create SQL Server and DB
az sql server create -l $REGION -g $RGP -n $SQLSERVER -u sqladmin -p P2ssw0rd1234

az sql db create -g $RGP -s $SQLSERVER -n $DB --service-objective S0

```

## Change the Firewall settings of the SQL server

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/d421dd8b-1a85-447a-ad2d-f0ddb859953d)


## Setup Azure DevOps Project

### Pre-requisites

Make sure the below Azure DevOps extensions are installed and enabled in your organization
- Replace Token
- Kubernetes extension

Once the infra is ready, go to dev.azure.com --> Project --> repos 
and import the below git repo, which has the source code and pipeline code

https://github.com/piyushsachdeva/MyHealthClinic-AKS

### Build and Release Pipeline

- You can create your pipeline by following along the video or editing the existing pipeline. The below details need to be updated in the pipeline:
   - Azure Service connection
   - Token pattern
   - Pipeline variables
   - The Kubectl version should be the latest in the release pipeline
   - Secrets should be updated in the deployment step
   - ACR details in the pipeline should be updated
 
#### Steps in the pipeline

<img width="805" alt="image" src="https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/64907bef-acbf-41f1-b3de-63b46681db3d">

 [Image source](https://azuredevopslabs.com/labs/vstsextend/kubernetes/)

## Destroy the resources at the end of the demo

```
#!/bin/bash


# Set environment variables
REGION="westus"
RGP="day11-demo-rg"
CLUSTER_NAME="day11-demo-cluster"
ACR_NAME="day11demoacr"
SQLSERVER="day11-demo-sqlserver"
DB="mhcdb"

# Function to handle errors
handle_error() {
    echo "Error: $1"
    exit 1
}

# Function to check if the resource exists
resource_exists() {
    az resource show --ids $1 &> /dev/null
}

# Delete Azure Kubernetes Service (AKS)
if resource_exists $(az aks show --resource-group $RGP --name $CLUSTER_NAME --query id --output tsv); then
    az aks delete --resource-group $RGP --name $CLUSTER_NAME || handle_error "Failed to delete AKS."
else
    echo "AKS not found. Skipping deletion."
fi

# Delete Azure Container Registry (ACR)
if resource_exists $(az acr show --name $ACR_NAME --resource-group $RGP --query id --output tsv); then
    az acr delete --name $ACR_NAME --resource-group $RGP || handle_error "Failed to delete ACR."
else
    echo "ACR not found. Skipping deletion."
fi

# Delete SQL Database
if resource_exists $(az sql db show --resource-group $RGP --server $SQLSERVER --name $DB --query id --output tsv); then
    az sql db delete --resource-group $RGP --server $SQLSERVER --name $DB || handle_error "Failed to delete SQL Database."
else
    echo "SQL Database not found. Skipping deletion."
fi

# Delete SQL Server
if resource_exists $(az sql server show --resource-group $RGP --name $SQLSERVER --query id --output tsv); then
    az sql server delete --resource-group $RGP --name $SQLSERVER || handle_error "Failed to delete SQL Server."
else
    echo "SQL Server not found. Skipping deletion."
fi

# Delete Resource Group
if resource_exists $(az group show --name $RGP --query id --output tsv); then
    az group delete --name $RGP || handle_error "Failed to delete Resource Group."
else
    echo "Resource Group not found. Skipping deletion."
fi

echo "Resources successfully deleted."

```


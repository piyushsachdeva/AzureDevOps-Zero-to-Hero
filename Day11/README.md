# Work IN Progress

## Lab Instructions:

### Pre-requisites

``` bash

#!/bin/bash
REGION="us-east-1"
RGP="day11-demo-rg"
CLUSTER_NAME="day11-demo"
ACR_NAME="day11-demo-acr"
SQLSERVER="day11-demo-sqlserver"


 version=$(az aks get-versions -l $REGION --query 'orchestrators[-1].orchestratorVersion' -o tsv)
 #Create Resource group
 az group create --name $CLUSTER_NAME --location $REGION

#Deploy AKS
az aks create --resource-group $RGP --name $CLUSTER_NAME --enable-addons monitoring --kubernetes-version $version --generate-ssh-keys --location $REGION

#Deploy ACR
az acr create --resource-group $RGP --name $CLUSTER_NAME --sku Standard --location $REGION

#Authenticate with ACR to AKS
az aks update -n $CLUSTER_NAME -g $RGP --attach-acr $ACR_NAME

#Create SQL Server and DB

az sql server create -l $REGION -g $RGP -n $SQLSERVER -u sqladmin -p P2ssw0rd1234

 az sql db create -g $RGP -s $SQLSERVER -n mhcdb --service-objective S0

```

## Change the Firewall settings

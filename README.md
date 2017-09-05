# Customers

## Pre-requisites  
* [Azure Cli](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)  
* [Azure Subscription](https://account.windowsazure.com/Subscriptions )  

## Setting Up Environment
* Create Resource Group or use an existing one
* Create Redis   
* Create SQL  
    * Download a backup or sql script to generate the database [here](https://northwinddatabase.codeplex.com/releases/view/71634)
* Create Function App  
* Configure Deployment  
Under platform features, setup a new deployment pointing to this repository `https://github.com/AzureSuperpowers/Customers`  
* Configure Connection Strings
    * Add `SqlConnection` pointing to SQL Database  
    * Add `MyRedis` pointing to Redis Cache 



> Most of the steps below can be done via the [Azure Portal](https://portal.azure.com)  
* Create Resource Group  
`az group create -n functionsRG -l eastus`   
* Create Storage Account  
The storage account name must be unique.   
`az storage account create -n mystorageaccount199 -g functionsRG --sku Standard_GRS`  
* Create AppService Consumption Plan  
`az appservice plan create -n MyServicePlan -g functionsRG --sku F1`  
* Create Function App
`az functionapp create -n MyFunctionApp -g functionsRG -s mystorageaccount199 -u https://github.com/AzureSuperpowers/Customers.git -p MyServicePlan`
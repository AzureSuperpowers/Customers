# Customers

## Pre-requisites  
* [Azure Cli](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)  
* [Azure Subscription](https://account.windowsazure.com/Subscriptions )  

## Setting Up Environment  
> All the steps below are done via the [Azure Portal](https://portal.azure.com)  
* Create Resource Group or use an existing one
* Create Redis   
* Create SQL  
    * Download a backup or sql script to generate the database [here](https://northwinddatabase.codeplex.com/releases/view/71634)  
* Create Service Bus
* Create Function App  
* Configure Deployment  
Under platform features, setup a new deployment pointing to this repository `https://github.com/AzureSuperpowers/Customers`  
* Configure Application Settings
    * Add `SqlConnection` connection string pointing to SQL Database  
    * Add `MyRedis` connection string pointing to Redis Cache  
    * Add `SB` pointing to Service Bus

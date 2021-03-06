# Azure Storage Copy
Copies all files in a container to another Storage Account container.

1. Stands up ACI
2. Runs AZCopy
3. Transfers Blobs
    - Utilizes bandwidth in the data center
    - Ensure the best possible transfer rate.

# Tools
[Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

# Commands
## 1. Create/Choose Resource Group
Choose the region nearest to the data; this is where ACI will be brought up.

``
az group create -g <resourceGroupName> --location "West US 2"
``

Deployment file
- Stands up ACI (in the region of the Resource Group)
- Intiates copy of data

## 2. Deploy
``
az group deployment create --name sync --resource-group <resourceGroupName> --template-file transfer.json --parameters source=SOURCE soruceKey=KEY destination=DESTINATION destinationKey=KEY
``

OR (Edit parameter.json)

``
az group deployment create --name sync --resource-group <resourceGroupName> --template-file transfer.json --parameters parameters.json
``
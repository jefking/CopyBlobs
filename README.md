# Azure Storage Copy
Copies all files in a container to another Storage Account container.
Stands up ACI, which pulls an AZCopy image; which then transfers the data.
Utilizes bandwidth in the data center, to ensure the best possible transfer rate.

# Commands
Choose the region nearest to the data; this is where ACI will be brought up.

``
az group create -g <resourceGroupName> --location "West US 2"
``

Deployment file
- Stands up ACI (in the region of the Resource Group)
- Intiates copy of data

``
az group deployment create --name sync --resource-group <resourceGroupName> --template-file transfer.json --parameters source=SOURCE soruceKey=KEY destination=DESTINATION destinationKey=KEY
``
OR
- Edit parameter.json

``
az group deployment create --name sync --resource-group <resourceGroupName> --template-file transfer.json --parameters parameters.json
``
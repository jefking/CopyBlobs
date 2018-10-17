# Copy Blobs
Copies all files in a container to another Storage Account.
Uses ACI on Azure; and an AZCopy container.

# Commands
Choose the region nearest to the data; this is where ACI will be brought up.
``
az group create -g <resourceGroupName> --location "West US 2"
``

``
az group deployment create --name sync --resource-group <resourceGroupName> --template-file deploy.json --parameters parameters.json
``
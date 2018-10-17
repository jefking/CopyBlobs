# Copy Blobs
Copies all files in a container to another Storage Account.

# Commands
``
az group create -g <resourceGroupName> --location "West US 2"
``

``
az group deployment create --name sync --resource-group <resourceGroupName> --template-file deploy.json --parameters 2.parameters.json
``
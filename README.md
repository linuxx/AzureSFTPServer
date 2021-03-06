# Create an on-demand SFTP Server with persistent storage using an existing storage account

This code was copied from https://github.com/Azure/azure-quickstart-templates/tree/master/201-aci-sftp-files-existing-storage

I didn't want to fork the whole repo, just wanted this one to make some changes.

[![Deploy To Azure](https://raw.githubusercontent.com/linuxx/AzureSFTPServer/master/images/deploytoazure.svg)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Flinuxx%2FAzureSFTPServer%2Fmaster%2Fazuredeploy.json)



This template demonstrates an on-demand SFTP server using an Azure Container Instance (ACI). This version requires an existing Storage Account and File Share to exist in the same region as the ACI to be created. This File Share is then mounted into the main ACI to provide persistent storage after the container is terminated.

`Tags: Azure Container Instance, az-cli, sftp`

## Deployment steps

Click the "Deploy to Azure" button at the beginning of this document or follow the instructions for command line deployment using the scripts in the root of this repository. Ensure that a Storage Account and a file share have previously been created, as these are required parameters.

## Usage

Once deployed, connect to the public IP of the SFTP ACI and upload files; these files should be placed into the File Share. Once transfers are complete, stop the ACI and the files will remain accessible. You can delete/recreate the ACI and mount the same file share to copy more files.

## Notes

Azure Container Instance is available in selected [locations](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-quotas#region-availability). Please use one of the available location for Azure Container Instance resource.
The container image used by this template is hosted on [Docker Hub](https://hub.docker.com/r/atmoz/sftp). It is not affiliated with Microsoft in any way, and usage is at your own risk.



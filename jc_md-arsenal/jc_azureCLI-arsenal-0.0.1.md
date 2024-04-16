# az
% cloud
#plateform/Azure #target/remote #cat/UTILS

<!-- Basics command -->
//test
## Create ressource group

az group create --name <MyResourceGroupName> --location <Location>

## Show VM

az vm show --name <vmName> --resource-group <resourceGroup> --query 'networkProfile.networkInterfaces[].id' --output tsv

## Create Vnet

az network vnet create --name <vnetName> --resource-group <resourceGroup> --address-prefixes <vnetAddressPrefix> --subnet-name <subnetName> --subnet-prefixes <subnetAddressPrefix>

## Create VM

az vm create --resource-group <resourceGroup> --name <vmName> --image <OSName> --vnet-name <vnetName> --subnet <subnetName> --generate-ssh-keys --output json --verbose

## 


# az
% cloud
#plateform/Azure #target/remote #cat/UTILS
az group create --name <MyResourceGroupName> --location <Location>


## Création de VM

az vm create \
  --resource-group $resourceGroup \
  --name $vmName \
  --image Ubuntu2204 \
  --vnet-name $vnetName \
  --subnet $subnetName \
  --generate-ssh-keys \
  --output json \
  --verbose 

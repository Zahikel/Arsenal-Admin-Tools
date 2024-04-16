# az
% cloud
#plateform/Azure #target/remote #cat/UTILS

<!-- Basics command - Create -->
<!-- alias : -g= --resourcegroup/ -n= --name/ -e= --registration-enabled/ -v= --virtual-network/ -z= --zone-name -->

## Create ressource group

az group create --name <MyResourceGroupName> --location <Location>

## Show VM

az vm show --name <vmName> --resource-group <resourceGroup> --query 'networkProfile.networkInterfaces[].id' --output tsv

## Create Vnet

az network vnet create --name <vnetName> --resource-group <resourceGroup> --address-prefixes <vnetAddressPrefix> --subnet-name <subnetName> --subnet-prefixes <subnetAddressPrefix>

## Create VM

az vm create --resource-group <resourceGroup> --name <vmName> --image <OSName> --vnet-name <vnetName> --subnet <subnetName> --generate-ssh-keys --output json --verbose

## Create ASG (Application Security Group)
<!-- alias : -g= --resourcegroup/ -n= --name -->
az network asg create -g <MyResourceGroup> -n <MyAsg> --tags <MyWebApp>

## Create NSG (Network Security Group)
<!-- alias : -g= --resourcegroup/ -n= --name -->
az network nsg create -g <MyResourceGroup> -n <MyNsg>

## Create NSG rule 
<!-- alias : -g= --resourcegroup/ -n= --name -->
az network nsg rule create -g <MyResourceGroup> --nsg-name <MyNsg> -n <MyNsgRuleWithAsg> --priority <PriorityNumber> --source-address-prefixes <AddressPrefixes> --destination-port-ranges <PortRanges> --destination-asgs <DestinationASGName> --access <Allow-or-Deny> --protocol <Protocol-ex_TCP> --description <EnterYourDescriptionWithDoubleQuote>

## Create Private-DNS
<!-- alias : -g= --resourcegroup/ -n= --name -->
az network private-dns zone create -g <MyResourceGroup> -n <MyDomain>

## Create Private-DNS link to Vnet
<!-- alias : -g= --resourcegroup/ -n= --name/ -e= --registration-enabled/ -v= --virtual-network/ -z= --zone-name -->
<!-- Link DNS zone to a Vnet -->
az network private-dns link vnet create -g <MyResourceGroup> -n <MyLinkName> -z <MyDomain> -v <MyVirtualNetworkId> -e <True-or-False>

## Create A record on Private-DNS
<!-- alias : -g= --resourcegroup/ -n= --name/ -e= --registration-enabled/ -v= --virtual-network/ -z= --zone-name -->
az network private-dns record-set a add-record -g <MyResourceGroup> -z <MyDomain> -n <MyRecordSet> -a <MyIpv4Address>

## Update A record on Private-DNS

az network private-dns record-set a update -g <MyResourceGroup> -n <MyRecordSet> -z <MyDomain>

## 

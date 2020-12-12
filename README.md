# AzurePowershell

Create 2 VMS 1Vnet 1 subnet:

# create new resource group
az group create -l westeurope -n excercise1


# Create a vnet configuration
az network vnet create --address-prefixes 10.0.0.0/16 --name MyVirtualNetwork --resource-group excercise1 --subnet-name MySubnet --subnet-prefixes 10.0.0.0/24

# Create VM1
az vm create -n MyVm1 -g excercise1 --image UbuntuLTS --subnet MySubnet --vnet-name MyVirtualNetwork --generate-ssh-keys

# Create VM2
az vm create -n MyVm2 -g excercise1 --image UbuntuLTS --subnet MySubnet --vnet-name MyVirtualNetwork --generate-ssh-keys

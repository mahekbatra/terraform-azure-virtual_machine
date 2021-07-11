# terraform-azure-virtual_machine

# Example

# module "virtual_machine" {
# source  = "mahekbatra/virtual_machine/azure"
# version = "1.2.0"
# resource_group ="taskrg"
# location="eastus"
# subscriptionId"="xxxxxxxxxxxxxx"
# prefix="lwterra"
# publisher="Canonical"}
# sku="16.04-LTS"
# offer="UbuntuServer"
# version="latest"
# computer_name="myVM"
# admin_username="mahekbatra"
# admin_password="Password123!"
# }


## Argument Reference:

The following arguments are supported:

name - (Required) Specifies the name of the Virtual Machine. Changing this forces a new resource to be created.

resource_group_name - (Required) Specifies the name of the Resource Group in which the Virtual Machine should exist. Changing this forces a new resource to be created.

location - (Required) Specifies the Azure Region where the Virtual Machine exists. Changing this forces a new resource to be created.

network_interface_ids - (Required) A list of Network Interface ID's which should be associated with the Virtual Machine.

os_profile_linux_config - (Required, when a Linux machine) A os_profile_linux_config block.

os_profile_windows_config - (Required, when a Windows machine) A os_profile_windows_config block.

vm_size - (Required) Specifies the size of the Virtual Machine. See also Azure VM Naming Conventions.

### A os_profile block supports the following:

computer_name - (Required) Specifies the name of the Virtual Machine.

admin_username - (Required) Specifies the name of the local administrator account.

admin_password - (Required for Windows, Optional for Linux) The password associated with the local administrator account.

## A os_profile_linux_config block supports the following:

disable_password_authentication - (Required) Specifies whether password authentication should be disabled. If set to false, an admin_password must be specified.

## A storage_image_reference block supports the following:

This block provisions the Virtual Machine from one of two sources: an Azure Platform Image (e.g. Ubuntu/Windows Server) or a Custom Image.

### To provision from an Azure Platform Image, the following fields are applicable:

publisher - (Required) Specifies the publisher of the image used to create the virtual machine. Changing this forces a new resource to be created.

offer - (Required) Specifies the offer of the image used to create the virtual machine. Changing this forces a new resource to be created.

sku - (Required) Specifies the SKU of the image used to create the virtual machine. Changing this forces a new resource to be created.

version - (Optional) Specifies the version of the image used to create the virtual machine. Changing this forces a new resource to be created.

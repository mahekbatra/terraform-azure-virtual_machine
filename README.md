# terraform-azure-virtual_machine

<b>This module will help in creating a virtual machine in the azure cloud.</b>

# Example:
```
 module "virtual_machine" {
     source  = "mahekbatra/virtual_machine/azure"
     version = "1.4.0"
     resource_group ="taskrg"
     location="eastus"
     prefix="lwterra"
     publisher="Canonical"
     sku="16.04-LTS"
     offer="UbuntuServer"
     computer_name="myVM"
     admin_username="mahekbatra"
     admin_password="Password123!"
  }
```

## Argument Reference:

The following arguments are supported:

:one: <b>name<b/> - (Required) Specifies the name of the Virtual Machine. Changing this forces a new resource to be created.

:two: <b>resource_group_name<b/> - (Required) Specifies the name of the Resource Group in which the Virtual Machine should exist. Changing this forces a new resource to be created.

:three: <b>location</b> - (Required) Specifies the Azure Region where the Virtual Machine exists. Changing this forces a new resource to be created.

:four: <b>network_interface_ids</b> - (Required) A list of Network Interface ID's which should be associated with the Virtual Machine.

:five: <b>os_profile_linux_config</b> - (Required, when a Linux machine) A os_profile_linux_config block.

:six: <b>vm_size<b/> - (Required) Specifies the size of the Virtual Machine. See also Azure VM Naming Conventions.

### A os_profile block supports the following:

:one: computer_name - (Required) Specifies the name of the Virtual Machine.

:two: admin_username - (Required) Specifies the name of the local administrator account.

:three: admin_password - (Required for Windows, Optional for Linux) The password associated with the local administrator account.

## A os_profile_linux_config block supports the following:

<b>disable_password_authentication</b> - (Required) Specifies whether password authentication should be disabled. If set to false, an admin_password must be specified.

## A storage_image_reference block supports the following:

This block provisions the Virtual Machine from one of two sources: an Azure Platform Image (e.g. Ubuntu/Windows Server) or a Custom Image.

### To provision from an Azure Platform Image, the following fields are applicable:

:one: publisher - (Required) Specifies the publisher of the image used to create the virtual machine. Changing this forces a new resource to be created.

:two: offer - (Required) Specifies the offer of the image used to create the virtual machine. Changing this forces a new resource to be created.

:three: sku - (Required) Specifies the SKU of the image used to create the virtual machine. Changing this forces a new resource to be created.

:four: version - (Optional) Specifies the version of the image used to create the virtual machine. Changing this forces a new resource to be created.

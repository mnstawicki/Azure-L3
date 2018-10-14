# Lesson 3, Task 3.1

Naming convention:

`project-id>-<role>-<resource>-<id>`

where:

`<project-id>` - id of the project, 3 to 10 lowercase letters and/or digits  
`<role>` - functional role in the project  
`<resource>` - one of the following: `vnet, vm, disk, dstorage`  
`<id>` - resource id within the project, 3 digits  

Examples:

`lab03-app-vm-001
ecommie-web-vnet-002`


# Lesson 3, Task 3.3

Role definition:

```
PS Azure:\> New-AzureRmRoleDefinition -InputFile BasicVMOperations.json


Name             : Virtual Machine Operator
Id               : e9588f45-bee6-4936-b551-3b7864f8bbb1
IsCustom         : True
Description      : Start and stop Virtual Machines, raise support request
Actions          : {Microsoft.Compute/virtualMachines/start/action, Microsoft.Compute/virtualMachines/restart/action,
                   Microsoft.Compute/virtualMachines/powerOff/action}
NotActions       : {}
DataActions      : {}
NotDataActions   : {}
AssignableScopes : {/subscriptions/cc04e834-5dbd-4aeb-a95f-a583c2e87ab2}
```

JSON definition of the new role:

```
PS Azure:\> Get-AzureRmRoleDefinition "Virtual Machine Operator" | ConvertTo-Json{
  "Name": "Virtual Machine Operator",
  "Id": "e9588f45-bee6-4936-b551-3b7864f8bbb1",
  "IsCustom": true,
  "Description": "Start and stop Virtual Machines, raise support request",
  "Actions": [
    "Microsoft.Compute/virtualMachines/start/action",
    "Microsoft.Compute/virtualMachines/restart/action",
    "Microsoft.Compute/virtualMachines/powerOff/action"
  ],
  "NotActions": [],
  "DataActions": [],
  "NotDataActions": [],
  "AssignableScopes": [
    "/subscriptions/cc04e834-5dbd-4aeb-a95f-a583c2e87ab2"
  ]
}
```

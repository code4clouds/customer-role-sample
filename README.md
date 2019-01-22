# Adding Azure Custom Role

The sample code here shows how to create a custom user role for Azure.  It defines a role that allows users the creation of resource groups in a subscription.

## Requirements

- [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
- Your Azure SubscriptionID

## Usage

- Update the contribute-rg-write.json

- Execute the az-cli command to add the role to the subscription

``` bash
az role definition create --role-definition ./contribute-rg-write.json
```
- The output will be something similar to this:
``` json
{
  "assignableScopes": [
    "/subscriptions/<your SubscriptionID>"
  ],
  "description": "Can create resource groups.",
  "id": "/subscriptions/<your SubscriptionID>/providers/Microsoft.Authorization/roleDefinitions/<your new roleID>",
  "name": "<your new roleID>",
  "permissions": [
    {
      "actions": [
        "Microsoft.Resources/*/write",
        "Microsoft.Resources/subscriptions/resourceGroups/write"
      ],
      "dataActions": [],
      "notActions": [],
      "notDataActions": []
    }
  ],
  "roleName": "Resource Group Write Access",
  "roleType": "CustomRole",
  "type": "Microsoft.Authorization/roleDefinitions"
}
```
# Azure ARM Template snippets

## Add an Azure Function Key

The following snippet allows you to add a new function / host key to your Azure Function using an ARM template:

![Azure ARM Function Key](/img/2020-01-23-11-05-17.png)


https://github.com/Azure/azure-quickstart-templates/issues/6757

Snippet:

```json
{
    "type": "Microsoft.Web/sites/host/functionKeys",
    "apiVersion": "2018-11-01",
    "name": "my-api-function-name, '/default/my-key-name')]",
    "properties": {
        "name": "my-key-name",
        "value": "my-key-value"
    },
    "dependsOn": [
        "[resourceId('Microsoft.Web/sites', my-api-function-name)]"
    ]
}
```

## Deploy Azure resources to more than one subscription or resource group

"resources": [
  {
    "apiVersion": "2017-05-10",
    "name": "nestedTemplate",
    "type": "Microsoft.Resources/deployments",
    "resourceGroup": "[parameters('secondResourceGroup')]",
    "subscriptionId": "[parameters('secondSubscriptionID')]",
    ...
  }
]

[Source](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/cross-resource-group-deployment?tabs=azure-powershell)

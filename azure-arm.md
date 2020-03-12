# Azure ARM Template snippets

## Add an Azure Function Key

The following snippet allows you to add a new function / host key to your Azure Function using an ARM template:

![Azure ARM Function Key](/img/2020-01-23-11-05-17.png)

[related GitHub issue](https://github.com/Azure/azure-quickstart-templates/issues/6757)

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

```json
"resources": [
  {
    "apiVersion": "2017-05-10",
    "name": "nestedTemplate",
    "type": "Microsoft.Resources/deployments",
    "resourceGroup": "[parameters('secondResourceGroup')]",
    "subscriptionId": "[parameters('secondSubscriptionID')]",
    // ...
  }
]
```

[Source](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/cross-resource-group-deployment?tabs=azure-powershell)

## Use the reference ressources with ressources that are defined in another template

You can use the reference function on ressources that are deployed in another template by explicitly setting the **API Version** to the same version that you`re using in the other template:

```json
"diagnosticsProfile": {
     "bootDiagnostics": {
         "enabled": "true",
         "storageUri": "[reference(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), '2019-06-01').primaryEndpoints.blob]"
     }
}
```

[Source](https://docs.microsoft.com/de-de/azure/azure-resource-manager/templates/template-best-practices#resources)

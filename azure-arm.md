# Azure ARM Template snippets

## Add an Azure Function Key

![Azure ARM Function Key](/img/2020-01-23-11-05-17.png)

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

# Azure CLI snippets

## Rest request using the CLI

```bash
az rest --method post --uri \
"/subscriptions/$SUBSCRIPTION_ID/resourceGroups/$RESOURCE_GROUP/providers/Microsoft.Web/sites/$FUNCTION_APP_NAME/host/default/listKeys?api-version=2018-11-01" \
--query functionKeys.default --output tsv
```

## Link a partner ID to your Azure accounts

### Install PAL extension

```bash
az extension add --name managementpartner
```

### Login with Service Principal

```bash
az login --tenant <tenantId> --service-principal -u <appid> -p <secret>
```

### ... Or with a user

```bash
az login --tenant <tenantId>
```

### Retrieve current PAL

```bash
az managementpartner show
```

### Create new PAL

```bash
az managementpartner create --partner-id 1234567
```

### Update PAL

```bash
az managementpartner update --partner-id 1234567
```

See also: [Use the Azure CLI to link to a new partner ID](https://docs.microsoft.com/en-us/azure/cost-management-billing/manage/link-partner-id#use-the-azure-cli-to-link-to-a-new-partner-id)

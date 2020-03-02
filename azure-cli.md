# Azure CLI snippets

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

### Update PAL

```bash
az managementpartner update --partner-id 1234567
```

### Create new PAL

```bash
az managementpartner create --partner-id 1234567
```

See also: [Use the Azure CLI to link to a new partner ID](https://docs.microsoft.com/en-us/azure/cost-management-billing/manage/link-partner-id#use-the-azure-cli-to-link-to-a-new-partner-id)

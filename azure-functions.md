# Azure Functions

## Forward EventGrid events to localhost using ngrok

Before you go forward, start the Azure function in order to handle the validation handshake!

=> Now grab the URL and replace it in the first parameter:
$ngrok = 'https://eee836833cd8.ngrok.io/runtime/webhooks/EventGrid?functionName=ProcessOperationUpdate'
$includedEventTypes = "Microsoft.Resources.ResourceDeleteSuccess", "Microsoft.Resources.ResourceWriteSuccess"
New-AzEventGridSubscription `
-EventSubscriptionName ngrokForward `
-Endpoint $ngrok `
-IncludedEventType $includedEventTypes

```bash
ngrok http -host-header=localhost 7071
```

##Fetch Metadata

To retrieve all the different parameters to build the push notification, you should call the fetch metadata request.

Example:

```csharp
var responseMetadata = client.FetchMetadata();
```

##Fetch Screen Tags

If you are going to send a push notification with a tag content, you should call the fetch screen tags request.

Example:

```csharp
var responseScreenTags = client.FetchScreenTags();
```

##Fetch Device Info URL

If you want to access the file with the reports of custom data for all users, you should call the fetch device info request.

Example:

```csharp
var responseCustom = client.FetchDeviceInfoUrl();
```

##Fetch Device Info URL

If you want to access the file with the reports of all push notifications, you should call the fetch push open request.

Example:

```csharp
var responseOpen = client.FetchPushOpenUrl();
```
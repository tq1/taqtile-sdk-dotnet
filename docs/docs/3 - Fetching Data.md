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

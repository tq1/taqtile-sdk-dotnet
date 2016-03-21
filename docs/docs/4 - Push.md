##Schedule Push Exclusive Notification

To send a push exclusive notification for one specific client, you should set the maximum audience for the push. In this case will be set to 1 because it should send just for one specific client.  If the number of devices found with the parameters used for filtering is bigger than the value setted ("1"), the push will not be sent for safety measures. Also the push can be grouped by an category id. If this `GroupId` is not provided, our service will generate one.
In order to create a push exclusive notification, you should send a Push Exclusive Notification request to the API. If the request occur how expected, it will return an object with the GroupId.

Example:

```csharp
// Schedule push exclusive notification segmented by a specific custom identification and send with a tag
// ScheduleAt must be in UTC time, and can’t be more than one hour in the past.

var responseExclusivePush = client.SchedulePushExclusiveNotification(new TQ1PushExclusiveRequest()
{
    Content = new PushContent()
    {
        Message = "Testing push send from API ",
        Title = string.Format("Public API push test {0}", TQ1Helper.ToUnixTime(DateTime.Now.ToUniversalTime())),
        ScheduledAt = TQ1Helper.ToUnixTime(DateTime.Now.ToUniversalTime())
    },
    Parameters = new PushParameters()
    {
        Platform = "iOS",
        Custom = new Dictionary<string, List<object>>()
        {
            {"clienteid", new List<object>(new object[] {"123"})}
        }
    },
    MaxAudience = 2,
    GroupId = "push_notification_random_id"
});
```

##Schedule Regular Push Notification

You can also send a generic push notification targeting possibly your entire devices base. In this case, neither `GroupId` nor `MaxAudience` arguments are valid. This method returns an empty object.

Example:

```csharp
var responsePush = client.SchedulePushNotification(new TQ1PushRequest()
{
    Content = new PushContent()
    {
        Message = "Testing push send from API ",
        Title = "Test",
        ScheduledAt = TQ1Helper.ToUnixTime(DateTime.Now.ToUniversalTime())
    },
    Parameters = new PushParameters()
    {
        Platform = "iOS",
    }
});
```
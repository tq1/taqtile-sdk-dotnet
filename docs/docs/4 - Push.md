##Schedule Push Exclusive Notification

To send a push exclusive notification for one specific client, you should set the maximum audience for the push. In this case will be set to 1 because it should send just for one specific client.  If the number of devices found with the parameters used for filtering is bigger than the value setted ("1"), the push will not be sent for safety measures. Also the push can be grouped by an categorie id.
In order to create a push exclusive notification, you should send a Push Exclusive Notification request to the API. If the request occur how expected, it will return an object with a string "success" and a token.

Example:

```csharp
//Schedule push exclusive notification segmented by a specific custom identification and send with a tag
// ScheduleAt must be in UTC time, and can’t be more than one hour in the past.

var responseExclusivePush = client.SchedulePushExclusiveNotification(new TQ1PushExclusiveRequest()
            {
                Content = new PushContent()
                {
                    Message = "Testing push send from API ",
                    Title = string.Format(" Public API push test {0}", TQ1Helper.ToUnixTime(DateTime.Now)),
                    ScheduledAt = TQ1Helper.ToUnixTime(DateTime.UtcNow),

 // Example - change
			 TagId = "A tag id chosen from fetch Screen Tags",
			 Tag = new ScreenTag()
			 {
			     Name = "Screen tag name from fetch Screen Tags",
     Values = new Dictionary<string, List<object>>()
     {
         {"key from fetch Screen Tags", "this is where tag value goes"}
     }
			 }
                },
                Parameters = new PushParameters()
                {
                    Custom = new Dictionary<string, List<object>>()
                    {
                        {"clienteCodigo", new List<object>(new object[] { "this is where client code goes"})}
                    }
                },
                MaxAudience = 1,
                GroupId = "push_notification_random_id"
});
```

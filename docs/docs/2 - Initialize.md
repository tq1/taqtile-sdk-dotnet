## Initialize TQ1Client class

The main class that access all TQ1 public API endpoints.

To call all the methods needed to send a push notification, first you should set the following parameters:

  - url
  - appKey
  - encriptionSecret

Example:

```csharp
string url = "http://api.tq1.io";
string appKey = "123456789123456789abcdefg";
string encriptionSecret = "this is where secret goes";

TQ1Client client = new TQ1Client(url, appKey, encriptionSecret)
```

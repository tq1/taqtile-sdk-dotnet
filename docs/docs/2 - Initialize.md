## Initialize TQ1Client class

The main class that access all TQ1 public API endpoints.

To call all the methods needed to send a push notification, first you should set the following parameters:

  - app key (this information is provided by us)
  - JWT token (the token can be acquired in our admin portal)
  - user id (this information is provided by us)

Example:

```csharp
string applicationKey = "f54d4a2c3b6543226fbe74e55074a531a4b62b28";
string token = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzIjoiMSJ9.Drra7WLy2QVV6B_uF0WEEGbv2-AGXH0ZxyXpklF6nxM";
string userId = "9222681bca06ea25101db7a2cd9584e005949bbf";

TQ1Client client = new TQ1Client(applicationKey, userId, token);
```

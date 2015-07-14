## Initialize TQ1Client class

The main class that access all TQ1 public API endpoints.

To call all the methods needed to send a push notification, first you should set the following parameters:

Production:

  - url - "http://npc-api.tq1.taqtile.io"
  - appKey
    - Extra - "ec5ce5aaaa7cf18258ffcb439d3246cf6002e4aa"
    - Extra Lista - "7e0396c42b14dc0b84a718df30ff1ed583f2669f"
    - Casas Bahia - "fba847b70c81a025a51364ab85b46d39eb33d16e"
    - Ponto Frio - "035298321256723b5922ff02b797f21dc823dd9e"
  - encriptionSecret

Staging:

  - url - "http://npc-api-staging.tq1.taqtile.io"
  - appKey
    - Extra - "95a7274b1519985c8cf2b4bfd7921d46fb6f7fcb"
    - Extra Lista - "1e7878e7b764d98c165fce1d7bb796a403d37789"
    - Casas Bahia - "665e6dda879eff202935610867ac4a5348191643"
    - Ponto Frio - "51fe482f654744ced7a9b1f0c55cd0305d4783a8"
  - encriptionSecret

Example:

```csharp
string url = "http://npc-api.tq1.taqtile.io";
string appKey = "ec5ce5aaaa7cf18258ffcb439d3246cf6002e4aa";
string encriptionSecret = "this is where secret goes";

TQ1Client client = new TQ1Client(url, appKey, encriptionSecret)
```

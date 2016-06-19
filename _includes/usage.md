```csharp
using (var client = new Client (username, password)) {

    var request = new SearchRequest {
        ExpertQuery = "TI ~ privacy",
        SearchLanguage = Language.en,
        PageSize = 10,
        Page = 1
    };

    var response = await client.DoQueryAsync (request);

    var title = response.Results [0].Content.Notice.Expression?.Title [0].Value;
}
```

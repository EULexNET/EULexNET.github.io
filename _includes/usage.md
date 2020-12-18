```csharp
using (var client = new Client (username, password)) {

    var request = new SearchRequest {
        ExpertQuery = "TI ~ privacy",
        SearchLanguage = Language.en,
        PageSize = 10,
        Page = 1
    };

    var response = await client.DoQueryAsync (request);

    var notice = response.Results[0].Content.Notice;
    var title = notice.Expression?.Title[0].Value;
}
```

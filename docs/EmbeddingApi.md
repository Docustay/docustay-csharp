# Docustay.Api.Api.EmbeddingApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BuilderSession**](EmbeddingApi.md#buildersession) | **POST** /api/v1/embedded/builder-session | Start an embedded template builder session |
| [**ScribeSession**](EmbeddingApi.md#scribesession) | **POST** /api/v1/embedded/scribe-session | Start an embedded Scribe session |

<a id="buildersession"></a>
# **BuilderSession**
> BuilderSession BuilderSession (BuilderSessionRequest builderSessionRequest)

Start an embedded template builder session

Returns a link that works for one hour and is meant for an iframe or the `<docustay-builder>` element on one of your allowed websites. The builder lets the person write a document, drop signature and other fields on it, and save it as a template; the saved template's id comes back to your page in a `saved` event. The link holds a key of its own that can only read and write templates and stops working after an hour. Needs an `Idempotency-Key` header.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class BuilderSessionExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmbeddingApi(config);
            var builderSessionRequest = new BuilderSessionRequest(); // BuilderSessionRequest | 

            try
            {
                // Start an embedded template builder session
                BuilderSession result = apiInstance.BuilderSession(builderSessionRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmbeddingApi.BuilderSession: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BuilderSessionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Start an embedded template builder session
    ApiResponse<BuilderSession> response = apiInstance.BuilderSessionWithHttpInfo(builderSessionRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmbeddingApi.BuilderSessionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **builderSessionRequest** | [**BuilderSessionRequest**](BuilderSessionRequest.md) |  |  |

### Return type

[**BuilderSession**](BuilderSession.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The session. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **409** | Embedding is off, or that website is not on your allowed list (Developers → Embedding). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="scribesession"></a>
# **ScribeSession**
> BuilderSession ScribeSession (ScribeSessionRequest scribeSessionRequest)

Start an embedded Scribe session

Returns a link that works for one hour and is meant for an iframe or the `<docustay-scribe>` element on one of your allowed websites. The person picks a play, names who signs, answers a few clickable questions and gets a DRAFT; the draft's id comes back to your page in a `drafted` event. The link holds a key of its own that is draft-only (it cannot send: asking to send files an approval a person decides in Docustay), allows 50 drafts a day and stops working after an hour. Needs an `Idempotency-Key` header.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ScribeSessionExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmbeddingApi(config);
            var scribeSessionRequest = new ScribeSessionRequest(); // ScribeSessionRequest | 

            try
            {
                // Start an embedded Scribe session
                BuilderSession result = apiInstance.ScribeSession(scribeSessionRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmbeddingApi.ScribeSession: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ScribeSessionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Start an embedded Scribe session
    ApiResponse<BuilderSession> response = apiInstance.ScribeSessionWithHttpInfo(scribeSessionRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmbeddingApi.ScribeSessionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **scribeSessionRequest** | [**ScribeSessionRequest**](ScribeSessionRequest.md) |  |  |

### Return type

[**BuilderSession**](BuilderSession.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The session. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **409** | Embedding is off, or that website is not on your allowed list (Developers → Embedding). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


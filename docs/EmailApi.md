# Docustay.Api.Api.EmailApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListEmails**](EmailApi.md#listemails) | **GET** /api/v1/emails | The log of email about your documents |

<a id="listemails"></a>
# **ListEmails**
> ListEmails200Response ListEmails (Guid? documentId = null, string? to = null, string? status = null, string? kind = null, int? limit = null, string? cursor = null)

The log of email about your documents

Every email sent about a document, to a person named on it: kind, subject, status (sent, delivered, bounced, complained, failed, paused). Filter by `documentId`, `to`, `status`, `kind`. No bodies, no links.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListEmailsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmailApi(config);
            var documentId = 6f1c1f0e-7a0c-4d1d-9b5e-2f0a7b1c3d4e;  // Guid? |  (optional) 
            var to = "to_example";  // string? |  (optional) 
            var status = "status_example";  // string? |  (optional) 
            var kind = "kind_example";  // string? |  (optional) 
            var limit = 56;  // int? |  (optional) 
            var cursor = "cursor_example";  // string? |  (optional) 

            try
            {
                // The log of email about your documents
                ListEmails200Response result = apiInstance.ListEmails(documentId, to, status, kind, limit, cursor);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmailApi.ListEmails: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListEmailsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // The log of email about your documents
    ApiResponse<ListEmails200Response> response = apiInstance.ListEmailsWithHttpInfo(documentId, to, status, kind, limit, cursor);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmailApi.ListEmailsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **documentId** | **Guid?** |  | [optional]  |
| **to** | **string?** |  | [optional]  |
| **status** | **string?** |  | [optional]  |
| **kind** | **string?** |  | [optional]  |
| **limit** | **int?** |  | [optional]  |
| **cursor** | **string?** |  | [optional]  |

### Return type

[**ListEmails200Response**](ListEmails200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A page of emails, newest first. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


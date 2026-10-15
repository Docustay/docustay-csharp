# Docustay.Api.Api.WebhooksApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWebhook**](WebhooksApi.md#createwebhook) | **POST** /api/v1/webhooks | Add a webhook |
| [**DeleteWebhook**](WebhooksApi.md#deletewebhook) | **DELETE** /api/v1/webhooks/{id} | Remove a webhook |
| [**FetchRelayEvents**](WebhooksApi.md#fetchrelayevents) | **GET** /api/v1/webhooks/{id}/relay | Fetch stored deliveries of a relay webhook |
| [**ListWebhookDeliveries**](WebhooksApi.md#listwebhookdeliveries) | **GET** /api/v1/webhooks/{id}/deliveries | Recent deliveries |
| [**ListWebhookTopics**](WebhooksApi.md#listwebhooktopics) | **GET** /api/v1/webhooks/topics | The events a webhook can subscribe to |
| [**ListWebhooks**](WebhooksApi.md#listwebhooks) | **GET** /api/v1/webhooks | List webhooks |
| [**RotateWebhookSecret**](WebhooksApi.md#rotatewebhooksecret) | **POST** /api/v1/webhooks/{id}/rotate | Rotate the signing secret |
| [**TestWebhook**](WebhooksApi.md#testwebhook) | **POST** /api/v1/webhooks/{id}/test | Send a test event |

<a id="createwebhook"></a>
# **CreateWebhook**
> CreateWebhook201Response CreateWebhook (CreateWebhookRequest createWebhookRequest)

Add a webhook

Give an `https` `url` that can be reached from the internet, or `relay: true` for an endpoint that keeps its signed deliveries for `docustay listen` to fetch to your own computer. The signing secret is in the answer **once**. Events are signed with HMAC-SHA256 (Standard Webhooks headers `webhook-id`, `webhook-timestamp`, `webhook-signature`; also `keystone-signature`).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class CreateWebhookExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);
            var createWebhookRequest = new CreateWebhookRequest(); // CreateWebhookRequest | 

            try
            {
                // Add a webhook
                CreateWebhook201Response result = apiInstance.CreateWebhook(createWebhookRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.CreateWebhook: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWebhookWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add a webhook
    ApiResponse<CreateWebhook201Response> response = apiInstance.CreateWebhookWithHttpInfo(createWebhookRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.CreateWebhookWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWebhookRequest** | [**CreateWebhookRequest**](CreateWebhookRequest.md) |  |  |

### Return type

[**CreateWebhook201Response**](CreateWebhook201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Added. &#x60;secret&#x60; is shown once. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewebhook"></a>
# **DeleteWebhook**
> DeleteWebhook200Response DeleteWebhook (Guid id)

Remove a webhook

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class DeleteWebhookExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);
            var id = "id_example";  // Guid | 

            try
            {
                // Remove a webhook
                DeleteWebhook200Response result = apiInstance.DeleteWebhook(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.DeleteWebhook: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWebhookWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove a webhook
    ApiResponse<DeleteWebhook200Response> response = apiInstance.DeleteWebhookWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.DeleteWebhookWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**DeleteWebhook200Response**](DeleteWebhook200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Removed: it receives nothing more. Its past deliveries stay in the record. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="fetchrelayevents"></a>
# **FetchRelayEvents**
> FetchRelayEvents200Response FetchRelayEvents (Guid id, Guid? after = null, int? wait = null, int? limit = null)

Fetch stored deliveries of a relay webhook

For `docustay listen`. Returns deliveries stored since `after` (an id from a previous answer; leave out for the newest few), oldest first, each with the exact headers to forward so the signature checks out. Waits up to `wait` seconds (max 25) when there is nothing yet. Kept 24 hours.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class FetchRelayEventsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);
            var id = "id_example";  // Guid | 
            var after = "after_example";  // Guid? |  (optional) 
            var wait = 56;  // int? |  (optional) 
            var limit = 56;  // int? |  (optional) 

            try
            {
                // Fetch stored deliveries of a relay webhook
                FetchRelayEvents200Response result = apiInstance.FetchRelayEvents(id, after, wait, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.FetchRelayEvents: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the FetchRelayEventsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch stored deliveries of a relay webhook
    ApiResponse<FetchRelayEvents200Response> response = apiInstance.FetchRelayEventsWithHttpInfo(id, after, wait, limit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.FetchRelayEventsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **after** | **Guid?** |  | [optional]  |
| **wait** | **int?** |  | [optional]  |
| **limit** | **int?** |  | [optional]  |

### Return type

[**FetchRelayEvents200Response**](FetchRelayEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Stored deliveries. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listwebhookdeliveries"></a>
# **ListWebhookDeliveries**
> ListWebhookDeliveries200Response ListWebhookDeliveries (Guid id)

Recent deliveries

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListWebhookDeliveriesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);
            var id = "id_example";  // Guid | 

            try
            {
                // Recent deliveries
                ListWebhookDeliveries200Response result = apiInstance.ListWebhookDeliveries(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.ListWebhookDeliveries: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWebhookDeliveriesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Recent deliveries
    ApiResponse<ListWebhookDeliveries200Response> response = apiInstance.ListWebhookDeliveriesWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.ListWebhookDeliveriesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**ListWebhookDeliveries200Response**](ListWebhookDeliveries200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The last 50 delivery attempts, newest first. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listwebhooktopics"></a>
# **ListWebhookTopics**
> ListWebhookTopics200Response ListWebhookTopics ()

The events a webhook can subscribe to

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListWebhookTopicsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);

            try
            {
                // The events a webhook can subscribe to
                ListWebhookTopics200Response result = apiInstance.ListWebhookTopics();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.ListWebhookTopics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWebhookTopicsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // The events a webhook can subscribe to
    ApiResponse<ListWebhookTopics200Response> response = apiInstance.ListWebhookTopicsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.ListWebhookTopicsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**ListWebhookTopics200Response**](ListWebhookTopics200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The event names. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listwebhooks"></a>
# **ListWebhooks**
> ListWebhooks200Response ListWebhooks ()

List webhooks

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListWebhooksExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);

            try
            {
                // List webhooks
                ListWebhooks200Response result = apiInstance.ListWebhooks();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.ListWebhooks: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWebhooksWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List webhooks
    ApiResponse<ListWebhooks200Response> response = apiInstance.ListWebhooksWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.ListWebhooksWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**ListWebhooks200Response**](ListWebhooks200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Your webhook endpoints, newest first. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="rotatewebhooksecret"></a>
# **RotateWebhookSecret**
> RotateWebhookSecret200Response RotateWebhookSecret (Guid id, RotateWebhookSecretRequest? rotateWebhookSecretRequest = null)

Rotate the signing secret

Makes a new secret (shown once). For `windowHours` (default 24) every event is signed with both the new and the old secret, so your receiver can switch without a gap.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class RotateWebhookSecretExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);
            var id = "id_example";  // Guid | 
            var rotateWebhookSecretRequest = new RotateWebhookSecretRequest?(); // RotateWebhookSecretRequest? |  (optional) 

            try
            {
                // Rotate the signing secret
                RotateWebhookSecret200Response result = apiInstance.RotateWebhookSecret(id, rotateWebhookSecretRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.RotateWebhookSecret: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RotateWebhookSecretWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Rotate the signing secret
    ApiResponse<RotateWebhookSecret200Response> response = apiInstance.RotateWebhookSecretWithHttpInfo(id, rotateWebhookSecretRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.RotateWebhookSecretWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **rotateWebhookSecretRequest** | [**RotateWebhookSecretRequest?**](RotateWebhookSecretRequest?.md) |  | [optional]  |

### Return type

[**RotateWebhookSecret200Response**](RotateWebhookSecret200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The new secret. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="testwebhook"></a>
# **TestWebhook**
> TestWebhook200Response TestWebhook (Guid id, TestWebhookRequest? testWebhookRequest = null)

Send a test event

Sends a sample signed event (`test: true` in its payload) to the webhook now and returns the receiver's answer. Nothing is stored and failures here never count toward disabling the webhook. Nothing is created, so no Idempotency-Key is needed: repeating the call just sends another test.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class TestWebhookExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new WebhooksApi(config);
            var id = "id_example";  // Guid | 
            var testWebhookRequest = new TestWebhookRequest?(); // TestWebhookRequest? |  (optional) 

            try
            {
                // Send a test event
                TestWebhook200Response result = apiInstance.TestWebhook(id, testWebhookRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.TestWebhook: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the TestWebhookWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send a test event
    ApiResponse<TestWebhook200Response> response = apiInstance.TestWebhookWithHttpInfo(id, testWebhookRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.TestWebhookWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **testWebhookRequest** | [**TestWebhookRequest?**](TestWebhookRequest?.md) |  | [optional]  |

### Return type

[**TestWebhook200Response**](TestWebhook200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | What the receiver answered. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


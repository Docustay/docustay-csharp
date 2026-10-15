# Docustay.Api.Api.AutomationsApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListAutomations**](AutomationsApi.md#listautomations) | **GET** /api/v1/automations | List automations |
| [**SetAutomationOn**](AutomationsApi.md#setautomationon) | **POST** /api/v1/automations/{id}/enable | Switch an automation on or off |

<a id="listautomations"></a>
# **ListAutomations**
> Object ListAutomations ()

List automations

Each automation built on the canvas: when it starts (a signed document from a template or form), its steps, whether it is on, how many times it ran and its recent runs. (`GET /api/v1/playbooks` lists packs: bundles of skills and templates.)

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListAutomationsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new AutomationsApi(config);

            try
            {
                // List automations
                Object result = apiInstance.ListAutomations();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AutomationsApi.ListAutomations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListAutomationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List automations
    ApiResponse<Object> response = apiInstance.ListAutomationsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AutomationsApi.ListAutomationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List automations |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setautomationon"></a>
# **SetAutomationOn**
> Object SetAutomationOn (Guid id, SetAutomationOnRequest setAutomationOnRequest)

Switch an automation on or off

`on: true` switches it on (Pro): from then on, each matching signed document starts a run. `on: false` stops new runs, and a run that is waiting stops when its wait ends, without sending its reminder.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class SetAutomationOnExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new AutomationsApi(config);
            var id = "id_example";  // Guid | 
            var setAutomationOnRequest = new SetAutomationOnRequest(); // SetAutomationOnRequest | 

            try
            {
                // Switch an automation on or off
                Object result = apiInstance.SetAutomationOn(id, setAutomationOnRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AutomationsApi.SetAutomationOn: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetAutomationOnWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Switch an automation on or off
    ApiResponse<Object> response = apiInstance.SetAutomationOnWithHttpInfo(id, setAutomationOnRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AutomationsApi.SetAutomationOnWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **setAutomationOnRequest** | [**SetAutomationOnRequest**](SetAutomationOnRequest.md) |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Switch an automation on or off |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# Docustay.Api.Api.ContractsApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListContracts**](ContractsApi.md#listcontracts) | **GET** /api/v1/contracts | List signed contracts with their key dates |
| [**SetContractDate**](ContractsApi.md#setcontractdate) | **POST** /api/v1/contracts/{id}/dates | Correct a contract&#39;s key date |

<a id="listcontracts"></a>
# **ListContracts**
> Object ListContracts (string? q = null, int? limit = null)

List signed contracts with their key dates

Every signed document with the dates read from its boxes at signing — start, end, notice, renewal — and its value, with where each came from (`source`: a box, or a person's correction). Filter with `q` (title or person).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListContractsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new ContractsApi(config);
            var q = "q_example";  // string? |  (optional) 
            var limit = 56;  // int? |  (optional) 

            try
            {
                // List signed contracts with their key dates
                Object result = apiInstance.ListContracts(q, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContractsApi.ListContracts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListContractsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List signed contracts with their key dates
    ApiResponse<Object> response = apiInstance.ListContractsWithHttpInfo(q, limit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContractsApi.ListContractsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **q** | **string?** |  | [optional]  |
| **limit** | **int?** |  | [optional]  |

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
| **200** | List signed contracts with their key dates |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setcontractdate"></a>
# **SetContractDate**
> Object SetContractDate (Guid id, SetContractDateRequest setContractDateRequest)

Correct a contract's key date

Sets one key date (or the value) on a signed document by hand. The signed PDF never changes; the correction is kept as the person's, and renewal reminders follow it. `date` is YYYY-MM-DD; `null` clears it.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class SetContractDateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new ContractsApi(config);
            var id = "id_example";  // Guid | 
            var setContractDateRequest = new SetContractDateRequest(); // SetContractDateRequest | 

            try
            {
                // Correct a contract's key date
                Object result = apiInstance.SetContractDate(id, setContractDateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContractsApi.SetContractDate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetContractDateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Correct a contract's key date
    ApiResponse<Object> response = apiInstance.SetContractDateWithHttpInfo(id, setContractDateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContractsApi.SetContractDateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **setContractDateRequest** | [**SetContractDateRequest**](SetContractDateRequest.md) |  |  |

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
| **200** | Correct a contract&#39;s key date |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


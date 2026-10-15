# Docustay.Api.Api.ReportsApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**Report**](ReportsApi.md#report) | **GET** /api/v1/reports | Counts of what was sent and completed |

<a id="report"></a>
# **Report**
> Report Report (string? from = null, string? to = null, Guid? team = null)

Counts of what was sent and completed

Real documents only — documents made in test mode are never counted. Dates are in the workspace's own time zone; `to` is inclusive; the default window is the last 30 days.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ReportExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new ReportsApi(config);
            var from = 2026-10-01;  // string? |  (optional) 
            var to = 2026-10-31;  // string? |  (optional) 
            var team = 6f1c1f0e-7a0c-4d1d-9b5e-2f0a7b1c3d4e;  // Guid? |  (optional) 

            try
            {
                // Counts of what was sent and completed
                Report result = apiInstance.Report(from, to, team);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ReportsApi.Report: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ReportWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Counts of what was sent and completed
    ApiResponse<Report> response = apiInstance.ReportWithHttpInfo(from, to, team);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ReportsApi.ReportWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **from** | **string?** |  | [optional]  |
| **to** | **string?** |  | [optional]  |
| **team** | **Guid?** |  | [optional]  |

### Return type

[**Report**](Report.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


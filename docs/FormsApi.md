# Docustay.Api.Api.FormsApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetForm**](FormsApi.md#getform) | **GET** /api/v1/forms/{id} | Get a form |
| [**ListFormResponses**](FormsApi.md#listformresponses) | **GET** /api/v1/forms/{id}/responses | List a form&#39;s responses |
| [**ListFormTemplates**](FormsApi.md#listformtemplates) | **GET** /api/v1/forms/templates | List form templates |
| [**ListForms**](FormsApi.md#listforms) | **GET** /api/v1/forms | List forms |
| [**PublishForm**](FormsApi.md#publishform) | **POST** /api/v1/forms/publish | Publish a form |
| [**SetFormOpen**](FormsApi.md#setformopen) | **POST** /api/v1/forms/{id}/open | Open or close a form |
| [**UnpublishForm**](FormsApi.md#unpublishform) | **POST** /api/v1/forms/{id}/unpublish | Unpublish a form |

<a id="getform"></a>
# **GetForm**
> Object GetForm (Guid id)

Get a form

One form: its link (`/f/<workspace>/<slug>`), settings, response count and whether it is open.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class GetFormExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);
            var id = "id_example";  // Guid | 

            try
            {
                // Get a form
                Object result = apiInstance.GetForm(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.GetForm: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetFormWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get a form
    ApiResponse<Object> response = apiInstance.GetFormWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.GetFormWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

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
| **200** | Get a form |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listformresponses"></a>
# **ListFormResponses**
> Object ListFormResponses (Guid id, int? limit = null, int? offset = null)

List a form's responses

Newest first. Each response is a document: its id opens it with GET /api/v1/documents/{id}. `limit` is 1 to 500.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListFormResponsesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);
            var id = "id_example";  // Guid | 
            var limit = 56;  // int? |  (optional) 
            var offset = 56;  // int? |  (optional) 

            try
            {
                // List a form's responses
                Object result = apiInstance.ListFormResponses(id, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.ListFormResponses: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListFormResponsesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List a form's responses
    ApiResponse<Object> response = apiInstance.ListFormResponsesWithHttpInfo(id, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.ListFormResponsesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **limit** | **int?** |  | [optional]  |
| **offset** | **int?** |  | [optional]  |

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
| **200** | List a form&#39;s responses |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listformtemplates"></a>
# **ListFormTemplates**
> Object ListFormTemplates ()

List form templates

The built-in form templates (the thirty from the template library) and your own: name, summary, who it is for, whether a team member counter-signs, and its default Publish settings.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListFormTemplatesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);

            try
            {
                // List form templates
                Object result = apiInstance.ListFormTemplates();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.ListFormTemplates: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListFormTemplatesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List form templates
    ApiResponse<Object> response = apiInstance.ListFormTemplatesWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.ListFormTemplatesWithHttpInfo: " + e.Message);
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
| **200** | List form templates |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listforms"></a>
# **ListForms**
> Object ListForms ()

List forms

Every form template in the workspace: its link name, whether it is open, its response count and whether it has closed (a closing date or a response limit).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListFormsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);

            try
            {
                // List forms
                Object result = apiInstance.ListForms();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.ListForms: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListFormsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List forms
    ApiResponse<Object> response = apiInstance.ListFormsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.ListFormsWithHttpInfo: " + e.Message);
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
| **200** | List forms |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="publishform"></a>
# **PublishForm**
> Object PublishForm (PublishFormRequest publishFormRequest)

Publish a form

Gives a form template its public link and settings (or changes them). `slug` is 4 to 60 letters, numbers and dashes. The template must be approved and have one person who fills it in, plus at most one team member who counter-signs (`settings.counterSign`).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class PublishFormExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);
            var publishFormRequest = new PublishFormRequest(); // PublishFormRequest | 

            try
            {
                // Publish a form
                Object result = apiInstance.PublishForm(publishFormRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.PublishForm: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the PublishFormWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Publish a form
    ApiResponse<Object> response = apiInstance.PublishFormWithHttpInfo(publishFormRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.PublishFormWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **publishFormRequest** | [**PublishFormRequest**](PublishFormRequest.md) |  |  |

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
| **200** | Publish a form |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setformopen"></a>
# **SetFormOpen**
> Object SetFormOpen (Guid id, SetFormOpenRequest setFormOpenRequest)

Open or close a form

`open: false` keeps the link but says the form is not taking responses.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class SetFormOpenExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);
            var id = "id_example";  // Guid | 
            var setFormOpenRequest = new SetFormOpenRequest(); // SetFormOpenRequest | 

            try
            {
                // Open or close a form
                Object result = apiInstance.SetFormOpen(id, setFormOpenRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.SetFormOpen: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetFormOpenWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Open or close a form
    ApiResponse<Object> response = apiInstance.SetFormOpenWithHttpInfo(id, setFormOpenRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.SetFormOpenWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **setFormOpenRequest** | [**SetFormOpenRequest**](SetFormOpenRequest.md) |  |  |

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
| **200** | Open or close a form |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="unpublishform"></a>
# **UnpublishForm**
> Object UnpublishForm (Guid id)

Unpublish a form

The link stops working. The form template, its settings and every response are kept; publish it again at any time.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class UnpublishFormExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new FormsApi(config);
            var id = "id_example";  // Guid | 

            try
            {
                // Unpublish a form
                Object result = apiInstance.UnpublishForm(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling FormsApi.UnpublishForm: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UnpublishFormWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Unpublish a form
    ApiResponse<Object> response = apiInstance.UnpublishFormWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling FormsApi.UnpublishFormWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

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
| **200** | Unpublish a form |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such form. |  -  |
| **409** | A conflict, for example the link name is already used by another form. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


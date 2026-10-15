# Docustay.Api.Api.TemplatesApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTemplateFromFile**](TemplatesApi.md#createtemplatefromfile) | **POST** /api/v1/templates/file | Make a template from a file with text tags |
| [**CreateTemplateFromHtml**](TemplatesApi.md#createtemplatefromhtml) | **POST** /api/v1/templates/html | Make a template from HTML with text tags |
| [**CreateTemplateFromSource**](TemplatesApi.md#createtemplatefromsource) | **POST** /api/v1/templates/source | Make a template from a document source |
| [**CustomizeLibraryTemplate**](TemplatesApi.md#customizelibrarytemplate) | **POST** /api/v1/templates/library/{slug}/customize | Customize a built-in template |
| [**DraftFromLibraryTemplate**](TemplatesApi.md#draftfromlibrarytemplate) | **POST** /api/v1/templates/library/{slug}/documents | Make a draft from a built-in template |
| [**GetLibraryTemplate**](TemplatesApi.md#getlibrarytemplate) | **GET** /api/v1/templates/library/{slug} | One built-in template |
| [**GetTemplate**](TemplatesApi.md#gettemplate) | **GET** /api/v1/templates/{id} | One template and its seats |
| [**ListLibraryTemplates**](TemplatesApi.md#listlibrarytemplates) | **GET** /api/v1/templates/library | List the built-in templates |
| [**SetTemplateDefaults**](TemplatesApi.md#settemplatedefaults) | **POST** /api/v1/templates/{id}/defaults | Set what a document made from a template starts with |
| [**UseTemplate**](TemplatesApi.md#usetemplate) | **POST** /api/v1/templates/{id}/documents | Use a written template for people |

<a id="createtemplatefromfile"></a>
# **CreateTemplateFromFile**
> TemplateMade CreateTemplateFromFile (string idempotencyKey, FileTemplateRequest fileTemplateRequest)

Make a template from a file with text tags

Reads a PDF file, places a field wherever a text tag is written in it, and keeps the result as a template. Needs an `Idempotency-Key` header.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class CreateTemplateFromFileExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var idempotencyKey = "idempotencyKey_example";  // string | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice.
            var fileTemplateRequest = new FileTemplateRequest(); // FileTemplateRequest | 

            try
            {
                // Make a template from a file with text tags
                TemplateMade result = apiInstance.CreateTemplateFromFile(idempotencyKey, fileTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.CreateTemplateFromFile: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateTemplateFromFileWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Make a template from a file with text tags
    ApiResponse<TemplateMade> response = apiInstance.CreateTemplateFromFileWithHttpInfo(idempotencyKey, fileTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.CreateTemplateFromFileWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice. |  |
| **fileTemplateRequest** | [**FileTemplateRequest**](FileTemplateRequest.md) |  |  |

### Return type

[**TemplateMade**](TemplateMade.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The template. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createtemplatefromhtml"></a>
# **CreateTemplateFromHtml**
> TemplateMade CreateTemplateFromHtml (string idempotencyKey, HtmlTemplateRequest htmlTemplateRequest)

Make a template from HTML with text tags

Prints your HTML to a PDF and places a field wherever a text tag sits, then keeps the result as a template you can send with `POST /api/v1/documents/send`. Needs an `Idempotency-Key` header.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class CreateTemplateFromHtmlExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var idempotencyKey = "idempotencyKey_example";  // string | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice.
            var htmlTemplateRequest = new HtmlTemplateRequest(); // HtmlTemplateRequest | 

            try
            {
                // Make a template from HTML with text tags
                TemplateMade result = apiInstance.CreateTemplateFromHtml(idempotencyKey, htmlTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.CreateTemplateFromHtml: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateTemplateFromHtmlWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Make a template from HTML with text tags
    ApiResponse<TemplateMade> response = apiInstance.CreateTemplateFromHtmlWithHttpInfo(idempotencyKey, htmlTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.CreateTemplateFromHtmlWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice. |  |
| **htmlTemplateRequest** | [**HtmlTemplateRequest**](HtmlTemplateRequest.md) |  |  |

### Return type

[**TemplateMade**](TemplateMade.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The template. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createtemplatefromsource"></a>
# **CreateTemplateFromSource**
> CreateTemplateFromSource201Response CreateTemplateFromSource (string idempotencyKey, CreateTemplateFromSourceRequest createTemplateFromSourceRequest)

Make a template from a document source

Keeps a document written in the shared editor's format as a template (profile `typeset` by default). Needs an `Idempotency-Key` header.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class CreateTemplateFromSourceExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var idempotencyKey = "idempotencyKey_example";  // string | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice.
            var createTemplateFromSourceRequest = new CreateTemplateFromSourceRequest(); // CreateTemplateFromSourceRequest | 

            try
            {
                // Make a template from a document source
                CreateTemplateFromSource201Response result = apiInstance.CreateTemplateFromSource(idempotencyKey, createTemplateFromSourceRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.CreateTemplateFromSource: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateTemplateFromSourceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Make a template from a document source
    ApiResponse<CreateTemplateFromSource201Response> response = apiInstance.CreateTemplateFromSourceWithHttpInfo(idempotencyKey, createTemplateFromSourceRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.CreateTemplateFromSourceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice. |  |
| **createTemplateFromSourceRequest** | [**CreateTemplateFromSourceRequest**](CreateTemplateFromSourceRequest.md) |  |  |

### Return type

[**CreateTemplateFromSource201Response**](CreateTemplateFromSource201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The template. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="customizelibrarytemplate"></a>
# **CustomizeLibraryTemplate**
> Object CustomizeLibraryTemplate (string slug, CustomizeLibraryTemplateRequest? customizeLibraryTemplateRequest = null)

Customize a built-in template

Your own editable copy of the built-in, as a new template. It counts toward the Free plan's monthly new-template limit.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class CustomizeLibraryTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var slug = "slug_example";  // string | 
            var customizeLibraryTemplateRequest = new CustomizeLibraryTemplateRequest?(); // CustomizeLibraryTemplateRequest? |  (optional) 

            try
            {
                // Customize a built-in template
                Object result = apiInstance.CustomizeLibraryTemplate(slug, customizeLibraryTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.CustomizeLibraryTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CustomizeLibraryTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Customize a built-in template
    ApiResponse<Object> response = apiInstance.CustomizeLibraryTemplateWithHttpInfo(slug, customizeLibraryTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.CustomizeLibraryTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **slug** | **string** |  |  |
| **customizeLibraryTemplateRequest** | [**CustomizeLibraryTemplateRequest?**](CustomizeLibraryTemplateRequest?.md) |  | [optional]  |

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
| **201** | Customize a built-in template |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | Not valid. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | Not allowed (for a customized copy: the plan&#39;s monthly new-template limit). |  -  |
| **404** | No such built-in template. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="draftfromlibrarytemplate"></a>
# **DraftFromLibraryTemplate**
> Object DraftFromLibraryTemplate (string slug, DraftFromLibraryTemplateRequest? draftFromLibraryTemplateRequest = null)

Make a draft from a built-in template

A new draft made straight from the built-in (nothing is copied into your templates, so it does not count toward the monthly new-template limit). Add the people and send it as any draft; it counts toward the month's documents when it is sent.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class DraftFromLibraryTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var slug = "slug_example";  // string | 
            var draftFromLibraryTemplateRequest = new DraftFromLibraryTemplateRequest?(); // DraftFromLibraryTemplateRequest? |  (optional) 

            try
            {
                // Make a draft from a built-in template
                Object result = apiInstance.DraftFromLibraryTemplate(slug, draftFromLibraryTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.DraftFromLibraryTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DraftFromLibraryTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Make a draft from a built-in template
    ApiResponse<Object> response = apiInstance.DraftFromLibraryTemplateWithHttpInfo(slug, draftFromLibraryTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.DraftFromLibraryTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **slug** | **string** |  |  |
| **draftFromLibraryTemplateRequest** | [**DraftFromLibraryTemplateRequest?**](DraftFromLibraryTemplateRequest?.md) |  | [optional]  |

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
| **201** | Make a draft from a built-in template |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | Not valid. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | Not allowed (for a customized copy: the plan&#39;s monthly new-template limit). |  -  |
| **404** | No such built-in template. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlibrarytemplate"></a>
# **GetLibraryTemplate**
> Object GetLibraryTemplate (string slug)

One built-in template

The template's fields (who fills each one) and its guidance: the questions, the facts it needs, the checklist and when not to use it.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class GetLibraryTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var slug = "slug_example";  // string | 

            try
            {
                // One built-in template
                Object result = apiInstance.GetLibraryTemplate(slug);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.GetLibraryTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLibraryTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // One built-in template
    ApiResponse<Object> response = apiInstance.GetLibraryTemplateWithHttpInfo(slug);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.GetLibraryTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **slug** | **string** |  |  |

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
| **200** | One built-in template |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | Not valid. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | Not allowed (for a customized copy: the plan&#39;s monthly new-template limit). |  -  |
| **404** | No such built-in template. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="gettemplate"></a>
# **GetTemplate**
> Template GetTemplate (Guid id)

One template and its seats

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class GetTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var id = 6f1c1f0e-7a0c-4d1d-9b5e-2f0a7b1c3d4e;  // Guid | 

            try
            {
                // One template and its seats
                Template result = apiInstance.GetTemplate(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.GetTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // One template and its seats
    ApiResponse<Template> response = apiInstance.GetTemplateWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.GetTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The template. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | No such template. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listlibrarytemplates"></a>
# **ListLibraryTemplates**
> Object ListLibraryTemplates (string? kind = null)

List the built-in templates

The built-in Document templates (`kind=document`) and Form templates (`kind=form`): title, summary, seats, field counts and the questions its guidance asks. `templateId` is your workspace's copy once it has been used. Empty when the workspace hides the library.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListLibraryTemplatesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var kind = "document";  // string? |  (optional) 

            try
            {
                // List the built-in templates
                Object result = apiInstance.ListLibraryTemplates(kind);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.ListLibraryTemplates: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListLibraryTemplatesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List the built-in templates
    ApiResponse<Object> response = apiInstance.ListLibraryTemplatesWithHttpInfo(kind);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.ListLibraryTemplatesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **kind** | **string?** |  | [optional]  |

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
| **200** | List the built-in templates |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | Not valid. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | Not allowed (for a customized copy: the plan&#39;s monthly new-template limit). |  -  |
| **404** | No such built-in template. |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="settemplatedefaults"></a>
# **SetTemplateDefaults**
> SetTemplateDefaults200Response SetTemplateDefaults (Guid id, SetTemplateDefaultsRequest setTemplateDefaultsRequest)

Set what a document made from a template starts with

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class SetTemplateDefaultsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var id = 6f1c1f0e-7a0c-4d1d-9b5e-2f0a7b1c3d4e;  // Guid | 
            var setTemplateDefaultsRequest = new SetTemplateDefaultsRequest(); // SetTemplateDefaultsRequest | 

            try
            {
                // Set what a document made from a template starts with
                SetTemplateDefaults200Response result = apiInstance.SetTemplateDefaults(id, setTemplateDefaultsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.SetTemplateDefaults: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetTemplateDefaultsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set what a document made from a template starts with
    ApiResponse<SetTemplateDefaults200Response> response = apiInstance.SetTemplateDefaultsWithHttpInfo(id, setTemplateDefaultsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.SetTemplateDefaultsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **setTemplateDefaultsRequest** | [**SetTemplateDefaultsRequest**](SetTemplateDefaultsRequest.md) |  |  |

### Return type

[**SetTemplateDefaults200Response**](SetTemplateDefaults200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Saved. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="usetemplate"></a>
# **UseTemplate**
> DocumentMade UseTemplate (Guid id, string idempotencyKey, UseTemplateRequest useTemplateRequest)

Use a written template for people

Makes a document from a template made with `POST /api/v1/templates/source`: the people, the template's questions answered in `variableValues` (see `GET /api/v1/templates/{id}`), the template's own defaults first. A draft unless `sendNow`. Needs an `Idempotency-Key`.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class UseTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new TemplatesApi(config);
            var id = 6f1c1f0e-7a0c-4d1d-9b5e-2f0a7b1c3d4e;  // Guid | 
            var idempotencyKey = "idempotencyKey_example";  // string | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice.
            var useTemplateRequest = new UseTemplateRequest(); // UseTemplateRequest | 

            try
            {
                // Use a written template for people
                DocumentMade result = apiInstance.UseTemplate(id, idempotencyKey, useTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TemplatesApi.UseTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UseTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Use a written template for people
    ApiResponse<DocumentMade> response = apiInstance.UseTemplateWithHttpInfo(id, idempotencyKey, useTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TemplatesApi.UseTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **idempotencyKey** | **string** | A unique value for this request (8–200 characters, for example a UUID). Repeating the request with the same key and body returns the first answer instead of doing it twice. |  |
| **useTemplateRequest** | [**UseTemplateRequest**](UseTemplateRequest.md) |  |  |

### Return type

[**DocumentMade**](DocumentMade.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The document. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


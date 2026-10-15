# Docustay.Api.Api.EmailApi

All URIs are relative to *https://app.docustay.app*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListEmailTemplates**](EmailApi.md#listemailtemplates) | **GET** /api/v1/email-templates | The workspace&#39;s email wording |
| [**ListEmails**](EmailApi.md#listemails) | **GET** /api/v1/emails | The log of email about your documents |
| [**PreviewEmailTemplate**](EmailApi.md#previewemailtemplate) | **POST** /api/v1/email-templates/{kind}/preview | Preview an email with made-up names |
| [**ResetEmailTemplate**](EmailApi.md#resetemailtemplate) | **DELETE** /api/v1/email-templates/{kind} | Back to the standard wording |
| [**SaveEmailTemplate**](EmailApi.md#saveemailtemplate) | **PUT** /api/v1/email-templates/{kind} | Set the wording of one email |

<a id="listemailtemplates"></a>
# **ListEmailTemplates**
> ListEmailTemplates200Response ListEmailTemplates (string? locale = null)

The workspace's email wording

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ListEmailTemplatesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmailApi(config);
            var locale = "locale_example";  // string? |  (optional) 

            try
            {
                // The workspace's email wording
                ListEmailTemplates200Response result = apiInstance.ListEmailTemplates(locale);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmailApi.ListEmailTemplates: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListEmailTemplatesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // The workspace's email wording
    ApiResponse<ListEmailTemplates200Response> response = apiInstance.ListEmailTemplatesWithHttpInfo(locale);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmailApi.ListEmailTemplatesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **locale** | **string?** |  | [optional]  |

### Return type

[**ListEmailTemplates200Response**](ListEmailTemplates200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The eight message types with the standard and the saved wording. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

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

<a id="previewemailtemplate"></a>
# **PreviewEmailTemplate**
> Dictionary&lt;string, Object&gt; PreviewEmailTemplate (string kind, EmailWording? emailWording = null)

Preview an email with made-up names

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class PreviewEmailTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmailApi(config);
            var kind = invitation;  // string | invitation, reminder, completed, declined, voided, expired, code or receipt
            var emailWording = new EmailWording?(); // EmailWording? |  (optional) 

            try
            {
                // Preview an email with made-up names
                Dictionary<string, Object> result = apiInstance.PreviewEmailTemplate(kind, emailWording);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmailApi.PreviewEmailTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the PreviewEmailTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Preview an email with made-up names
    ApiResponse<Dictionary<string, Object>> response = apiInstance.PreviewEmailTemplateWithHttpInfo(kind, emailWording);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmailApi.PreviewEmailTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **kind** | **string** | invitation, reminder, completed, declined, voided, expired, code or receipt |  |
| **emailWording** | [**EmailWording?**](EmailWording?.md) |  | [optional]  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Subject, preview line, body and the HTML. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="resetemailtemplate"></a>
# **ResetEmailTemplate**
> Dictionary&lt;string, Object&gt; ResetEmailTemplate (string kind, string? locale = null)

Back to the standard wording

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class ResetEmailTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmailApi(config);
            var kind = invitation;  // string | invitation, reminder, completed, declined, voided, expired, code or receipt
            var locale = "locale_example";  // string? |  (optional) 

            try
            {
                // Back to the standard wording
                Dictionary<string, Object> result = apiInstance.ResetEmailTemplate(kind, locale);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmailApi.ResetEmailTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ResetEmailTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Back to the standard wording
    ApiResponse<Dictionary<string, Object>> response = apiInstance.ResetEmailTemplateWithHttpInfo(kind, locale);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmailApi.ResetEmailTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **kind** | **string** | invitation, reminder, completed, declined, voided, expired, code or receipt |  |
| **locale** | **string?** |  | [optional]  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The standard wording again. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="saveemailtemplate"></a>
# **SaveEmailTemplate**
> Dictionary&lt;string, Object&gt; SaveEmailTemplate (string kind, EmailWording emailWording)

Set the wording of one email

Variables look like `{{document.title}}`; each message type accepts only its own (see GET). A blank field means the standard wording.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Docustay.Api.Api;
using Docustay.Api.Client;
using Docustay.Api.Model;

namespace Example
{
    public class SaveEmailTemplateExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://app.docustay.app";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            var apiInstance = new EmailApi(config);
            var kind = invitation;  // string | invitation, reminder, completed, declined, voided, expired, code or receipt
            var emailWording = new EmailWording(); // EmailWording | 

            try
            {
                // Set the wording of one email
                Dictionary<string, Object> result = apiInstance.SaveEmailTemplate(kind, emailWording);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EmailApi.SaveEmailTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SaveEmailTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set the wording of one email
    ApiResponse<Dictionary<string, Object>> response = apiInstance.SaveEmailTemplateWithHttpInfo(kind, emailWording);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EmailApi.SaveEmailTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **kind** | **string** | invitation, reminder, completed, declined, voided, expired, code or receipt |  |
| **emailWording** | [**EmailWording**](EmailWording.md) |  |  |

### Return type

**Dictionary<string, Object>**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The saved wording. |  * Docustay-Version -  <br>  * RateLimit-Limit -  <br>  * RateLimit-Remaining -  <br>  * RateLimit-Reset -  <br>  |
| **400** | The request is not valid. &#x60;message&#x60; says which field and why. |  -  |
| **401** | The key is missing, wrong, revoked, or lacks the scope. Every credential failure gets this same answer. |  -  |
| **403** | The key is valid but not allowed to do this (a plan limit, or the action is not permitted for keys). |  -  |
| **404** | Not found: nothing with that id or name in this workspace (something in another workspace answers exactly the same). |  -  |
| **429** | Too many requests. Wait &#x60;Retry-After&#x60; seconds, then try again. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


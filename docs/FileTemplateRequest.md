# Docustay.Api.Model.FileTemplateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Name** | **string** |  | 
**FileName** | **string** |  | 
**File** | **string** | The file, base64-encoded: a PDF file with text tags written in it. | 
**Fields** | **string** | &#x60;tags&#x60; (default) places fields only where a text tag is written. &#x60;auto&#x60; also looks at the page itself — lines, boxes, tick boxes, highlighted bars and the words beside them — and places the fields it is confident about, with the people grouped into seats. | [optional] 
**MinConfidence** | **decimal** | With &#x60;fields: auto&#x60;: the least sure a field may be and still be placed (default 0.6). | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


# Docustay.Api.Model.HtmlTemplateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Name** | **string** |  | 
**Html** | **string** | HTML with text tags such as {{Tenant signature;type&#x3D;signature;role&#x3D;Tenant}}. Scripts, styles, frames, forms and remote addresses are removed; pictures must be data: addresses. Up to 2 MB. | 
**Paper** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


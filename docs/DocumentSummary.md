# Docustay.Api.Model.DocumentSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | 
**Test** | **bool** | True for a document made in test mode (a test API key or the workspace&#39;s test switch). | 
**Id** | **Guid** |  | 
**Title** | **string** |  | 
**State** | **string** |  | 
**Parties** | **int** |  | 
**CreatedAt** | **string** |  | 
**SentAt** | **string** |  | 
**ExecutedAt** | **string** |  | 
**ExpiresAt** | **string** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


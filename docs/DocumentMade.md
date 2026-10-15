# Docustay.Api.Model.DocumentMade

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Approval** | [**SendDraft202ResponseApproval**](SendDraft202ResponseApproval.md) |  | [optional] 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**Id** | **Guid** |  | 
**State** | **string** |  | 
**Roles** | [**List&lt;TemplateSeatsInner&gt;**](TemplateSeatsInner.md) |  | [optional] 
**Emailed** | **int** |  | [optional] 
**NotEmailed** | **List&lt;Object&gt;** |  | [optional] 
**Warnings** | **List&lt;Object&gt;** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


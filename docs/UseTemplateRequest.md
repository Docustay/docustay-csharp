# Docustay.Api.Model.UseTemplateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Email** | [**EmailChoice**](EmailChoice.md) |  | [optional] 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Title** | **string** |  | [optional] 
**People** | [**List&lt;Person&gt;**](Person.md) |  | 
**VariableValues** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**Facts** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**Send** | [**SendChoices**](SendChoices.md) |  | [optional] 
**SendNow** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


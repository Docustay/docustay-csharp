# Docustay.Api.Model.SendDocument201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**State** | **string** |  | 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**Emailed** | **int** | How many signing emails went out now. | 
**NotEmailed** | [**List&lt;SendDocument201ResponseNotEmailedInner&gt;**](SendDocument201ResponseNotEmailedInner.md) | Anyone who was NOT emailed, and why (for example &#x60;limit_reached&#x60;: the daily email limit). The document is still sent; fetch their link or send a reminder later. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


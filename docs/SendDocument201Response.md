# Docustay.Api.Model.SendDocument201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**State** | **string** |  | 
**Emailed** | **int** | How many signing emails went out now. | 
**NotEmailed** | [**List&lt;SendDocument201ResponseNotEmailedInner&gt;**](SendDocument201ResponseNotEmailedInner.md) | Anyone who was NOT emailed, and why (for example &#x60;limit_reached&#x60;: the daily email limit). The document is still sent; fetch their link or send a reminder later. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


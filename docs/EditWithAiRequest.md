# Docustay.Api.Model.EditWithAiRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Request** | **string** |  | 
**Source** | **Dictionary&lt;string, Object&gt;** | A written document: TipTap JSON &#x60;{type:\&quot;doc\&quot;,content:[…]}&#x60;. Field tags (&#x60;fieldTag&#x60; with name, type, role, required, autofill, editable, placeholder, tooltip, locked, options, default…), merge chips (&#x60;variableChip&#x60;; &#x60;custom.&lt;key&gt;&#x60; chips are the template&#39;s questions), and headings with &#x60;audience: \&quot;sender\&quot;&#x60; (Sender only: in nothing a signer sees, signs or receives). | 
**Mode** | **string** |  | [optional] 
**Variables** | [**List&lt;EditWithAiRequestVariablesInner&gt;**](EditWithAiRequestVariablesInner.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


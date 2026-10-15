# Docustay.Api.Model.CheckDocumentRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Source** | **Dictionary&lt;string, Object&gt;** | A written document: TipTap JSON &#x60;{type:\&quot;doc\&quot;,content:[…]}&#x60;. Field tags (&#x60;fieldTag&#x60; with name, type, role, required, autofill, editable, placeholder, tooltip, locked, options, default…), merge chips (&#x60;variableChip&#x60;; &#x60;custom.&lt;key&gt;&#x60; chips are the template&#39;s questions), and headings with &#x60;audience: \&quot;sender\&quot;&#x60; (Sender only: in nothing a signer sees, signs or receives). | 
**Facts** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**People** | [**List&lt;Person&gt;**](Person.md) | With people, each person&#39;s own merge text is known, as when the document is made. | [optional] 
**VariableValues** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**RequireSignature** | **bool** |  | [optional] 
**ForTemplate** | **bool** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


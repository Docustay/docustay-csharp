# Docustay.Api.Model.CreateTemplateFromSourceRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Name** | **string** |  | 
**Source** | **Dictionary&lt;string, Object&gt;** | The document source: a ProseMirror/TipTap JSON document (&#x60;{type:\&quot;doc\&quot;,content:[…]}&#x60;) using headings, paragraphs, lists, tables, &#x60;fieldTag&#x60;, &#x60;signatureBlock&#x60;, &#x60;variableChip&#x60;. See the guide on document sources. | 
**Profile** | **string** |  | [optional] 
**Paper** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


# Docustay.Api.Model.CreateDocumentRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Email** | [**EmailChoice**](EmailChoice.md) |  | [optional] 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Title** | **string** |  | 
**Source** | **Dictionary&lt;string, Object&gt;** | A written document: TipTap JSON &#x60;{type:\&quot;doc\&quot;,content:[…]}&#x60;. Field tags (&#x60;fieldTag&#x60; with name, type, role, required, autofill, editable, placeholder, tooltip, locked, options, default…), merge chips (&#x60;variableChip&#x60;; &#x60;custom.&lt;key&gt;&#x60; chips are the template&#39;s questions), and headings with &#x60;audience: \&quot;sender\&quot;&#x60; (Sender only: in nothing a signer sees, signs or receives). | 
**People** | [**List&lt;Person&gt;**](Person.md) |  | 
**Facts** | **Dictionary&lt;string, string&gt;** | Merge text: &#x60;org.name&#x60;, &#x60;sender.name&#x60;, &#x60;custom.&lt;key&gt;&#x60; … | [optional] 
**VariableValues** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**Paper** | **string** |  | [optional] 
**Send** | [**SendChoices**](SendChoices.md) |  | [optional] 
**Description** | **string** |  | [optional] 
**SendNow** | **bool** | Also send it. The same checks as the screen&#39;s Send apply (a payment field needs Stripe connected). | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


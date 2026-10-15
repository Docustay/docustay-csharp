# Docustay.Api.Model.Document

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | 
**Test** | **bool** |  | 
**Id** | **Guid** |  | 
**Title** | **string** |  | 
**State** | **string** |  | 
**SentAt** | **string** |  | 
**ExpiresAt** | **string** |  | 
**ExecutedAt** | **string** |  | 
**VoidedAt** | **string** |  | 
**VoidReason** | **string** |  | 
**Progress** | [**DocumentProgress**](DocumentProgress.md) |  | 
**SignedCopyAvailable** | **bool** |  | 
**Parties** | [**List&lt;Party&gt;**](Party.md) |  | 
**Payments** | [**List&lt;Payment&gt;**](Payment.md) | Payments made through payment fields on this document (empty when it has none). A payment field&#39;s amount is set by ONE of: a fixed amount, a formula over the signer&#39;s own fields, a Stripe price, or a Stripe payment link — see the text tag settings &#x60;amount&#x60;, &#x60;formula&#x60;, &#x60;price&#x60; and &#x60;link&#x60;. | 
**Events** | [**List&lt;DocumentEventsInner&gt;**](DocumentEventsInner.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


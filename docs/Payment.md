# Docustay.Api.Model.Payment

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**FieldId** | **string** |  | 
**Person** | **string** |  | 
**Status** | **string** | &#x60;paid&#x60; once Stripe says so. A refund moves it to &#x60;partially_refunded&#x60; or &#x60;refunded&#x60;. | 
**AmountMinor** | **int** | What was charged, in the smallest unit of &#x60;currency&#x60; (cents). Worked out on the server; never taken from the browser. | 
**Currency** | **string** |  | 
**PaidAt** | **string** |  | 
**ReceiptUrl** | **string** | Stripe&#39;s own receipt for the payment. | 
**RefundedMinor** | **int** |  | 
**Fee** | [**PaymentFee**](PaymentFee.md) |  | 
**Test** | **bool** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


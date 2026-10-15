# Docustay.Api.Model.PaymentFee
Docustay's platform fee on this payment, on top of Stripe's own fees (which Stripe charges to your own Stripe account).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**BasisPoints** | **int** | Docustay&#39;s fee, decided when the payment started: 200 (2%) on the Free plan, 0 on Pro. | 
**AmountMinor** | **int** |  | 
**RefundedMinor** | **int** | How much of the fee went back with refunds. | 
**Plan** | **string** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


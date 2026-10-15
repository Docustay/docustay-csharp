# Docustay.Api.Model.DetectedField

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Type** | **string** |  | 
**Page** | **int** |  | 
**X** | **decimal** |  | 
**Y** | **decimal** |  | 
**W** | **decimal** |  | 
**H** | **decimal** |  | 
**Confidence** | **decimal** |  | 
**Source** | **string** | &#x60;native&#x60; (already a form field), &#x60;line&#x60;, &#x60;text&#x60;, &#x60;box&#x60;, &#x60;table&#x60;, &#x60;checkbox&#x60; or &#x60;highlight&#x60;. | 
**Label** | **string** |  | [optional] 
**Role** | **string** | The seat this field belongs to: one of &#x60;signers[].key&#x60;. | [optional] 
**Sensitive** | **bool** |  | [optional] 
**Format** | **string** |  | [optional] 
**Group** | **string** | Tick boxes that answer one question share a group: pick one. | [optional] 
**Uncertain** | **bool** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


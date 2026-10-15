# Docustay.Api.Model.Person

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ExternalId** | **string** | Your own id for this thing, so you can match it to your records. Filter lists with &#x60;externalId&#x3D;&#x60;. | [optional] 
**Metadata** | **Dictionary&lt;string, string&gt;** | Your own key-value text (up to 20 keys; keys 1–40 letters, digits, dot, dash or underscore; values up to 500 characters). Returned in every response and every webhook for this document; never shown to a signer. | [optional] 
**Name** | **string** |  | 
**Email** | **string** |  | 
**Role** | **string** | The role word in the text (Client, Provider). Left out, people take the roles in the order they appear. | [optional] 
**Action** | **string** |  | [optional] 
**Order** | **int** | Signing order when signingOrder is sequential. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


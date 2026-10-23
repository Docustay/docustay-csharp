# Docustay.Api.Model.UsageBilling
Usage that costs money on Pay as you go, Pro and Lifetime: what has been billed per unit this month, the monthly budget (default $50), and whether sending is paused at 100% of it. Amounts are whole cents.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PerDocumentMinor** | **int?** |  | 
**PerDraftMinor** | **int?** |  | 
**BillableDocuments** | **int** |  | 
**BillableDrafts** | **int** |  | 
**UnbilledMinor** | **int** |  | 
**BudgetMinor** | **int** |  | 
**PercentOfBudget** | **int** |  | 
**Paused** | **bool** |  | 
**Currency** | **string** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


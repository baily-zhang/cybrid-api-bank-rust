# PostDepositBankAccount

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The account type. To generate deposit bank accounts with their own unique account number set this to \"main\". To generate deposit bank accounts with the same account number as the parent deposit bank account set this to \"sub_account\". This setting will only generate a unique identifier for the deposit bank and will not result in a unique account number being generated. \"sub_account\" is only  available for customer-level deposit bank accounts. (enum: main, sub_account) | 
**account_guid** | **String** | The fiat or reserve account guid. | 
**customer_guid** | Option<**String**> | The unique identifier for the customer. | [optional]
**parent_deposit_bank_account_guid** | Option<**String**> | The unique identifier for the bank-level deposit bank account. This is only required for sub-accounts. Required when type is sub_account. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the bank account. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



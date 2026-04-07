# AccountAssociation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | **String** | Auto-generated unique identifier for the transfer account. | 
**r#type** | **String** | The type of transfer account; one of trading, fiat, external_bank_account, or external_wallet. | 
**organization_guid** | Option<**String**> | The account's organization identifier. | [optional]
**bank_guid** | Option<**String**> | The account's bank identifier. | [optional]
**customer_guid** | Option<**String**> | The account's customer identifier. | [optional]
**counterparty_guid** | Option<**String**> | The account's counterparty identifier. | [optional]
**asset** | **String** | The account asset, e.g., USD. | 
**requested_amount** | Option<**i32**> | The requested amount in base units intended to transfer from or to the account. | [optional]
**quoted_amount** | Option<**i32**> | The quoted amount in base units to transfer from or to the account. | [optional]
**executed_amount** | Option<**i32**> | The executed amount in base units transferred from or to the account. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



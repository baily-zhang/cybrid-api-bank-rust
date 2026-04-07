# DepositBankAccount

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the identity verification. | [optional]
**r#type** | Option<**String**> | The account type; one of main or sub_account. | [optional]
**bank_guid** | Option<**String**> | The address' bank identifier. | [optional]
**customer_guid** | Option<**String**> | The address' customer identifier. | [optional]
**account_guid** | Option<**String**> | The address' account identifier. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**deleted_at** | Option<**String**> | ISO8601 datetime the record was last deleted at. | [optional]
**asset** | Option<**String**> | The asset the transfer is related to, e.g., USD. | [optional]
**state** | Option<**String**> | The state of the address; one of storing or created. | [optional]
**unique_memo_id** | Option<**String**> | The unique memo identifier for the address. This is used to identify the recipient when sending funds to the account. This value MUST be included in all wire transfers to this account. | [optional]
**counterparty_name** | Option<**String**> | The name of the account holder. | [optional]
**counterparty_address** | Option<[**models::DepositBankAccountCounterpartyAddress**](DepositBankAccountCounterpartyAddress.md)> |  | [optional]
**account_details** | Option<[**Vec<models::DepositBankAccountAccountDetailsInner>**](DepositBankAccountAccountDetailsInner.md)> | The account details for the bank account. | [optional]
**routing_details** | Option<[**Vec<models::DepositBankAccountRoutingDetailsInner>**](DepositBankAccountRoutingDetailsInner.md)> | The account details for the bank account. | [optional]
**parent_deposit_bank_account_guid** | Option<**String**> | The unique identifier for the bank-level deposit bank account. This is only set for sub-accounts. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the address. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



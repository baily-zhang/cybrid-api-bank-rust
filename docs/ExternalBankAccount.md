# ExternalBankAccount

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the account. | [optional]
**name** | Option<**String**> | The name of the account. | [optional]
**asset** | Option<**String**> | The asset code. | [optional]
**account_kind** | Option<**String**> | The type of account; one of plaid, plaid_processor_token, or raw_routing_details. | [optional]
**environment** | Option<**String**> | The environment that the external bank account is operating in; one of sandbox or production. | [optional]
**bank_guid** | Option<**String**> | The bank identifier. | [optional]
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**counterparty_guid** | Option<**String**> | The counterparty identifier. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**plaid_institution_id** | Option<**String**> | The Plaid institution ID for the account. | [optional]
**plaid_account_mask** | Option<**String**> | The account number mask for the account. | [optional]
**plaid_account_name** | Option<**String**> | The name for the account. | [optional]
**state** | Option<**String**> | The state of the external bank account; one of storing, completed, failed, refresh_required, unverified, deleting, or deleted. | [optional]
**failure_code** | Option<**String**> | The failure code for failed transfers. | [optional]
**balance_updated_at** | Option<**String**> | The timestamp that the balance information was last updated at. | [optional]
**balances** | Option<[**models::ExternalBankAccountBalances**](ExternalBankAccountBalances.md)> |  | [optional]
**pii** | Option<[**Vec<models::ExternalBankAccountPiiInner>**](ExternalBankAccountPiiInner.md)> | The account holder information. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



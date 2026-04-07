# PostExternalBankAccount

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **String** | The name of the account. | 
**account_kind** | **AccountKind** | The account type (enum: plaid, plaid_processor_token, raw_routing_details) | 
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**asset** | Option<**String**> | The asset code. If not set will try and default to the Bank's configured fiat asset. | [optional]
**plaid_public_token** | Option<**String**> | The public token for the account. Required for 'plaid' accounts. Required when account_kind is plaid. | [optional]
**plaid_account_id** | Option<**String**> | The account identifier in plaid. Required for 'plaid' accounts. Required when account_kind is plaid. | [optional]
**plaid_processor_token** | Option<**String**> | The Plaid processor token used to access the account. Required when account_kind is plaid_processor_token. | [optional]
**plaid_institution_id** | Option<**String**> | Plaid's institution ID for the account's institution. Required when account_kind is plaid_processor_token. | [optional]
**plaid_account_mask** | Option<**String**> | The account mask for the account. Required when account_kind is plaid_processor_token. | [optional]
**plaid_account_name** | Option<**String**> | The name of the account. Required when account_kind is plaid_processor_token. | [optional]
**counterparty_guid** | Option<**String**> | The counterparty identifier. Optional when account_kind is raw_routing_details. | [optional]
**counterparty_bank_account** | Option<[**models::PostExternalBankAccountCounterpartyBankAccount**](PostExternalBankAccountCounterpartyBankAccount.md)> |  | [optional]
**counterparty_name** | Option<[**models::PostExternalBankAccountCounterpartyName**](PostExternalBankAccountCounterpartyName.md)> |  | [optional]
**counterparty_address** | Option<[**models::PostExternalBankAccountCounterpartyAddress**](PostExternalBankAccountCounterpartyAddress.md)> |  | [optional]
**counterparty_email_address** | Option<**String**> | The counterparty's email address on their checking account. Optional when account_kind is raw_routing_details and counterparty_guid is not present. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



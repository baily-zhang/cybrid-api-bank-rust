# PaymentInstruction

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the payment instruction. | [optional]
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**invoice_guid** | Option<**String**> | The invoice identifier. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**expired_at** | Option<**String**> | ISO8601 datetime the instructions expired at. | [optional]
**failed_at** | Option<**String**> | ISO8601 datetime the instructions failed to be created at. | [optional]
**network_address** | Option<**String**> | The network address to pay the invoice to. | [optional]
**expected_payment_asset** | Option<**String**> | The asset the payor must pay the invoice in, e.g., BTC. | [optional]
**expected_payment_amount** | Option<**i32**> | The amount to be paid in base units of expected_payment_asset. | [optional]
**failure_code** | Option<**String**> | The reason code explaining the failure; ond of invoice_paid, invoice_cancelled, or invalid_amount. | [optional]
**state** | Option<**String**> | The state of the payment instruction; one of storing, created, expired, or failed. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



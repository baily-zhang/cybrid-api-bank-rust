# Invoice

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the payment instruction. | [optional]
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**account_guid** | Option<**String**> | The account payment will ultimately be received into. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**r#type** | Option<**String**> | The type of invoice; one of lightning. | [optional]
**asset** | Option<**String**> | The asset code the customer will receive the funds in. | [optional]
**receive_amount** | Option<**i32**> | The amount to be received in base units of the asset, i.e., the amount the customer will receive after fees. ONLY one of receive_amount or deliver_amount is required. | [optional]
**deliver_amount** | Option<**i32**> | The amount to be delivered in base units of the asset, i.e., the amount the customer will receive before fees. ONLY one of receive_amount or deliver_amount is required. | [optional]
**fee** | Option<**i32**> | The fee associated with this invoice in base units of the asset. | [optional]
**state** | Option<**String**> | The state of the invoice; one of storing, unpaid, cancelling, cancelled, settling, or paid. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the invoice. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



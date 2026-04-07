# Account

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | Option<**String**> | The account type; one of trading, fee, fiat, gas, reserve, invoice_operations, or storage. | [optional]
**guid** | Option<**String**> | Auto-generated unique identifier for the account. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**asset** | Option<**String**> | The asset code. | [optional]
**name** | Option<**String**> | The name of the account. | [optional]
**bank_guid** | Option<**String**> | The bank identifier associated with the account. | [optional]
**customer_guid** | Option<**String**> | The customer identifier associated with the account. | [optional]
**platform_balance** | Option<**i32**> | The amount of funds that are in the account, in base units of the asset. | [optional]
**platform_available** | Option<**i32**> | The amount of funds that are in the account, in base units of the asset, that are available for use on the platform. | [optional]
**state** | Option<**String**> | The state of the account; one of storing or created. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the account. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



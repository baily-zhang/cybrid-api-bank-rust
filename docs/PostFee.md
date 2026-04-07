# PostFee

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The fee's type (enum: spread, fixed) | 
**spread_fee** | Option<**i32**> | The percentage amount, in basis points, to apply when charging a fee. Required when type is spread. | [optional]
**fixed_fee** | Option<**i32**> | The fixed amount to apply when charging a fee; for trades, the fiat asset is used. Required when type is fixed. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



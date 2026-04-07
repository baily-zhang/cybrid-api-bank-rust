# ActivityLimit

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | Option<**String**> | The type of the limit; one of rolling, daily, weekly, or monthly. | [optional]
**name** | Option<**String**> | The name of the limit. | [optional]
**asset** | Option<**String**> | The asset code for the limit. | [optional]
**amount** | Option<**i32**> | The limit amount for the asset. | [optional]
**interval** | Option<**i32**> | The limit interval in seconds for the asset. | [optional]
**activities** | Option<**Vec<String>**> | The activities associated with the limit. | [optional]
**sides** | Option<**Vec<String>**> | The sides associated with the limit. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# PatchBank

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | Option<**String**> | The name of the bank. | [optional]
**supported_trading_symbols** | Option<**Vec<String>**> | The trading symbols supported by the bank. | [optional]
**supported_payout_symbols** | Option<[**Vec<models::PostSupportedPayoutSymbols>**](PostSupportedPayoutSymbols.md)> | The payout symbols supported by the bank. This is not yet supported and should be nil or empty. | [optional]
**cors_allowed_origins** | Option<**Vec<String>**> | The list of allowed CORS origin URIs. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



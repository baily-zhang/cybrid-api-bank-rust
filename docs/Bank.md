# Bank

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | **String** | Auto-generated unique identifier for the bank. | 
**organization_guid** | **String** | The organization's identifier. | 
**name** | **String** | The bank's name. | 
**r#type** | **String** | The bank type; one of sandbox or production. | 
**supported_trading_symbols** | Option<**Vec<String>**> | The bank's list of supported trading symbols. | [optional]
**supported_payout_symbols** | Option<[**Vec<models::BankSupportedPayoutSymbolsInner>**](BankSupportedPayoutSymbolsInner.md)> | The bank's list of supported payout symbols. | [optional]
**supported_fiat_account_assets** | Option<**Vec<String>**> | The bank's list of supported fiat symbols. | [optional]
**supported_country_codes** | Option<**Vec<String>**> | The bank's list of supported country codes. | [optional]
**features** | **Vec<String>** | The bank's enabled features. | 
**cors_allowed_origins** | Option<**Vec<String>**> | The bank's list of CORS allowed origins. | [optional]
**created_at** | **String** | ISO8601 datetime the record was created at. | 
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



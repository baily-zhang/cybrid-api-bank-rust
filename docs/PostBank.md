# PostBank

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The type of bank. (enum: sandbox) | 
**name** | **String** | The name of the bank. | 
**supported_trading_symbols** | **Vec<String>** | The trading symbols supported by the bank. | 
**supported_payout_symbols** | Option<[**Vec<models::PostSupportedPayoutSymbols>**](PostSupportedPayoutSymbols.md)> | The payout symbols supported by the bank. This is not yet supported and should be nil or empty. | [optional]
**supported_fiat_account_assets** | **Vec<String>** | The fiat account assets supported by the bank. | 
**supported_country_codes** | **Vec<String>** | The country codes supported by the bank. | 
**features** | **Vec<Features>** | The features supported by the bank. (enum: attestation_identity_records, attestation_identity_records_v2, attestation_identity_records_v3, kyc_identity_verifications, business_customers, individual_customers) | 
**cors_allowed_origins** | Option<**Vec<String>**> | The list of allowed CORS origin URIs. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



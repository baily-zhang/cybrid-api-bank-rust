# PostTrade

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**trade_type** | Option<**TradeType**> | The type of trade. (enum: platform) | [optional][default to Platform]
**quote_guid** | **String** | The associated quote's identifier. | 
**fiat_account_guid** | Option<**String**> | The identifier for the fiat account to use for the trade. Required if the customer or bank has multiple fiat accounts. | [optional]
**expected_error** | Option<**ExpectedError**> | The optional expected error to simulate trade failure. (enum: expired_quote, non_sufficient_funds) | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the trade. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



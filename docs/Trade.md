# Trade

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the trade. | [optional]
**trade_type** | Option<**String**> | The type of trade; one of platform, liquidation, or exit. | [optional]
**customer_guid** | Option<**String**> | The associated customer's identifier. | [optional]
**quote_guid** | Option<**String**> | The associated quote's identifier. | [optional]
**symbol** | Option<**String**> | The trade symbol the pricing is related to. Format is asset-counter_asset, e.g., BTC-USD. | [optional]
**side** | Option<**String**> | The direction of the trade; one of buy or sell. | [optional]
**state** | Option<**String**> | The state of the trade; one of storing, pending, cancelled, completed, settling, or failed. | [optional]
**failure_code** | Option<**String**> | The failure code for failed trades; one of non_sufficient_funds, unsupported, limit_exceeded, expired_quote, market_volatility, or not_filled. | [optional]
**receive_amount** | Option<**i32**> | The amount to be received in base units of the currency: currency is \"asset\" for buy and \"counter_asset\" for sell. | [optional]
**deliver_amount** | Option<**i32**> | The amount to be delivered in base units of the currency: currency is \"counter_asset\" for buy and \"asset\" for sell. | [optional]
**fee** | Option<**i32**> | The fee associated with the trade. Denominated in \"counter_asset\" base units. Represents the sum of the bank and platform fees. | [optional]
**fee_details** | Option<[**Vec<models::FeeDetail>**](FeeDetail.md)> | The fees associated with the trade. | [optional]
**reference_trade_guid** | Option<**String**> | The guid of the related trade. Only present on `exit` trades. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the trade. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



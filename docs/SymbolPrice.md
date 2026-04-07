# SymbolPrice

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**symbol** | Option<**String**> | The trade symbol the pricing is related to. Format is asset-counter_asset, e.g., BTC-USD. | [optional]
**r#type** | Option<**String**> | The type of price; one of trading or payout. | [optional]
**buy_price** | Option<**i32**> | The purchase price (in base units) for the asset denominated in the counter asset currency. | [optional]
**sell_price** | Option<**i32**> | The sale price (in base units) for the asset denominated in the counter asset currency. | [optional]
**buy_price_last_updated_at** | Option<**String**> | ISO8601 datetime the purchase price was generated at. | [optional]
**sell_price_last_updated_at** | Option<**String**> | ISO8601 datetime the sale price was generated at. | [optional]
**country_code** | Option<**String**> | The ISO 3166 country 2-Alpha country code of the price. | [optional]
**participants_type** | Option<**String**> | The type of participants the price is for; one of C2C, C2B, B2C, or B2B. | [optional]
**route** | Option<**String**> | The route the price is for; one of bank_account or mobile_wallet. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



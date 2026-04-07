# Quote

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the quote. | [optional]
**product_type** | Option<**String**> | The type of product the quote is for; one of trading, trading_exit, funding, crypto_transfer, inter_account, or lightning_transfer. | [optional]
**bank_guid** | Option<**String**> | The unique identifier for the bank. | [optional]
**customer_guid** | Option<**String**> | The unique identifier for the customer. | [optional]
**symbol** | Option<**String**> | Symbol the quote was requested for. Format is \"asset-counter_asset\" in uppercase. Populated for trade quotes. | [optional]
**side** | Option<**String**> | The direction of the quote; one of buy, sell, deposit, or withdrawal. | [optional]
**receive_amount** | Option<**i32**> | The amount to be received in base units of the currency: currency is \"asset\" for buy and \"counter_asset\" for sell for trade quotes. | [optional]
**deliver_amount** | Option<**i32**> | The amount to be delivered in base units of the currency: currency is \"counter_asset\" for buy and \"asset\" for sell for trade quotes. | [optional]
**fee** | Option<**i32**> | The fee associated with the trade. Denominated in \"counter_asset\" base units for trade quotes. | [optional]
**fee_details** | Option<[**Vec<models::FeeDetail>**](FeeDetail.md)> | The fees associated with the quote. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**issued_at** | Option<**String**> | ISO8601 datetime the quote was created at. | [optional]
**expires_at** | Option<**String**> | ISO8601 datetime the quote is expiring at. Populated for trading quotes. | [optional]
**asset** | Option<**String**> | The asset code the quote was requested for. Populated for book transfer and funding quotes. | [optional]
**network_fee** | Option<**i32**> | The network fee in base units of network_fee_asset. Only present on `crypto_transfer` quotes. | [optional]
**network_fee_asset** | Option<**String**> | The asset code of the network fee. | [optional]
**network_address** | Option<**String**> | The network address to pay the invoice to. Populated for lightning_transfer quotes. | [optional]
**entries** | Option<[**Vec<models::QuoteEntry>**](QuoteEntry.md)> | The quote entries for a batch transfer quote | [optional]
**trade_guid** | Option<**String**> | The unique identifier for the trade. | [optional]
**transfer_guid** | Option<**String**> | The unique identifier for the transfer. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



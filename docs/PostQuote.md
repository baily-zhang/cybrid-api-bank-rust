# PostQuote

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**product_type** | Option<**ProductType**> | The type of product the quote is for. (enum: trading, funding, crypto_transfer, inter_account, lightning_transfer, book_transfer) | [optional][default to Trading]
**bank_guid** | Option<**String**> | The unique identifier for the bank. | [optional]
**customer_guid** | Option<**String**> | The unique identifier for the customer. | [optional]
**receive_amount** | Option<**i32**> | The amount to be received in base units of the currency: currency is \"asset\" for buy and \"counter_asset\" for sell for trade quotes. | [optional]
**deliver_amount** | Option<**i32**> | The amount to be delivered in base units of the currency: currency is \"counter_asset\" for buy and \"asset\" for sell for trade quotes. | [optional]
**asset** | Option<**String**> | The asset code the quote was requested for. Required when product_type is lightning_transfer, product_type is book_transfer, product_type is funding, product_type is crypto_transfer, or product_type is inter_account. | [optional]
**network_address** | Option<**String**> | The network address to pay the invoice to. Required when product_type is lightning_transfer. | [optional]
**fees** | Option<[**Vec<models::PostFee>**](PostFee.md)> | The custom fees associated with the quote Optional when product_type is lightning_transfer, product_type is funding, product_type is trading, product_type is crypto_transfer, or product_type is trading_exit. | [optional]
**side** | Option<**Side**> | The direction for trade quotes: either 'buy' or 'sell'. The direction for funding quotes: either 'deposit' or 'withdrawal'. The direction for crypto transfer quotes: 'withdrawal'. Book transfers do not require a side. They are all 'deposit's.  Required when product_type is funding, product_type is trading, or product_type is crypto_transfer. (enum: deposit, withdrawal, buy, sell) | [optional]
**destination_account_guid** | Option<**String**> | The unique identifier for the destination account. Used to determine routing-specific fees for EFT withdrawals. Required when product_type is inter_account. Optional when product_type is funding. | [optional]
**symbol** | Option<**String**> | Symbol the quote is being requested for. Format is \"asset-counter_asset\" in uppercase. See the Symbols API for a complete list of cryptocurrencies supported.  Required when product_type is trading. | [optional]
**destination_accounts** | Option<[**Vec<models::PostQuoteEntry>**](PostQuoteEntry.md)> | Destination accounts for batch transactions on UTXO-based blockchains. A single destination account is required for Base blockchain assets. Optional when product_type is crypto_transfer. | [optional]
**reference_trade_guid** | Option<**String**> | The guid of the related trade. Only present on `exit` trades. Required when product_type is trading_exit. | [optional]
**source_account_guid** | Option<**String**> | The source account's identifier. Required when product_type is inter_account. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



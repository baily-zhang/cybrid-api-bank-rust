# \PricesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_prices**](PricesApi.md#list_prices) | **GET** /api/prices | Get Price



## list_prices

> Vec<models::SymbolPrice> list_prices(symbol, trading_symbol, payout_symbol, payout_country_code, payout_participants_type, payout_route, bank_guid)
Get Price

Retrieves a listing of symbol prices.  ## Symbols  Symbol are pairs and are in the format asset-counter_asset, e.g., 'BTC-USD' for the Bitcoin/ USD pair. See the Symbols API for a complete list of cryptocurrencies supported.    Required scope: **prices:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**symbol** | Option<**String**> | Comma separated trading symbols to list prices for. |  |
**trading_symbol** | Option<**String**> | Comma separated trading symbols to list prices for. |  |
**payout_symbol** | Option<**String**> | Comma separated payout symbols to list prices for. |  |
**payout_country_code** | Option<**String**> | Comma separated payout country codes to list prices for. |  |
**payout_participants_type** | Option<**String**> | Comma separated payout participants types to list prices for. |  |
**payout_route** | Option<**String**> | Comma separated payout routes to list prices for. |  |
**bank_guid** | Option<**String**> | The bank identifier to retrieve prices for. |  |

### Return type

[**Vec<models::SymbolPrice>**](SymbolPrice.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \TradesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_trade**](TradesApi.md#create_trade) | **POST** /api/trades | Create Trade
[**get_trade**](TradesApi.md#get_trade) | **GET** /api/trades/{trade_guid} | Get Trade
[**list_trades**](TradesApi.md#list_trades) | **GET** /api/trades | Get trades list



## create_trade

> models::Trade create_trade(post_trade)
Create Trade

Creates a trade.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the trade details in our private store | | pending | The Platform has stored the trade details and is processing it | | executed | The Platform has processed the trade and needs to settle it | | settling | The Platform has executed the trade and is settling the funds | | cancelled | The Platform has cancelled the trade | | completed | The Platform has successfully completed the trade | | failed | The Platform was not able to successfully complete the trade |  ## Failure codes  | Code | Description | |------|-------------| | non_sufficient_funds | The delivery account does not have enough funds to complete the trade | | unsupported | The trading pair is not supported for this customer | | limit_exceeded | The customer is over the limits that have been set for them for this activity | | daily_limit_exceeded | The customer is over their daily limits for this activity | | weekly_limit_exceeded | The customer is over their weekly limits for this activity | | monthly_limit_exceeded | The customer is over their monthly limits for this activity | | expired_quote | The quote expired before it could be executed | | market_volatility | The quote could not be executed due to market volatility | | not_filled | The trade could not be filled based on the amounts specified |    Required scope: **trades:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_trade** | [**PostTrade**](PostTrade.md) |  | [required] |

### Return type

[**models::Trade**](Trade.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_trade

> models::Trade get_trade(trade_guid)
Get Trade

Retrieves a trade.  Required scope: **trades:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**trade_guid** | **String** | Identifier for the trade. | [required] |

### Return type

[**models::Trade**](Trade.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_trades

> models::TradeList list_trades(page, per_page, guid, bank_guid, customer_guid, account_guid, state, side, label, created_at_gte, created_at_lt, updated_at_gte, updated_at_lt)
Get trades list

Retrieves a listing of trades. Records are sorted by creation date in descending order.  Required scope: **trades:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated trade_guids to list trades for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list trades for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list trades for. |  |
**account_guid** | Option<**String**> | Comma separated account_guids to list trades for. |  |
**state** | Option<**String**> | Comma separated states to list trades for. |  |
**side** | Option<**String**> | Comma separated sides to list trades for. |  |
**label** | Option<**String**> | Comma separated labels to list trades for. |  |
**created_at_gte** | Option<**String**> | Created at start date-time inclusive lower bound, ISO8601. |  |
**created_at_lt** | Option<**String**> | Created at end date-time exclusive upper bound, ISO8601. |  |
**updated_at_gte** | Option<**String**> | Updated at start date-time inclusive lower bound, ISO8601. |  |
**updated_at_lt** | Option<**String**> | Updated at end date-time exclusive upper bound, ISO8601. |  |

### Return type

[**models::TradeList**](TradeList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


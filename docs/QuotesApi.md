# \QuotesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_quote**](QuotesApi.md#create_quote) | **POST** /api/quotes | Create Quote
[**get_quote**](QuotesApi.md#get_quote) | **GET** /api/quotes/{quote_guid} | Get Quote
[**list_quotes**](QuotesApi.md#list_quotes) | **GET** /api/quotes | Get quotes list



## create_quote

> models::Quote create_quote(post_quote)
Create Quote

Creates a quote.  ## Quote creation  Quotes can be created for a Bank or a Customer.  To create quotes for your Bank, omit the `customer_guid` parameter in the request body. To create quotes for your Customers, include the `customer_guid` parameter in the request body.  ## Failure codes  | Code | Description | |------|-------------| | invalid_amount | The amount on the invoice is unprocessable | | insufficient_balance | There are insufficient funds to process the quote | | invalid_invoice | The invoice cannot be processed |    Required scope: **quotes:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_quote** | [**PostQuote**](PostQuote.md) |  | [required] |

### Return type

[**models::Quote**](Quote.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_quote

> models::Quote get_quote(quote_guid)
Get Quote

Retrieves a quote.  Required scope: **quotes:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**quote_guid** | **String** | Identifier for the quote. | [required] |

### Return type

[**models::Quote**](Quote.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_quotes

> models::QuoteList list_quotes(page, per_page, guid, product_type, bank_guid, customer_guid, side)
Get quotes list

Retrieves a listing of quotes. Records are sorted by creation date in descending order.  Required scope: **quotes:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> |  |  |
**per_page** | Option<**i32**> |  |  |
**guid** | Option<**String**> | Comma separated quote_guids to list quotes for. |  |
**product_type** | Option<**String**> | Comma separated product_types to list accounts for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list quotes for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list quotes for. |  |
**side** | Option<**String**> | Comma separated sides to list quotes for. |  |

### Return type

[**models::QuoteList**](QuoteList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


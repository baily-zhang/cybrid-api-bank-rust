# \AccountsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_account**](AccountsApi.md#create_account) | **POST** /api/accounts | Create Account
[**get_account**](AccountsApi.md#get_account) | **GET** /api/accounts/{account_guid} | Get Account
[**list_accounts**](AccountsApi.md#list_accounts) | **GET** /api/accounts | List Accounts



## create_account

> models::Account create_account(post_account)
Create Account

Creates an account.  ## Account Type  An Account is tied to a specific cryptocurrency or fiat and is comprised of transactions and a current balance.  An account is required to allow a Bank or Customer to hold cryptocurrency or a Customer to hold fiat on the Cybrid Platform.  At present, accounts can be created as `trading`, `storage` or `fiat ` accounts and are required before a Customer can generate quotes or execute a `trade` or `transfer`.  To create accounts for your Bank, omit the `customer_guid` parameter in the request body. To create accounts for your Customers, include the `customer_guid` parameter in the request body.  At the bank level, `invoice_operations` accounts can be configured to pre-fund your customers' Lightning Network operations.  ## Asset  The asset is the specific cryptocurrency or fiat that the account holds, e.g., 'BTC' for Bitcoin or `USD` for US dollars. See the Symbols API for a complete list of cryptocurrencies and fiat supported.   ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the account details in our private store | | created | The Platform has created the account |    Required scope: **accounts:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_account** | [**PostAccount**](PostAccount.md) |  | [required] |

### Return type

[**models::Account**](Account.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_account

> models::Account get_account(account_guid)
Get Account

Retrieves an account.  Required scope: **accounts:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**account_guid** | **String** | Identifier for the account. | [required] |

### Return type

[**models::Account**](Account.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_accounts

> models::AccountList list_accounts(page, per_page, owner, guid, r#type, bank_guid, customer_guid, label)
List Accounts

Retrieves a list of accounts. Records are sorted by creation date in descending order.  Required scope: **accounts:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**owner** | Option<**String**> | The owner of the entity. |  |
**guid** | Option<**String**> | Comma separated account_guids to list accounts for. |  |
**r#type** | Option<**String**> | Comma separated account_types to list accounts for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list accounts for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list accounts for. |  |
**label** | Option<**String**> | Comma separated labels to list accounts for. |  |

### Return type

[**models::AccountList**](AccountList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


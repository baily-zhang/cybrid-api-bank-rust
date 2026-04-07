# \ExternalWalletsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_external_wallet**](ExternalWalletsApi.md#create_external_wallet) | **POST** /api/external_wallets | Create ExternalWallet
[**delete_external_wallet**](ExternalWalletsApi.md#delete_external_wallet) | **DELETE** /api/external_wallets/{external_wallet_guid} | Delete External Wallet
[**get_external_wallet**](ExternalWalletsApi.md#get_external_wallet) | **GET** /api/external_wallets/{external_wallet_guid} | Get External Wallet
[**list_external_wallets**](ExternalWalletsApi.md#list_external_wallets) | **GET** /api/external_wallets | Get external wallets list



## create_external_wallet

> models::ExternalWallet create_external_wallet(post_external_wallet)
Create ExternalWallet

Create an ExternalWallet.  ## Wallet creation  External Wallets can be created for a Bank or a Customer.  To create a wallet for your Bank, omit the `customer_guid` parameter in the request body. To create a wallet for your Customers, include the `customer_guid` parameter in the request body.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the external wallet details in our private store | | pending | The Platform is waiting for the external wallet to be created | | reviewing | The Platform is reviewing the external wallet for compliance | | completed | The Platform has created the external wallet | | failed | The Platform was not able to successfully create the external wallet | | deleting | The Platform is deleting the external wallet | | deleted | The Platform has deleted the external wallet |  ## Failure Codes  | Code | Description | |-------|-------------| | invalid_address | The provided wallet address is invalid | | prohibited_address | The provided wallet address failed screening |    External wallets can be added to the bank by leaving the customer_guid blank. External wallets added to the bank can be used by any customer of the bank.  External wallets can also be added to a specific customer by providing the customer_guid. External wallets added to a customer can only be used by that customer.  Required scope: **external_wallets:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_external_wallet** | [**PostExternalWallet**](PostExternalWallet.md) |  | [required] |

### Return type

[**models::ExternalWallet**](ExternalWallet.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_external_wallet

> models::ExternalWallet delete_external_wallet(external_wallet_guid)
Delete External Wallet

Deletes an external wallet.  Required scope: **external_wallets:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**external_wallet_guid** | **String** | Identifier for the external wallet. | [required] |

### Return type

[**models::ExternalWallet**](ExternalWallet.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_external_wallet

> models::ExternalWallet get_external_wallet(external_wallet_guid)
Get External Wallet

Retrieves an external_wallet.  Required scope: **external_wallets:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**external_wallet_guid** | **String** | Identifier for the external_wallet. | [required] |

### Return type

[**models::ExternalWallet**](ExternalWallet.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_external_wallets

> models::ExternalWalletList list_external_wallets(page, per_page, owner, guid, bank_guid, customer_guid, counterparty_guid, asset, state)
Get external wallets list

Retrieves a listing of external wallets. Records are sorted by creation date in descending order.  Required scope: **external_wallets:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**owner** | Option<**String**> | The owner of the entity. |  |
**guid** | Option<**String**> | Comma separated external_wallet_guids to list external_wallets for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list external_wallets for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list external_wallets for. |  |
**counterparty_guid** | Option<**String**> | Comma separated counterparty_guids to list external_wallets for. |  |
**asset** | Option<**String**> | Comma separated assets to list external_wallets for. |  |
**state** | Option<**String**> | Comma separated states to list external_wallets for. |  |

### Return type

[**models::ExternalWalletList**](ExternalWalletList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


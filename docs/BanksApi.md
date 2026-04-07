# \BanksApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_bank**](BanksApi.md#create_bank) | **POST** /api/banks | Create Bank
[**get_bank**](BanksApi.md#get_bank) | **GET** /api/banks/{bank_guid} | Get Bank
[**list_banks**](BanksApi.md#list_banks) | **GET** /api/banks | Get banks list
[**update_bank**](BanksApi.md#update_bank) | **PATCH** /api/banks/{bank_guid} | Patch Bank



## create_bank

> models::Bank create_bank(post_bank)
Create Bank

Creates a bank.  ## Bank Type  Bank's can be created in either `sandbox` or `production` mode. Sandbox Banks will not transact in real fiat dollars or cryptocurrencies.  Via the API, only `sandbox` banks can be created. In order to enable a `production` bank please contact [Support](mailto:support@cybrid.app).    Required scope: **banks:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_bank** | [**PostBank**](PostBank.md) |  | [required] |

### Return type

[**models::Bank**](Bank.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_bank

> models::Bank get_bank(bank_guid)
Get Bank

Retrieves a bank.  Required scope: **banks:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**bank_guid** | **String** | Identifier for the bank. | [required] |

### Return type

[**models::Bank**](Bank.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_banks

> models::BankList list_banks(page, per_page, r#type, guid)
Get banks list

Retrieves a listing of bank. Records are sorted by creation date in descending order.  Required scope: **banks:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**r#type** | Option<**String**> | Comma separated types to list banks for. |  |
**guid** | Option<**String**> | Comma separated bank_guids to list banks for. |  |

### Return type

[**models::BankList**](BankList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_bank

> models::Bank update_bank(bank_guid, patch_bank)
Patch Bank

Update a bank.  Required scope: **banks:write**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**bank_guid** | **String** | Identifier for the bank. | [required] |
**patch_bank** | [**PatchBank**](PatchBank.md) |  | [required] |

### Return type

[**models::Bank**](Bank.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


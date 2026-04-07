# \DepositAddressesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_deposit_address**](DepositAddressesApi.md#create_deposit_address) | **POST** /api/deposit_addresses | Create Deposit Address
[**get_deposit_address**](DepositAddressesApi.md#get_deposit_address) | **GET** /api/deposit_addresses/{deposit_address_guid} | Get Deposit Address
[**list_deposit_addresses**](DepositAddressesApi.md#list_deposit_addresses) | **GET** /api/deposit_addresses | List Deposit Addresses



## create_deposit_address

> models::DepositAddress create_deposit_address(post_deposit_address)
Create Deposit Address

Creates a deposit address.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the deposit address details in our private store | | created | The Platform has created the deposit address |    Required scope: **deposit_addresses:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_deposit_address** | [**PostDepositAddress**](PostDepositAddress.md) |  | [required] |

### Return type

[**models::DepositAddress**](DepositAddress.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_deposit_address

> models::DepositAddress get_deposit_address(deposit_address_guid)
Get Deposit Address

Retrieves a deposit address.  Required scope: **deposit_addresses:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**deposit_address_guid** | **String** | Identifier for the deposit address. | [required] |

### Return type

[**models::DepositAddress**](DepositAddress.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_deposit_addresses

> models::DepositAddressList list_deposit_addresses(page, per_page, guid, bank_guid, customer_guid, label)
List Deposit Addresses

Retrieves a list of deposit addresses. Records are sorted by creation date in descending order.  Required scope: **deposit_addresses:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated guids to list deposit addresses for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list deposit addresses for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list deposit addresses for. |  |
**label** | Option<**String**> | Comma separated labels to list deposit addresses for. |  |

### Return type

[**models::DepositAddressList**](DepositAddressList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


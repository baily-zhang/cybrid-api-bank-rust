# \DepositBankAccountsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_deposit_bank_account**](DepositBankAccountsApi.md#create_deposit_bank_account) | **POST** /api/deposit_bank_accounts | Create Deposit Bank Account
[**get_deposit_bank_account**](DepositBankAccountsApi.md#get_deposit_bank_account) | **GET** /api/deposit_bank_accounts/{deposit_bank_account_guid} | Get Deposit Bank Account
[**list_deposit_bank_accounts**](DepositBankAccountsApi.md#list_deposit_bank_accounts) | **GET** /api/deposit_bank_accounts | List Deposit Bank Accounts



## create_deposit_bank_account

> models::DepositBankAccount create_deposit_bank_account(post_deposit_bank_account)
Create Deposit Bank Account

Creates a deposit bank account.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the deposit bank account details in our private store | | created | The Platform has created the deposit bank account |    Required scope: **deposit_bank_accounts:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_deposit_bank_account** | [**PostDepositBankAccount**](PostDepositBankAccount.md) |  | [required] |

### Return type

[**models::DepositBankAccount**](DepositBankAccount.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_deposit_bank_account

> models::DepositBankAccount get_deposit_bank_account(deposit_bank_account_guid)
Get Deposit Bank Account

Retrieves a deposit bank account.  Required scope: **deposit_bank_accounts:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**deposit_bank_account_guid** | **String** | Identifier for the deposit bank account. | [required] |

### Return type

[**models::DepositBankAccount**](DepositBankAccount.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_deposit_bank_accounts

> models::DepositBankAccountList list_deposit_bank_accounts(page, per_page, guid, bank_guid, customer_guid, label, unique_memo_id, r#type, parent_deposit_bank_account_guid)
List Deposit Bank Accounts

Retrieves a list of deposit bank accounts. Records are sorted by creation date in descending order.  Required scope: **deposit_bank_accounts:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated guids to list deposit bank accounts for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list deposit bank accounts for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list deposit bank accounts for. |  |
**label** | Option<**String**> | Comma separated labels to list deposit bank accounts for. |  |
**unique_memo_id** | Option<**String**> | Comma separated unique memo ids to list deposit bank accounts for. |  |
**r#type** | Option<**String**> | Comma separated types to list deposit bank accounts for. |  |
**parent_deposit_bank_account_guid** | Option<**String**> | Comma separated guids for parent accounts to list deposit bank accounts for. |  |

### Return type

[**models::DepositBankAccountList**](DepositBankAccountList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


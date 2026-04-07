# \ExternalBankAccountsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_external_bank_account**](ExternalBankAccountsApi.md#create_external_bank_account) | **POST** /api/external_bank_accounts | Create ExternalBankAccount
[**delete_external_bank_account**](ExternalBankAccountsApi.md#delete_external_bank_account) | **DELETE** /api/external_bank_accounts/{external_bank_account_guid} | Delete External Bank Account
[**get_external_bank_account**](ExternalBankAccountsApi.md#get_external_bank_account) | **GET** /api/external_bank_accounts/{external_bank_account_guid} | Get External Bank Account
[**list_external_bank_accounts**](ExternalBankAccountsApi.md#list_external_bank_accounts) | **GET** /api/external_bank_accounts | Get external bank accounts list
[**patch_external_bank_account**](ExternalBankAccountsApi.md#patch_external_bank_account) | **PATCH** /api/external_bank_accounts/{external_bank_account_guid} | Patch ExternalBankAccount



## create_external_bank_account

> models::ExternalBankAccount create_external_bank_account(post_external_bank_account)
Create ExternalBankAccount

Create an ExternalBankAccount.  ## Account creation  Accounts can be created for a Bank or a Customer.  To create accounts for your Bank, omit the `customer_guid` parameter in the request body. To create accounts for your Customers, include the `customer_guid` parameter in the request body.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the external bank account details in our private store | | completed | The Platform has created the external bank account | | unverified | The external bank account is created, but it has not yet been verified | | failed | The Platform was not able to successfully create the external bank account | | refresh_required | The Platform has created the external bank account, but needs to be refreshed | | deleting | The Platform is deleting the external bank account | | deleted | The Platform has deleted the external bank account |  ## Failure codes  | Code | Description | |------|-------------| | invalid_routing_number | The provided routing number is invalid | | invalid_account_number | The account number is invalid | | invalid_account_type | The account type is invalid | | duplicate | An account with the same details already exists | | plaid_processor_token | An account could not be created due to an invalid Plaid processor token or an error with Plaid | | plaid_multiple_accounts | The supplied Plaid token is associated with multiple accounts. Must only be a single account. | | create_failed | The bank account and associated holder could not be created correctly | | unverified_counterparty | The counterparty account is unverified |    Required scope: **external_bank_accounts:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_external_bank_account** | [**PostExternalBankAccount**](PostExternalBankAccount.md) |  | [required] |

### Return type

[**models::ExternalBankAccount**](ExternalBankAccount.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_external_bank_account

> models::ExternalBankAccount delete_external_bank_account(external_bank_account_guid)
Delete External Bank Account

Deletes an external bank account.  Required scope: **external_bank_accounts:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**external_bank_account_guid** | **String** | Identifier for the external bank account. | [required] |

### Return type

[**models::ExternalBankAccount**](ExternalBankAccount.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_external_bank_account

> models::ExternalBankAccount get_external_bank_account(external_bank_account_guid, force_balance_refresh, include_balances, include_pii)
Get External Bank Account

Retrieves an external bank account.  ## ExternalBankAccount retrieval  When retrieving an external bank account and include_balances is set to true, the Platform will attempt to retrieve the balance from the account's financial institution.  If force_balance_refresh is set to true, the Platform will always attempt to retrieve the most up to date balance from the account's financial institution. If force_balance_refresh is set to false, the Platform will return the cached balance.  If while getting the balance the Platform determines that the account needs to be refreshed, the Platform will return a 422 status code with the message \"Bank account refresh required\" and the ExternalBankAccount will be put into the refresh_required state.  If while getting the balance the Platform determines that the account is no longer valid, the Platform will return a 422 status code with the message \"Bank account can no longer be used and is being deleted. It must be re-added\" and the ExternalBankAccount will be deleted.  When retrieving an external bank account and include_pii is set to true, the Platform will include the account holder's information in the response.    Required scope: **external_bank_accounts:read** Optional scope: **external_bank_accounts:pii:read**.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**external_bank_account_guid** | **String** | Identifier for the external bank account. | [required] |
**force_balance_refresh** | Option<**bool**> | Force the balance on the account to be retrieved. |  |
**include_balances** | Option<**bool**> | Include balance information in the response. If `force_balance_refresh` is `true`, the most up to date balance will be returned. If `force_balance_refresh` is `false`, the cached balance will be returned. `balance_updated_at` in the response will provide the timestamp the balance was last updated. |  |
**include_pii** | Option<**bool**> | Include the account holder's PII in the response (requires **external_bank_accounts:pii:read** scope). |  |

### Return type

[**models::ExternalBankAccount**](ExternalBankAccount.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_external_bank_accounts

> models::ExternalBankAccountList list_external_bank_accounts(page, per_page, guid, bank_guid, customer_guid, counterparty_guid, asset, state)
Get external bank accounts list

Retrieves a listing of external bank accounts. Records are sorted by creation date in descending order.  Required scope: **external_bank_accounts:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated external_bank_account_guids to list external_bank_accounts for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list external_bank_accounts for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list external_bank_accounts for. |  |
**counterparty_guid** | Option<**String**> | Comma separated counterparty_guids to list external_bank_accounts for. |  |
**asset** | Option<**String**> | Comma separated assets to list external_bank_accounts for. |  |
**state** | Option<**String**> | Comma separated states to list external_bank_accounts for. Filtering by \"completed\" and \"unverified\" states is only supported for individual customer accounts. |  |

### Return type

[**models::ExternalBankAccountList**](ExternalBankAccountList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## patch_external_bank_account

> models::ExternalBankAccount patch_external_bank_account(external_bank_account_guid, patch_external_bank_account)
Patch ExternalBankAccount

Patch an external bank account.  Required scope: **external_bank_accounts:write**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**external_bank_account_guid** | **String** | Identifier for the external bank account. | [required] |
**patch_external_bank_account** | [**PatchExternalBankAccount**](PatchExternalBankAccount.md) |  | [required] |

### Return type

[**models::ExternalBankAccount**](ExternalBankAccount.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


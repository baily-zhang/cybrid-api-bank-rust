# \TransfersApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_transfer**](TransfersApi.md#create_transfer) | **POST** /api/transfers | Create Transfer
[**get_transfer**](TransfersApi.md#get_transfer) | **GET** /api/transfers/{transfer_guid} | Get Transfer
[**list_transfers**](TransfersApi.md#list_transfers) | **GET** /api/transfers | Get transfers list
[**update_transfer**](TransfersApi.md#update_transfer) | **PATCH** /api/transfers/{transfer_guid} | Patch Transfer



## create_transfer

> models::Transfer create_transfer(post_transfer)
Create Transfer

Creates a transfer.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the transfer details in our private store | | reviewing | The Platform is reviewing the transfer for compliance | | pending | The Platform is executing the transfer | | completed | The Platform has successfully completed the transfer | | failed | The Platform was not able to successfully complete the transfer |  ## Failure codes  | Code | Description | |------|-------------| | amount_too_low | The transfer was rejected due to the amount being too low | | cancelled | The transfer was manually cancelled | | compliance_rejection | The transfer was rejected for compliance reasons | | internal_error | An internal error occurred while processing the transfer, please try again | | invalid_address | The destination address is invalid for transfer | | invalid_balance | There was insufficient balance for all required currencies to complete the transfer | | return_risk_exceeded | The risk of return is too high for this activity to be completed | | limit_exceeded | The customer is over the limits that have been set for them for this activity | | daily_limit_exceeded | The customer is over their daily limits for this activity | | weekly_limit_exceeded | The customer is over their weekly limits for this activity | | monthly_limit_exceeded | The customer is over their monthly limits for this activity | | network_fee_too_low | The transfer was rejected due to the network fee being too low | | non_sufficient_funds | The customer does not have enough funds to complete the transfer | | party_name_invalid | The transfer's associated external bank account has an invalid party name | | payment_rail_invalid | The payment rail specified for the transfer is not supported by the external bank account | | payment_request_expired | The payment request expired before it could be completed | | plaid_access_not_granted | See the description from Plaid [here](https://plaid.com/docs/errors/item/#access_not_granted) | | plaid_institution_not_responding | See the description from Plaid [here](https://plaid.com/docs/errors/institution/#institution_not_responding) | | plaid_internal_server_error | See the description from Plaid [here](https://plaid.com/docs/errors/api/#internal_server_error-or-plaid-internal-error) | | plaid_item_not_found | See the description from Plaid [here](https://plaid.com/docs/errors/item/#item_not_found) | | plaid_item_not_supported | See the description from Plaid [here](https://plaid.com/docs/errors/item/#item_not_supported) | | plaid_multiple_accounts | Multiple accounts were selected through Plaid Link. | | plaid_no_accounts | See the description from Plaid [here](https://plaid.com/docs/errors/item/#no_accounts) | | plaid_none_balances_error | The transfer was rejected due to an error with the balances retrieved by Plaid | | plaid_unknown_error | See the description from Plaid [here](https://plaid.com/docs/errors/api/#unknown_error) | | refresh_required | The transfer's associated external_bank_account needs to be reconnected via Plaid | | invalid_destination | Issues with the destination details (invalid, closed, blocked) | | customer_action_required | Authorization declined or customer action required | | external_vendor_error | Unexpected error occurred with an external vendor or partner service during transfer processing  | | reversed | The transfer was reversed |  ## Failure codes that will result in a state change for the associated external bank account  | Code | Description | |------|-------------| | refresh_required | The transfer was rejected due to the external bank account needing to be refreshed. The external bank account will be put in the state `refresh_required` | | plaid_access_not_granted | The transfer was rejected due to the external bank account needing to be reconnected via Plaid. The external bank account will be put in the state `deleted` | | plaid_item_not_found | The transfer was rejected due to the external bank account needing to be reconnected via Plaid. The external bank account will be put in the state `deleted` | | plaid_item_not_supported | The transfer was rejected because the account is not supported. A different account should be connected via Plaid. The external bank account will be put in the state `deleted` | | plaid_multiple_accounts | The transfer was rejected because multiple accounts were selected through Plaid Link. Only one account must be selected. The external bank account will be put in the state `deleted` | | plaid_no_accounts | The transfer was rejected because no compatible accounts could be found. The external bank account will be put in the state `deleted` |    Required scope: **transfers:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_transfer** | [**PostTransfer**](PostTransfer.md) |  | [required] |

### Return type

[**models::Transfer**](Transfer.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_transfer

> models::Transfer get_transfer(transfer_guid)
Get Transfer

Retrieves a transfer.  Required scope: **transfers:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**transfer_guid** | **String** | Identifier for the transfer. | [required] |

### Return type

[**models::Transfer**](Transfer.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_transfers

> models::TransferList list_transfers(page, per_page, guid, transfer_type, bank_guid, customer_guid, account_guid, state, side, label, txn_hash, created_at_gte, created_at_lt, updated_at_gte, updated_at_lt)
Get transfers list

Retrieves a listing of transfers. Records are sorted by creation date in descending order.  Required scope: **transfers:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated transfer_guids to list transfers for. |  |
**transfer_type** | Option<**String**> | Comma separated transfer_types to list accounts for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list transfers for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list transfers for. |  |
**account_guid** | Option<**String**> | Comma separated account_guids to list transfers for. |  |
**state** | Option<**String**> | Comma separated states to list transfers for. |  |
**side** | Option<**String**> | Comma separated sides to list transfers for. |  |
**label** | Option<**String**> | Comma separated labels to list transfers for. |  |
**txn_hash** | Option<**String**> | Comma separated transaction hashes to list transfers for. |  |
**created_at_gte** | Option<**String**> | Created at start date-time inclusive lower bound, ISO8601 |  |
**created_at_lt** | Option<**String**> | Created at end date-time exclusive upper bound, ISO8601. |  |
**updated_at_gte** | Option<**String**> | Created at start date-time inclusive lower bound, ISO8601 |  |
**updated_at_lt** | Option<**String**> | Created at end date-time exclusive upper bound, ISO8601. |  |

### Return type

[**models::TransferList**](TransferList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_transfer

> models::Transfer update_transfer(transfer_guid, patch_transfer)
Patch Transfer

Update a transfer.  Required scope: **transfers:write**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**transfer_guid** | **String** | Identifier for the transfer. | [required] |
**patch_transfer** | [**PatchTransfer**](PatchTransfer.md) |  | [required] |

### Return type

[**models::Transfer**](Transfer.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


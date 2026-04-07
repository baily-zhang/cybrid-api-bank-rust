# \CounterpartiesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_counterparty**](CounterpartiesApi.md#create_counterparty) | **POST** /api/counterparties | Create Counterparty
[**get_counterparty**](CounterpartiesApi.md#get_counterparty) | **GET** /api/counterparties/{counterparty_guid} | Get Counterparty
[**list_counterparties**](CounterpartiesApi.md#list_counterparties) | **GET** /api/counterparties | Get counterparties list



## create_counterparty

> models::Counterparty create_counterparty(post_counterparty)
Create Counterparty

Creates a counterparty.  ## Counterparty Type  Counterparty resources are an abstraction for real world individuals and businesses that are not directly on the Cybrid Platform.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the counterparty details in our private store | | unverified | The Platform has not yet verified the counterparty's identity | | verified | The Platform has verified the counterparty's identity | | rejected | The Platform was not able to successfully verify the counterparty's identity |    Required scope: **counterparties:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_counterparty** | [**PostCounterparty**](PostCounterparty.md) |  | [required] |

### Return type

[**models::Counterparty**](Counterparty.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_counterparty

> models::Counterparty get_counterparty(counterparty_guid, include_pii)
Get Counterparty

Retrieves a counterparty.  Required scope: **counterparties:read** Optional scope: **counterparties:pii:read**.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**counterparty_guid** | **String** | Identifier for the counterparty. | [required] |
**include_pii** | Option<**bool**> | Include PII in the response (requires **counterparties:pii:read** scope). |  |

### Return type

[**models::Counterparty**](Counterparty.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_counterparties

> models::CounterpartyList list_counterparties(page, per_page, r#type, bank_guid, customer_guid, guid, label, include_pii)
Get counterparties list

Retrieves a listing of counterparties. Records are sorted by creation date in descending order.  Required scope: **counterparties:read** Optional scope: **counterparties:pii:read**.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> |  |  |
**per_page** | Option<**i32**> |  |  |
**r#type** | Option<**String**> | Comma separated types to list counterparties for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list counterparties for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list counterparties for. |  |
**guid** | Option<**String**> | Comma separated counterparty_guids to list counterparties for. |  |
**label** | Option<**String**> | Comma separated labels to list counterparties for. |  |
**include_pii** | Option<**bool**> | Include PII in the response (requires **counterparties:pii:read** scope). |  |

### Return type

[**models::CounterpartyList**](CounterpartyList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


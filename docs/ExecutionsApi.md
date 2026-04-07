# \ExecutionsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_execution**](ExecutionsApi.md#create_execution) | **POST** /api/executions | Create Execution
[**get_execution**](ExecutionsApi.md#get_execution) | **GET** /api/executions/{execution_guid} | Get Execution
[**list_executions**](ExecutionsApi.md#list_executions) | **GET** /api/executions | Get executions list



## create_execution

> models::Execution create_execution(post_execution)
Create Execution

Creates an execution.  ## Create a plan execution  | State | Description | |-------|-------------| | storing | The Platform is storing the execution details in our private store | | executing | The Platform is executing the plan | | completed | The Platform has successfully completed the plan execution | | failed | The Platform was not able to successfully complete the plan execution |  ## Failure codes  | Code | Description | |------|-------------| | invalid_counterparty | The payout failed due to an invalid or rejected counterparty | | invalid_destination_account | The payout failed due to an invalid, closed, or blocked destination account |    Required scope: **executions:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_execution** | [**PostExecution**](PostExecution.md) |  | [required] |

### Return type

[**models::Execution**](Execution.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_execution

> models::Execution get_execution(execution_guid)
Get Execution

Retrieves a execution.  Required scope: **executions:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**execution_guid** | **String** | Identifier for the payment instruction. | [required] |

### Return type

[**models::Execution**](Execution.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_executions

> models::ExecutionList list_executions(page, per_page, guid, plan_guid, bank_guid, customer_guid, r#type, state, source_account_guid, destination_account_guid, created_at_gte, created_at_lt, updated_at_gte, updated_at_lt)
Get executions list

Retrieves a listing of executions. Records are sorted by creation date in descending order.  Required scope: **executions:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated execution_guids to list executions for. |  |
**plan_guid** | Option<**String**> | Comma separated plan_guids to list executions for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list executions for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list executions for. |  |
**r#type** | Option<**String**> | Comma separated types to list executions for. |  |
**state** | Option<**String**> | Comma separated states to list executions for. |  |
**source_account_guid** | Option<**String**> | Comma separated source account guids to list executions for. |  |
**destination_account_guid** | Option<**String**> | Comma separated destination account guids to list executions for. |  |
**created_at_gte** | Option<**String**> | Created at start date-time inclusive lower bound, ISO8601. |  |
**created_at_lt** | Option<**String**> | Created at end date-time exclusive upper bound, ISO8601. |  |
**updated_at_gte** | Option<**String**> | Updated at start date-time inclusive lower bound, ISO8601. |  |
**updated_at_lt** | Option<**String**> | Updated at end date-time exclusive upper bound, ISO8601. |  |

### Return type

[**models::ExecutionList**](ExecutionList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


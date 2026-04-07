# \WorkflowsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_workflow**](WorkflowsApi.md#create_workflow) | **POST** /api/workflows | Create Workflow
[**get_workflow**](WorkflowsApi.md#get_workflow) | **GET** /api/workflows/{workflow_guid} | Get Workflow
[**list_workflows**](WorkflowsApi.md#list_workflows) | **GET** /api/workflows | Get workflows list



## create_workflow

> models::Workflow create_workflow(post_workflow)
Create Workflow

Creates a workflow.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the workflow details in our private store | | completed | The Platform has created the workflow | | failed | The workflow was not completed successfully |  ## Plaid  | Param | Description | |-------|-------------| | redirect_uri | All URIs must be registered with Cybrid. For local testing use `http://localhost:4200/bank-account-connect` |    Required scope: **workflows:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_workflow** | [**PostWorkflow**](PostWorkflow.md) |  | [required] |

### Return type

[**models::Workflow**](Workflow.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_workflow

> models::WorkflowWithDetails get_workflow(workflow_guid)
Get Workflow

Retrieves a workflow.  Required scope: **workflows:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workflow_guid** | **String** | Identifier for the workflow. | [required] |

### Return type

[**models::WorkflowWithDetails**](WorkflowWithDetails.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_workflows

> models::WorkflowsList list_workflows(page, per_page, guid, bank_guid, customer_guid)
Get workflows list

Retrieves a listing of workflows. Records are sorted by creation date in descending order.  Required scope: **workflows:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated workflow_guids to list workflows for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list workflows for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list workflows for. |  |

### Return type

[**models::WorkflowsList**](WorkflowsList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \PlansApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_plan**](PlansApi.md#create_plan) | **POST** /api/plans | Create Plan
[**get_plan**](PlansApi.md#get_plan) | **GET** /api/plans/{plan_guid} | Get Plan
[**list_plans**](PlansApi.md#list_plans) | **GET** /api/plans | Get plans list



## create_plan

> models::Plan create_plan(post_plan)
Create Plan

Creates a plan.  ## Create a plan  Plans can be created for a Bank or a Customer.  To create plan for your Bank, omit the `customer_guid` parameter in the request body. To create plans for your Customers, include the `customer_guid` parameter in the request body.  | State | Description | |-------|-------------| | storing | The Platform is storing the plan details in our private store | | planning | The Platform is currently building the plan | | completed | The Platform has successfully completed the plan | | failed | The Platform was not able to successfully complete the plan |    Required scope: **plans:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_plan** | [**PostPlan**](PostPlan.md) |  | [required] |

### Return type

[**models::Plan**](Plan.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_plan

> models::Plan get_plan(plan_guid)
Get Plan

Retrieves a plan.  Required scope: **plans:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**plan_guid** | **String** | Identifier for the payment instruction. | [required] |

### Return type

[**models::Plan**](Plan.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_plans

> models::PlanList list_plans(page, per_page, guid, bank_guid, customer_guid, r#type, state, source_account_guid, destination_account_guid, created_at_gte, created_at_lt, updated_at_gte, updated_at_lt)
Get plans list

Retrieves a listing of plans. Records are sorted by creation date in descending order.  Required scope: **plans:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated plan_guids to list plans for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list plans for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list plans for. |  |
**r#type** | Option<**String**> | Comma separated types to list plans for. |  |
**state** | Option<**String**> | Comma separated states to list plans for. |  |
**source_account_guid** | Option<**String**> | Comma separated source account guids to list plans for. |  |
**destination_account_guid** | Option<**String**> | Comma separated destination account guids to list plans for. |  |
**created_at_gte** | Option<**String**> | Created at start date-time inclusive lower bound, ISO8601. |  |
**created_at_lt** | Option<**String**> | Created at end date-time exclusive upper bound, ISO8601. |  |
**updated_at_gte** | Option<**String**> | Updated at start date-time inclusive lower bound, ISO8601. |  |
**updated_at_lt** | Option<**String**> | Updated at end date-time exclusive upper bound, ISO8601. |  |

### Return type

[**models::PlanList**](PlanList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \CustomersApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_customer**](CustomersApi.md#create_customer) | **POST** /api/customers | Create Customer
[**get_customer**](CustomersApi.md#get_customer) | **GET** /api/customers/{customer_guid} | Get Customer
[**list_customers**](CustomersApi.md#list_customers) | **GET** /api/customers | Get customers list
[**update_customer**](CustomersApi.md#update_customer) | **PATCH** /api/customers/{customer_guid} | Patch Customer



## create_customer

> models::Customer create_customer(post_customer)
Create Customer

Creates a customer.  ## Customer Type  Customer resources are an abstraction for real world individuals and businesses on the Cybrid Platform and are used throughout the platform to perform high level operations, e.g., create a quote, execute a trade, etc..  Customers can have additional resources attached to them, e.g., identity verifications, accounts, etc.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the customer details in our private store | | unverified | The Platform has not yet verified the customer's identity | | verified | The Platform has verified the customer's identity | | rejected | The Platform was not able to successfully verify the customer's identity | | frozen | The customer has been frozen on the Platform |    Required scope: **customers:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_customer** | [**PostCustomer**](PostCustomer.md) |  | [required] |

### Return type

[**models::Customer**](Customer.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_customer

> models::Customer get_customer(customer_guid, include_pii)
Get Customer

Retrieves a customer.  Required scope: **customers:read** Optional scope: **customers:pii:read**.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**customer_guid** | **String** | Identifier for the customer. | [required] |
**include_pii** | Option<**bool**> | Include PII in the response (requires **customers:pii:read** scope). |  |

### Return type

[**models::Customer**](Customer.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_customers

> models::CustomerList list_customers(page, per_page, r#type, bank_guid, guid, label, include_pii)
Get customers list

Retrieves a listing of customers. Records are sorted by creation date in descending order.  Required scope: **customers:read** Optional scope: **customers:pii:read**.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> |  |  |
**per_page** | Option<**i32**> |  |  |
**r#type** | Option<**String**> | Comma separated types to list customers for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list customers for. |  |
**guid** | Option<**String**> | Comma separated customer_guids to list customers for. |  |
**label** | Option<**String**> | Comma separated labels to list customers for. |  |
**include_pii** | Option<**bool**> | Include PII in the response (requires **customers:pii:read** scope). |  |

### Return type

[**models::CustomerList**](CustomerList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_customer

> models::Customer update_customer(customer_guid, patch_customer)
Patch Customer

Update a customer.  Required scope: **customers:write**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**customer_guid** | **String** | Identifier for the customer. | [required] |
**patch_customer** | [**PatchCustomer**](PatchCustomer.md) |  | [required] |

### Return type

[**models::Customer**](Customer.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


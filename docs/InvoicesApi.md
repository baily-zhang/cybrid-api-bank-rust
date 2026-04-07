# \InvoicesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancel_invoice**](InvoicesApi.md#cancel_invoice) | **DELETE** /api/invoices/{invoice_guid} | Cancel Invoice
[**create_invoice**](InvoicesApi.md#create_invoice) | **POST** /api/invoices | Create Invoice
[**get_invoice**](InvoicesApi.md#get_invoice) | **GET** /api/invoices/{invoice_guid} | Get Invoice
[**list_invoices**](InvoicesApi.md#list_invoices) | **GET** /api/invoices | List Invoices



## cancel_invoice

> models::Invoice cancel_invoice(invoice_guid)
Cancel Invoice

Cancels an invoice.  Required scope: **invoices:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**invoice_guid** | **String** | Identifier for the invoice. | [required] |

### Return type

[**models::Invoice**](Invoice.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_invoice

> models::Invoice create_invoice(post_invoice)
Create Invoice

Creates a invoice.  ## State  | State | Description | |-------|-------------| | storing    | The Platform is storing the invoice details in our private store | | unpaid     | The invoice is unpaid. Payment instructions can be generated for an invoice in this state | | cancelling | The invocie is in the process of being cancelled | | cancelled  | The invoice has been cancelled |  | settling   | The invoice has been paid and the funds associated with this invoice are in the process of being settled | | paid       | The invoice has been paid and the funds associated with this invoice have been settled |     Required scope: **invoices:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_invoice** | [**PostInvoice**](PostInvoice.md) |  | [required] |

### Return type

[**models::Invoice**](Invoice.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_invoice

> models::Invoice get_invoice(invoice_guid)
Get Invoice

Retrieves a invoice.  Required scope: **invoices:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**invoice_guid** | **String** | Identifier for the payment instruction. | [required] |

### Return type

[**models::Invoice**](Invoice.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_invoices

> models::InvoiceList list_invoices(page, per_page, guid, bank_guid, customer_guid, account_guid, state, asset, environment, label)
List Invoices

Retrieves a list of invoices. Records are sorted by creation date in descending order.  Required scope: **invoices:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated guids to list invoices for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list invoices for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list invoices for. |  |
**account_guid** | Option<**String**> | Comma separated account_guids to list invoices for. |  |
**state** | Option<**String**> | Comma separated states to list invoices for. |  |
**asset** | Option<**String**> | Comma separated assets to list invoices for. |  |
**environment** | Option<**String**> |  |  |
**label** | Option<**String**> | Comma separated labels to list invoices for. |  |

### Return type

[**models::InvoiceList**](InvoiceList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


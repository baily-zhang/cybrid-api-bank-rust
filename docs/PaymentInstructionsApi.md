# \PaymentInstructionsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_payment_instruction**](PaymentInstructionsApi.md#create_payment_instruction) | **POST** /api/payment_instructions | Create Payment Instruction
[**get_payment_instruction**](PaymentInstructionsApi.md#get_payment_instruction) | **GET** /api/payment_instructions/{payment_instruction_guid} | Get Payment Instruction
[**list_payment_instructions**](PaymentInstructionsApi.md#list_payment_instructions) | **GET** /api/payment_instructions | List Payment Instructions



## create_payment_instruction

> models::PaymentInstruction create_payment_instruction(post_payment_instruction)
Create Payment Instruction

Creates a payment instruction.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the payment instruction details in our private store | | created | The Platform has created the payment instruction | | expired | The PaymentInstruction is no longer valid |    Required scope: **invoices:write**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_payment_instruction** | [**PostPaymentInstruction**](PostPaymentInstruction.md) |  | [required] |

### Return type

[**models::PaymentInstruction**](PaymentInstruction.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_payment_instruction

> models::PaymentInstruction get_payment_instruction(payment_instruction_guid)
Get Payment Instruction

Retrieves a payment_instruction.  Required scope: **invoices:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**payment_instruction_guid** | **String** | Identifier for the payment instruction. | [required] |

### Return type

[**models::PaymentInstruction**](PaymentInstruction.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_payment_instructions

> models::PaymentInstructionList list_payment_instructions(page, per_page, guid, bank_guid, customer_guid, invoice_guid)
List Payment Instructions

Retrieves a list of payment instructions. Records are sorted by creation date in descending order.  Required scope: **invoices:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated guids to list payment instructions for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list payment instructions for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list payment instructions for. |  |
**invoice_guid** | Option<**String**> | Comma separated invoice_guids to list payment instructions for. |  |

### Return type

[**models::PaymentInstructionList**](PaymentInstructionList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


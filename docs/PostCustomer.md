# PostCustomer

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The type of customer. (enum: business, individual) | 
**address** | Option<[**models::PostCustomerAddress**](PostCustomerAddress.md)> |  | [optional]
**phone_number** | Option<**String**> | The customer's phone number. | [optional]
**email_address** | Option<**String**> | The customer's email address. | [optional]
**identification_numbers** | Option<[**Vec<models::PostIdentificationNumber>**](PostIdentificationNumber.md)> | The customer's identification numbers. | [optional]
**name** | Option<[**models::PostCustomerName**](PostCustomerName.md)> |  | [optional]
**date_of_birth** | Option<[**String**](String.md)> | The customer's date of birth. Optional when type is individual. | [optional]
**aliases** | Option<[**Vec<models::PostCustomerAliasesInner>**](PostCustomerAliasesInner.md)> | The aliases of the customer. Optional when type is business. | [optional]
**website** | Option<**String**> | The customer's website. Optional when type is business. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the customer. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



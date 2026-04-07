# PostCounterparty

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The counterparty's type. (enum: business, individual) | 
**customer_guid** | Option<**String**> | The owning customer's identifier. | [optional]
**address** | [**models::PostCounterpartyAddress**](PostCounterpartyAddress.md) |  | 
**name** | Option<[**models::PostCounterpartyName**](PostCounterpartyName.md)> |  | [optional]
**aliases** | Option<[**Vec<models::PostCounterpartyAliasesInner>**](PostCounterpartyAliasesInner.md)> | The aliases of the counterparty. Optional when type is business. | [optional]
**date_of_birth** | Option<[**String**](String.md)> | The counterparty's date of birth. Optional when type is individual. | [optional]
**email_address** | Option<**String**> | The counterparty's email address. | [optional]
**identification_numbers** | Option<[**Vec<models::PostIdentificationNumber>**](PostIdentificationNumber.md)> | The counterparty's identification numbers. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the counterparty. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



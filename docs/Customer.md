# Customer

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the customer. | [optional]
**bank_guid** | Option<**String**> | Auto-generated unique identifier for the customer's bank. | [optional]
**r#type** | Option<**String**> | The customer type; one of business or individual. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**state** | Option<**String**> | The customer state; one of storing, unverified, verified, rejected, or frozen. | [optional]
**name** | Option<[**models::CustomerName**](CustomerName.md)> |  | [optional]
**address** | Option<[**models::CustomerAddress**](CustomerAddress.md)> |  | [optional]
**aliases** | Option<[**Vec<models::CustomerAliasesInner>**](CustomerAliasesInner.md)> | The customer's aliases. Only available for GET operations when 'include_pii' is set. | [optional]
**website** | Option<**String**> | The customer's website. Only available for GET operations when 'include_pii' is set. | [optional]
**date_of_birth** | Option<[**String**](String.md)> | The customer's DOB. Only available for GET operations when 'include_pii' is set. | [optional]
**phone_number** | Option<**String**> | The customer's phone number. Only available for GET operations when 'include_pii' is set. | [optional]
**email_address** | Option<**String**> | The customer's email address. Only available for GET operations when 'include_pii' is set. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the customer. | [optional]
**compliance_decisions** | Option<[**Vec<models::ComplianceDecision>**](ComplianceDecision.md)> | The compliance decisions associated with the customer. | [optional]
**identification_numbers** | Option<[**Vec<models::IdentificationNumber>**](IdentificationNumber.md)> | The customer's identification numbers. Only available for GET operations when 'include_pii' is set and bank has access. | [optional]
**activity_limits** | Option<[**Vec<models::ActivityLimit>**](ActivityLimit.md)> | The asset limits associated with the customer. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



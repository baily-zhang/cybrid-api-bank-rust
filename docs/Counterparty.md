# Counterparty

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the counterparty. | [optional]
**r#type** | Option<**String**> | The counterparty type; one of business or individual. | [optional]
**bank_guid** | Option<**String**> | Auto-generated unique identifier for the counterparty's bank. | [optional]
**customer_guid** | Option<**String**> | Auto-generated unique identifier for the counterparty's customer. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**state** | Option<**String**> | The counterparty state; one of storing, unverified, verified, or rejected. | [optional]
**name** | Option<[**models::CounterpartyName**](CounterpartyName.md)> |  | [optional]
**address** | Option<[**models::CounterpartyAddress**](CounterpartyAddress.md)> |  | [optional]
**aliases** | Option<[**Vec<models::CounterpartyAliasesInner>**](CounterpartyAliasesInner.md)> | The counterparty's aliases. Only available for GET operations when 'include_pii' is set. | [optional]
**date_of_birth** | Option<[**String**](String.md)> | The counterparty's DOB. Only available for GET operations when 'include_pii' is set. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the counterparty. | [optional]
**compliance_decisions** | Option<[**Vec<models::ComplianceDecision>**](ComplianceDecision.md)> | The compliance decisions associated with the counterparty. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



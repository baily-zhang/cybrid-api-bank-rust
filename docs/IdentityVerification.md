# IdentityVerification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the identity verification. | [optional]
**r#type** | Option<**String**> | The identity verification type; one of kyc, bank_account, or counterparty. | [optional]
**method** | Option<**String**> | The identity verification method; one of attested, document_submission, enhanced_due_diligence, id_and_selfie, tax_id_and_selfie, business_registration, attested_id_and_selfie, attested_business_registration, attested_business_associate, attested_id_and_database, watchlists, attested_ownership, or account_ownership. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**customer_guid** | Option<**String**> | The customer's identifier. | [optional]
**counterparty_guid** | Option<**String**> | The counterparty's identifier. | [optional]
**external_bank_account_guid** | Option<**String**> | The external bank account's identifier. | [optional]
**state** | Option<**String**> | The identity verification state; one of storing, waiting, pending, reviewing, expired, or completed. | [optional]
**outcome** | Option<**String**> | The identity verification outcome; one of passed or failed. | [optional]
**failure_codes** | Option<**Vec<String>**> | The reason codes explaining the outcome. | [optional]
**compliance_decisions** | Option<[**Vec<models::ComplianceDecision>**](ComplianceDecision.md)> | The compliance decisions associated with the identity verification. | [optional]
**options** | Option<[**models::IdentityVerificationOptions**](IdentityVerificationOptions.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



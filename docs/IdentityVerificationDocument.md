# IdentityVerificationDocument

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the document. | [optional]
**r#type** | Option<**String**> | The document type; one of drivers_license, passport, passport_card, residence_card, visa, social_security_number, tax_identification_number, selfie, proof_of_address, formation_document, employer_identification_number, indigenous_document_number, or work_permit. | [optional]
**validated** | Option<**bool**> | Whether the document has been validated. | [optional]
**expiration_date** | Option<[**String**](String.md)> | The document expiration date. | [optional]
**files** | Option<[**Vec<models::IdentityVerificationDocumentFile>**](IdentityVerificationDocumentFile.md)> | The files associated with the document. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



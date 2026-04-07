# PostFile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The type of file. (enum: drivers_license_front, drivers_license_back, drivers_license, passport, passport_card, visa, identification_card, residence_card, work_permit, indigenous_id_document, selfie, selfie_video, selfie_left, selfie_right, utility_bill, proof_of_address, bank_statement, property_tax, tax_document, ein_letter, incorporation_certificate, persona_inquiry_report, persona_inquiry_export) | 
**customer_guid** | **String** | The customer identifier. | 
**filename** | **String** | The name of the file. | 
**content_type** | **ContentType** | The content type of the file. (enum: image/jpeg, image/png, application/pdf, application/json, video/mp4) | 
**data** | Option<**String**> | Base64 encoded file content | [optional]
**metadata** | Option<[**models::PostFileMetadata**](PostFileMetadata.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# PlatformFile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | The unique identifier for the file. | [optional]
**organization_guid** | Option<**String**> | The organization identifier. | [optional]
**bank_guid** | Option<**String**> | The bank identifier. | [optional]
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**r#type** | Option<**String**> | The file type; one of drivers_license_front, drivers_license_back, drivers_license, passport, passport_card, visa, identification_card, residence_card, work_permit, indigenous_id_document, selfie, selfie_video, selfie_left, selfie_right, utility_bill, proof_of_address, bank_statement, property_tax, tax_document, ein_letter, incorporation_certificate, persona_inquiry_report, or persona_inquiry_export. | [optional]
**content_type** | Option<**String**> | The media type; one of image/jpeg, image/png, application/pdf, application/json, or video/mp4. | [optional]
**filename** | Option<**String**> | The name of the file. | [optional]
**completed_at** | Option<**String**> | The ISO8601 datetime the file was completed at. | [optional]
**failed_at** | Option<**String**> | The ISO8601 datetime the file failed at. | [optional]
**state** | Option<**State**> | The state of the file. One of storing, completed, or failed. (enum: storing, completed, failed) | [optional]
**failure_code** | Option<**String**> | The failure code for failed files. | [optional]
**upload_url** | Option<**String**> | The URL to upload the file to. | [optional]
**upload_expires_at** | Option<**String**> | The ISO8601 datetime the upload URL expires at. | [optional]
**download_url** | Option<**String**> | The URL to download the file from. | [optional]
**download_expires_at** | Option<**String**> | The ISO8601 datetime the download URL expires at. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



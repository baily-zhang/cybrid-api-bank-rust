# PostWorkflow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The workflow type. (enum: plaid) | 
**kind** | Option<**Kind**> | The Plaid workflow kind. Required when type is plaid. (enum: link_token_create, link_token_update) | [optional]
**customer_guid** | Option<**String**> | The customer identifier associated with the workflow. Optional when type is plaid and kind is link_token_create. | [optional]
**external_bank_account_guid** | Option<**String**> | The external bank account identifier associated with the workflow. Required when type is plaid and kind is link_token_update. | [optional]
**language** | Option<**Language**> | The language to initialize Plaid link. Required when type is plaid. (enum: en, fr, es, nl, de) | [optional]
**link_customization_name** | Option<**String**> | The customization name for Plaid link. For English, use \"default\". For Spanish, use \"spanish_customization\". Required when type is plaid. | [optional]
**redirect_uri** | Option<**String**> | The redirect URI for Plaid link. Optional when type is plaid. | [optional]
**android_package_name** | Option<**String**> | The Android package name for Plaid link. Optional when type is plaid. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



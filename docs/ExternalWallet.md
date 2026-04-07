# ExternalWallet

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the wallet. | [optional]
**name** | Option<**String**> | The name of the wallet. | [optional]
**asset** | Option<**String**> | The asset code. | [optional]
**environment** | Option<**String**> | The environment that the wallet is configured for; one of sandbox or production. | [optional]
**bank_guid** | Option<**String**> | The bank identifier. | [optional]
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**counterparty_guid** | Option<**String**> | The counterparty identifier. | [optional]
**address** | Option<**String**> | The blockchain wallet address for the wallet. | [optional]
**tag** | Option<**String**> | The blockchain tag to use when transferring crypto to the wallet. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**state** | Option<**String**> | The state of the external wallet; one of storing, pending, failed, completed, deleting, or deleted. | [optional]
**failure_code** | Option<**String**> | The failure code of an external wallet (if any) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# PostExternalWallet

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **String** | Name of the external wallet. | 
**customer_guid** | Option<**String**> | The customer identifier. | [optional]
**counterparty_guid** | Option<**String**> | The counterparty identifier. | [optional]
**asset** | **String** | The asset code. | 
**address** | **String** | The blockchain wallet address for the wallet. | 
**tag** | Option<**String**> | The blockchain tag to use when transferring crypto to the wallet. | [optional]
**expected_behaviours** | Option<**Vec<ExpectedBehaviours>**> | The optional expected behaviour to simulate. Only applicable wallets under sandbox banks. (enum: force_review) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# Transfer

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | Option<**String**> | Auto-generated unique identifier for the transfer. | [optional]
**transfer_type** | Option<**String**> | The type of transfer; one of funding, book, crypto, instant_funding, funding_return, crypto_return, loss_recovery, inter_account, lightning, or instant_funding_return. | [optional]
**bank_guid** | Option<**String**> | The associated bank's identifier. | [optional]
**customer_guid** | Option<**String**> | The associated customer's identifier. | [optional]
**quote_guid** | Option<**String**> | The associated quote's identifier. | [optional]
**external_bank_account_guid** | Option<**String**> | The associated external bank account's identifier. | [optional]
**asset** | Option<**String**> | The asset the transfer is related to, e.g., USD. | [optional]
**side** | Option<**String**> | The direction of the quote; one of deposit or withdrawal. | [optional]
**state** | Option<**String**> | The state of the transfer; one of storing, pending, reviewing, completed, or failed. | [optional]
**failure_code** | Option<**String**> | The failure code for failed transfers; one of non_sufficient_funds, refresh_required, party_name_invalid, payment_rail_invalid, compliance_rejection, cancelled, reversed, limit_exceeded, network_fee_too_low, amount_too_low, internal_error, invalid_address, invalid_destination, customer_action_required, external_vendor_error, or payment_request_expired. | [optional]
**return_code** | Option<**String**> | The return code for reversed transfers | [optional]
**amount** | Option<**i32**> | The actual amount in base units of the asset. | [optional]
**estimated_amount** | Option<**i32**> | The estimated amount in base units of the asset. | [optional]
**fee** | Option<**i32**> | The fee associated with the transfer. Represents the sum of the bank and platform fees. | [optional]
**fee_details** | Option<[**Vec<models::FeeDetail>**](FeeDetail.md)> | The fees associated with the transfer. | [optional]
**estimated_network_fee** | Option<**i32**> | The estimated network fee in base units of network_fee_asset. Only present on `crypto` transfers. | [optional]
**network_fee** | Option<**i32**> | The actual network fee in base units of network_fee_asset. Only present on `crypto` transfers that have successfully completed. | [optional]
**network_fee_asset** | Option<**String**> | The asset code of the network fee. Only present on `crypto` transfers that have successfully completed. | [optional]
**network_fee_liability_amount** | Option<**i32**> | The equivalent fiat network fee in base units of network_fee_liability_amount_asset. Only present on `crypto` transfers that have successfully completed. | [optional]
**network_fee_liability_amount_asset** | Option<**String**> | The fiat asset the network_fee_liability_amount is denominated in. Only present on `crypto` transfers that have successfully completed. | [optional]
**txn_hash** | Option<**String**> | The hash of the blockchain transaction (deprecated: use identifiers array) | [optional]
**identifiers** | Option<[**Vec<models::TransferIdentifiersInner>**](TransferIdentifiersInner.md)> | Array of identifiers associated with this transfer (transaction hash, wire reference numbers) | [optional]
**reference_transfer_guid** | Option<**String**> | The guid of the related transfer. Only present on return type transfers. | [optional]
**source_account** | Option<[**models::TransferSourceAccount**](TransferSourceAccount.md)> |  | [optional]
**source_participants** | Option<[**Vec<models::TransferParticipant>**](TransferParticipant.md)> | The participants in the source account. | [optional]
**destination_account** | Option<[**models::TransferDestinationAccount**](TransferDestinationAccount.md)> |  | [optional]
**destination_participants** | Option<[**Vec<models::TransferParticipant>**](TransferParticipant.md)> | The participants in the source account. | [optional]
**deposit_address_guid** | Option<**String**> | The guid of the deposit address. Only present on crypto deposits. | [optional]
**created_at** | Option<**String**> | ISO8601 datetime the record was created at. | [optional]
**updated_at** | Option<**String**> | ISO8601 datetime the record was last updated at. | [optional]
**hold_details** | Option<[**models::TransferHoldDetails**](TransferHoldDetails.md)> |  | [optional]
**transfer_details** | Option<**serde_json::Value**> | The raw details on the transfer from the bank. | [optional]
**payment_rail** | Option<**String**> | The rail the payment was done on. One of: ach, eft, wire, rtp, etransfer | [optional]
**external_id** | Option<**String**> | The external identifier for the transfer. | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the transfer. | [optional]
**entries** | Option<[**Vec<models::TransferEntry>**](TransferEntry.md)> | Transfer entries associated with the batch transfer | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



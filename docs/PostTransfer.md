# PostTransfer

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**quote_guid** | **String** | The associated quote's identifier. | 
**transfer_type** | **TransferType** | The type of transfer. (enum: funding, crypto, instant_funding, inter_account, lightning, book) | 
**external_bank_account_guid** | Option<**String**> | The customer's 'plaid', 'plaid_processor_token', or 'raw_routing_details' external bank account's identifier. Required for ACH, EFT, WIRE, and RTP payment rails. Not used for e-transfer rail. Required when transfer_type is instant_funding. Optional when transfer_type is funding. | [optional]
**fiat_account_guid** | Option<**String**> | The identifier for the fiat account to use for the transfer. Required if the customer or bank has multiple fiat accounts. Optional when transfer_type is funding. | [optional]
**send_as_deposit_bank_account_guid** | Option<**String**> | The deposit bank account's identifier. Only valid for withdrawals. The deposit bank account must be owned by the customer or bank initiating the transfer. Optional when transfer_type is funding. | [optional]
**payment_rail** | Option<**PaymentRail**> | The desired payment rail to initiate the transfer for. Optional when transfer_type is funding. (enum: ach, eft, wire, rtp, etransfer) | [optional]
**beneficiary_memo** | Option<**String**> | The memo to send to the counterparty. Optional when transfer_type is funding. | [optional]
**source_participants** | Option<[**Vec<models::PostTransferParticipant>**](PostTransferParticipant.md)> | The source participants for the transfer. Required when transfer_type is funding, transfer_type is instant_funding, transfer_type is book, transfer_type is crypto, or transfer_type is lightning. | [optional]
**destination_participants** | Option<[**Vec<models::PostTransferParticipant>**](PostTransferParticipant.md)> | The destination participants for the transfer. Required when transfer_type is funding, transfer_type is instant_funding, transfer_type is book, transfer_type is crypto, or transfer_type is lightning. | [optional]
**bank_fiat_account_guid** | Option<**String**> | The identifier for the fiat account to use for the transfer. Required if the bank has multiple fiat accounts. Optional when transfer_type is instant_funding or transfer_type is lightning. | [optional]
**customer_fiat_account_guid** | Option<**String**> | The identifier for the fiat account to use for the transfer. Required if the customer has multiple fiat accounts. Optional when transfer_type is instant_funding or transfer_type is lightning. | [optional]
**source_account_guid** | Option<**String**> | The source account's identifier. Required when transfer_type is book or transfer_type is inter_account. | [optional]
**destination_account_guid** | Option<**String**> | The destination account's identifier. Required when transfer_type is book or transfer_type is inter_account. | [optional]
**external_wallet_guid** | Option<**String**> | The customer's external wallet's identifier. Optional when transfer_type is crypto. | [optional]
**customer_guid** | Option<**String**> | The customer's identifier. Required when transfer_type is lightning. | [optional]
**network_fee_account_guid** | Option<**String**> | The network fee account's identifier. Required for network fee transfers. Must be the identifier for the customer's or bank's fiat or trading account. For customer's to pay the network fees, include the customer's fiat or trading account guid. For bank's to pay the network fees, include the bank's fiat or trading account guid. Required when transfer_type is lightning. | [optional]
**expected_behaviours** | Option<**Vec<ExpectedBehaviours>**> | The optional expected behaviour to simulate. Only applicable for transfers under sandbox banks. The force_review behaviour will force the transfer to be reviewed for funding and instant_funding transfers. (enum: force_review) | [optional]
**labels** | Option<**Vec<String>**> | The labels associated with the transfer. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



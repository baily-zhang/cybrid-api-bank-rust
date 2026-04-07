# PostBankAccountDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**bank_code** | Option<**String**> | The bank code. | [optional]
**account_identifier** | **String** | The account number or unique identifier for the account. | 
**account_identifier_type** | Option<**AccountIdentifierType**> | The type of account identifier. Must be PHONE_NUMBER for mobile wallet rails. Required when payment_rail is EASY_PAISA, payment_rail is FINJA, payment_rail is JAZZ_CASH, payment_rail is NAYA_PAY, or payment_rail is SADA_PAY. (enum: CLABE, PHONE_NUMBER, EMAIL, DEBIT_CARD, CBU, CVU, RANDOM, CPF, CNPJ) | [optional]
**payment_rail** | **PaymentRail** | The payment rail used for the account. (enum: EFT, ACH, RTP, WIRE, SPEI, PIX, COELSA, PSE, ETRANSFER, IFSC, SBP, BEFTN, NGBANK, LBTR, EASY_PAISA, FINJA, JAZZ_CASH, NAYA_PAY, SADA_PAY, UNSPECIFIED) | 
**bank_code_type** | Option<**BankCodeType**> | The type of bank code. Required when payment_rail is EFT, payment_rail is ACH, payment_rail is RTP, payment_rail is WIRE, payment_rail is SPEI, payment_rail is PIX, payment_rail is COELSA, payment_rail is PSE, payment_rail is ETRANSFER, payment_rail is IFSC, payment_rail is SBP, payment_rail is BEFTN, payment_rail is NGBANK, payment_rail is LBTR, or payment_rail is UNSPECIFIED. (enum: CPA, ABA, CLABE, PIX, CBU_CVU, PSE, IFSC, IBAN, SBP, BEFTN, SWIFT_BIC, CBN) | [optional]
**account_type** | Option<**AccountType**> | The type of account. Required when payment_rail is PSE or payment_rail is LBTR. (enum: checking, savings) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



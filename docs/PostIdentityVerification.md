# PostIdentityVerification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The type of identity verification. (enum: kyc, bank_account, counterparty) | 
**customer_guid** | Option<**String**> | The customer's identifier. Required when type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, or type is kyc and method is attested_id_and_database. | [optional]
**expected_behaviours** | Option<**Vec<ExpectedBehaviours>**> | The optional expected behaviour to simulate. (enum: passed_immediately, failed_immediately, tax_id_not_checked) | [optional]
**method** | Option<**Method**> | The identity verification method. Required when type is counterparty, type is kyc, or type is bank_account. (enum: watchlists, attested, document_submission, enhanced_due_diligence, id_and_selfie, tax_id_and_selfie, business_registration, attested_id_and_selfie, attested_business_registration, attested_business_associate, attested_id_and_database, attested_ownership, account_ownership) | [optional]
**counterparty_guid** | Option<**String**> | The counterparty's identifier. Required when type is counterparty. | [optional]
**country_code** | Option<**String**> | The ISO 3166 country 2-Alpha country the customer is being verified in. If not present, will default to the Bank's configured country code. Optional when type is kyc and method is id_and_selfie, type is kyc and method is tax_id_and_selfie, or type is kyc and method is business_registration. | [optional]
**require_tax_id** | Option<**bool**> | Whether the collection of the tax id is required during identity verification. This will default to SSN in USA and SIN in Canada. It's not used elsewhere. Optional when type is kyc and method is id_and_selfie. | [optional][default to false]
**name** | Option<[**models::PostIdentityVerificationName**](PostIdentityVerificationName.md)> |  | [optional]
**address** | Option<[**models::PostIdentityVerificationAddress**](PostIdentityVerificationAddress.md)> |  | [optional]
**date_of_birth** | Option<[**String**](String.md)> | The customer's date of birth. Required when type is kyc and method is attested, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, or type is kyc and method is attested_id_and_database. | [optional]
**identification_numbers** | Option<[**Vec<models::PostIdentificationNumber>**](PostIdentificationNumber.md)> | The customer's identification numbers. Required when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, or type is kyc and method is attested_id_and_database. | [optional]
**aliases** | Option<[**Vec<models::PostIdentityVerificationAliasesInner>**](PostIdentityVerificationAliasesInner.md)> | The aliases of the customer. Optional when type is kyc and method is attested_business_registration or type is kyc and method is watchlists. | [optional]
**phone_number** | Option<**String**> | The customer's phone number. Required when type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, or type is kyc and method is attested_id_and_database. Optional when type is bank_account and method is attested_ownership. | [optional]
**email_address** | Option<**String**> | The customer's email address. Required when type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, or type is kyc and method is attested_id_and_database. Optional when type is bank_account and method is attested_ownership. | [optional]
**website** | Option<**String**> | The customer's website. Required when type is kyc and method is attested_business_registration. | [optional]
**nature_of_business** | Option<**String**> | The customer's nature of business. Required when type is kyc and method is attested_business_registration. | [optional]
**director_customer_guids** | Option<**Vec<String>**> | The customer guids of the directors of the business Required when type is kyc and method is attested_business_registration. | [optional]
**ultimate_beneficial_owners** | Option<[**Vec<models::PostUltimateBeneficialOwner>**](PostUltimateBeneficialOwner.md)> | The ultimate beneficial owners of the business with 10% or more ownership Required when type is kyc and method is attested_business_registration. | [optional]
**supporting_file_guids** | Option<**Vec<String>**> | File guids supporting the verification Required when type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, or type is kyc and method is attested_id_and_database. | [optional]
**registered_address** | Option<[**models::PostIdentityVerificationRegisteredAddress**](PostIdentityVerificationRegisteredAddress.md)> |  | [optional]
**business_industry** | Option<**String**> | The industry the business operates in. Required for attested business registration V3. e.g. 'Crypto / Digital Assets / Blockchain', 'Education', 'Gaming', 'Healthcare / Hospitality', 'Lending / Investments', 'Retail / E-Commerce', etc. Optional when type is kyc and method is attested_business_registration. | [optional]
**business_funds_source** | Option<**String**> | The source of business funds. Required for attested business registration V3. e.g. 'Funds from individual customers', 'Funds from business customers', 'Funds from both individual and business customers', etc. Optional when type is kyc and method is attested_business_registration. | [optional]
**business_funds_destination** | Option<**String**> | The destination of business funds. Required for attested business registration V3. e.g. 'To your business account (bank or wallet)', 'To vendors or suppliers', 'To employees or contractors', 'To sellers or merchants', 'Bulk payments or payouts', etc. Optional when type is kyc and method is attested_business_registration. | [optional]
**occupation** | Option<**String**> | The customer's occupation. Required when type is kyc and method is attested_business_associate. Optional when type is kyc and method is attested_id_and_selfie. | [optional]
**biometrics_verified** | Option<**bool**> | Whether biometrics have been verified Required when type is kyc and method is attested_business_associate or type is kyc and method is attested_id_and_database. | [optional]
**external_bank_account_guid** | Option<**String**> | The external bank account's identifier. Required when type is bank_account. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



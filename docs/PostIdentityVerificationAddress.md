# PostIdentityVerificationAddress

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**street** | Option<**String**> | The first line of the address. Required when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, type is kyc and method is attested_id_and_database, type is kyc and method is watchlists, or type is bank_account and method is attested_ownership. | [optional]
**street2** | Option<**String**> | The optional second line of the address. Optional when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, type is kyc and method is attested_id_and_database, type is kyc and method is watchlists, or type is bank_account and method is attested_ownership. | [optional]
**city** | Option<**String**> | The city of the address. Required when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, type is kyc and method is attested_id_and_database, type is kyc and method is watchlists, or type is bank_account and method is attested_ownership. | [optional]
**subdivision** | Option<**String**> | The ISO 3166-2 subdivision code of the address. Applicable only for countries that use subnational states, provinces, lands, oblasts or regions. Optional when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, type is kyc and method is attested_id_and_database, type is kyc and method is watchlists, or type is bank_account and method is attested_ownership. | [optional]
**postal_code** | Option<**String**> | The postal, zip or post code of the address. Applicable only for countries that use postal, zip or post codes. Optional when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, type is kyc and method is attested_id_and_database, type is kyc and method is watchlists, or type is bank_account and method is attested_ownership. | [optional]
**country_code** | Option<**String**> | The ISO 3166 country 2-Alpha country code of the address. Required when type is kyc and method is attested, type is kyc and method is attested_business_registration, type is kyc and method is attested_id_and_selfie, type is kyc and method is attested_business_associate, type is kyc and method is attested_id_and_database, type is kyc and method is watchlists, or type is bank_account and method is attested_ownership. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



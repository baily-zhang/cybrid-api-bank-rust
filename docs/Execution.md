# Execution

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | **String** | Auto-generated unique identifier for the quote. | 
**r#type** | **String** | The type of product the plan is for; one of remittance. | 
**plan_guid** | **String** | The unique identifier for the plan. | 
**bank_guid** | Option<**String**> | The unique identifier for the bank. | [optional]
**customer_guid** | Option<**String**> | The unique identifier for the customer. | [optional]
**created_at** | **String** | ISO8601 datetime the record was created at. | 
**updated_at** | **String** | ISO8601 datetime the record was last updated at. | 
**state** | **String** | The state of the execution; one of storing, executing, completed, or failed. | 
**failure_code** | Option<**String**> | The failure code for failed executions. | [optional]
**source_account** | [**models::AccountAssociation**](AccountAssociation.md) |  | 
**destination_account** | [**models::AccountAssociation**](AccountAssociation.md) |  | 
**stages** | [**Vec<models::Stage>**](Stage.md) | The stages of the execution. | 
**fees** | [**Vec<models::FeeAssociation>**](FeeAssociation.md) | The fees associated with the execution. | 
**travel_rule_info** | [**models::ExecutionTravelRuleInfo**](ExecutionTravelRuleInfo.md) |  | 
**purpose_of_transaction** | Option<**PurposeOfTransaction**> | The purpose of transaction for the execution. (enum: computer_services, family_support, education, gift, charitable_donation, medical_treatment, maintenance_expenses, travel, hotel_accommodation, small_value_remittance, liberalized_remittance, personal_transfer, loan_payment, tax_payment, construction_expenses, advertising_expenses, advisory_fees, business_insurance, insurance_claims, delivery_fees, service_charges, office_expenses, property_purchase, property_rental, royalty_fees, shares_investment, fund_investment, bill_payment, transportation_fees, salary_payment, reward_payment, influencer_payment, other_fees, other) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# PostPlan

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**r#type** | **Type** | The type of product the plan is for. (enum: remittance) | 
**bank_guid** | Option<**String**> | The unique identifier for the bank. | [optional]
**customer_guid** | Option<**String**> | The unique identifier for the customer. | [optional]
**source_account** | [**models::PostPlanSourceAccount**](PostPlanSourceAccount.md) |  | 
**destination_account** | [**models::PostPlanDestinationAccount**](PostPlanDestinationAccount.md) |  | 
**travel_rule_info** | Option<[**models::PostPlanTravelRuleInfo**](PostPlanTravelRuleInfo.md)> |  | [optional]
**purpose_of_transaction** | Option<**PurposeOfTransaction**> | The purpose of transaction for the plan. (enum: computer_services, family_support, education, gift, charitable_donation, medical_treatment, maintenance_expenses, travel, hotel_accommodation, small_value_remittance, liberalized_remittance, personal_transfer, loan_payment, tax_payment, construction_expenses, advertising_expenses, advisory_fees, business_insurance, insurance_claims, delivery_fees, service_charges, office_expenses, property_purchase, property_rental, royalty_fees, shares_investment, fund_investment, bill_payment, transportation_fees, salary_payment, reward_payment, influencer_payment, other_fees, other) | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



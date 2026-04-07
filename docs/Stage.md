# Stage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**guid** | **String** | The unique identifier for the stage. | 
**r#type** | **String** | The type of stage; one of payout. | 
**state** | **String** | The state of the stage; one of storing, planning, planned, executing, completed, or failed. | 
**failure_code** | Option<**String**> | The failure code for failed stages. | [optional]
**created_at** | **String** | The ISO8601 datetime the stage was created at. | 
**updated_at** | **String** | The ISO8601 datetime the stage was last updated at. | 
**source_account** | [**models::AccountAssociation**](AccountAssociation.md) |  | 
**destination_account** | [**models::AccountAssociation**](AccountAssociation.md) |  | 
**fees** | [**Vec<models::FeeAssociation>**](FeeAssociation.md) | The fees associated with the stage. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



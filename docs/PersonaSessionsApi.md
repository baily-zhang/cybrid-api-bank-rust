# \PersonaSessionsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_persona_session**](PersonaSessionsApi.md#create_persona_session) | **POST** /api/persona_sessions | Create Persona Session



## create_persona_session

> models::PersonaSession create_persona_session(post_persona_session)
Create Persona Session

Create a Persona session.  Required scope: **persona_sessions:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_persona_session** | [**PostPersonaSession**](PostPersonaSession.md) |  | [required] |

### Return type

[**models::PersonaSession**](PersonaSession.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


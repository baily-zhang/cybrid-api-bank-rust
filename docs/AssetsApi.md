# \AssetsApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_assets**](AssetsApi.md#list_assets) | **GET** /api/assets | Get assets list



## list_assets

> models::AssetList list_assets(page, per_page, code)
Get assets list

Retrieves a listing of assets.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**code** | Option<**String**> | Comma separated codes to list assets for. |  |

### Return type

[**models::AssetList**](AssetList.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


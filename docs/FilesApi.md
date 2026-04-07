# \FilesApi

All URIs are relative to *https://bank.sandbox.cybrid.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_file**](FilesApi.md#create_file) | **POST** /api/files | Create File
[**get_file**](FilesApi.md#get_file) | **GET** /api/files/{file_guid} | Get File
[**list_files**](FilesApi.md#list_files) | **GET** /api/files | List Files



## create_file

> models::PlatformFile create_file(post_file)
Create File

Creates a file.  #### This feature is currently in preview mode and is not yet available for partner use.  ## Data  The attribute contains the base64 encoded file content. The value needs to be smaller than 10MB otherwise the Platform will reject the request. To upload files larger than 10MB do not provide the content and use the returned upload URL to provide the file.  ## State  | State | Description | |-------|-------------| | storing | The Platform is storing the file in our private store | | completed | The Platform has completed storing the file | | failed | The Platform failed to store the file |    Required scope: **files:execute**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**post_file** | [**PostFile**](PostFile.md) |  | [required] |

### Return type

[**models::PlatformFile**](PlatformFile.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_file

> models::PlatformFile get_file(file_guid, include_download_url)
Get File

Retrieves a file.  Required scopes: **files:read,  files:pii:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**file_guid** | **String** | Identifier for the file. | [required] |
**include_download_url** | Option<**String**> | Include download information in response. Note, the files:pii:read scope is required if this parameter is set. |  |

### Return type

[**models::PlatformFile**](PlatformFile.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_files

> models::PlatformFileList list_files(page, per_page, guid, r#type, state, bank_guid, customer_guid)
List Files

Retrieves a list of files. Records are sorted by creation date in descending order.  Required scope: **files:read**

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**page** | Option<**i32**> | The page index to retrieve. |  |
**per_page** | Option<**i32**> | The number of entities per page to return. |  |
**guid** | Option<**String**> | Comma separated file_guids to list files for. |  |
**r#type** | Option<**String**> | Comma separated file types to list files for. |  |
**state** | Option<**String**> | Comma separated file states to list files for. |  |
**bank_guid** | Option<**String**> | Comma separated bank_guids to list files for. |  |
**customer_guid** | Option<**String**> | Comma separated customer_guids to list files for. |  |

### Return type

[**models::PlatformFileList**](PlatformFileList.md)

### Authorization

[oauth2](../README.md#oauth2), [BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


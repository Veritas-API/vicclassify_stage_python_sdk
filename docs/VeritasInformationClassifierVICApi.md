# swagger_client.VeritasInformationClassifierVICApi

All URIs are relative to *http://veritas-nonprod-stage.apigee.net/vic/v1/classification*

Method | HTTP request | Description
------------- | ------------- | -------------
[**classify**](VeritasInformationClassifierVICApi.md#classify) | **POST** /classify | Determine a document&#39;s classification(s)


# **classify**
> ClassificationResultCollection classify(tenant_id=tenant_id, policy_id=policy_id, policy=policy, metadata=metadata, metadata_file=metadata_file, document_name=document_name, include_matches=include_matches, max_content_matches_per_rule=max_content_matches_per_rule, skip_text_extraction=skip_text_extraction, skip_whitespace_collapse=skip_whitespace_collapse, file=file)

Determine a document's classification(s)

Classify a document using the specified policies or the tenant's default policies.   The document can be supplied by value (a stream of bytes) or by reference (a file path).  The document is automatically converted to text where required.   The classification results include the policies matched and suggested classification 'tags' that the caller may associate with the content.  Extra information can optionally be returned giving more details about the content that triggered the classification - this reduces performance but is useful for diagnostics.

### Example 
```python
from __future__ import print_statement
import time
import swagger_client
from swagger_client.rest import ApiException
from pprint import pprint

# Configure HTTP basic authorization: Bearer
swagger_client.configuration.username = 'YOUR_USERNAME'
swagger_client.configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = swagger_client.VeritasInformationClassifierVICApi()
tenant_id = 'tenant_id_example' # str | The tenant identifier (optional)
policy_id = ['policy_id_example'] # list[str] | One or more policies to use for the classification.  If not specified (and the 'policy' parameter is not specified), the tenant's default policies are used. (optional)
policy = 'policy_example' # str | A policy to use for the classification (json).  Normally the policies are specified by policyId, which is a reference to a stored policy.  However this option allows a policy to be supplied by value, which is useful (for example) for testing policies before storing them. (optional)
metadata = ['metadata_example'] # list[str] | One or more items of document metadata to use for classification (along with any content provided).   Each item of metadata is specified as a field/value pair separated by a colon, for example auth:Sue Bloggs.   Note that tools such as Swagger may send each field/value pair as a separate form part, but this is not necessary. It is more efficient to send each pair LF-delimited in a single form part. (optional)
metadata_file = 'metadata_file_example' # str | Full path to text file containing metadata to use for classification.  Each piece of metadata is specified as a field/value pair separated by a colon, for example auth:Sue Bloggs.  Multiple items of metadata are separated by a line feed (or CRLF). Multi-valued metadata must be specified as separate field/value pairs, for example recp:Sue\\nrecp:Bob.  The text MUST be UTF-8 or UTF-16LE.  The file SHOULD have a byte order mark indicating the encoding.  If the encoding cannot be determined, UTF-8 is assumed. (optional)
document_name = 'document_name_example' # str | The document name and extension or full path. If known should include at least name and/or . prefixed extension.   If not supplying the document content in the request body then the document's full and accessible path is required. (optional)
include_matches = true # bool | If true, the response contains details about the document matches used to determine the classification.  This may have a significant impact on classification performance. (optional)
max_content_matches_per_rule = 56 # int | The maximum number of content matches to include in the match details.   Only relevant if includeMatches is true.   This setting does not affect classification - it only affects the verbosity of the match information returned with the results. (optional)
skip_text_extraction = true # bool | If true, the content to classify is assumed to be text and no text extraction is performed.   **This optimization should only be used when the client is sure that the content is text.**   The text MUST be UTF-8 or UTF-16LE. If the content is specified by reference to a file, the file SHOULD have a byte order mark indicating the encoding.  If the encoding cannot be determined, UTF-8 is assumed. (optional)
skip_whitespace_collapse = true # bool | If true, the content to classify does not have its whitespace collapsed before classification.   **This optimization should only be used when the client is sure that whitespace has already been collapsed.**   Whitespace collapsing means that all sequences or two or more whitespace characters are replaced by a single space character.   This flag is only valid is skipTextExtraction is true. (optional)
file = '/path/to/file.txt' # file | The document's binary or text content. Optional when documentName is the document's full and accessible path.   If multiple files are specified, the first is considered the primary document and the remaining files as attachments. (optional)

try: 
    # Determine a document's classification(s)
    api_response = api_instance.classify(tenant_id=tenant_id, policy_id=policy_id, policy=policy, metadata=metadata, metadata_file=metadata_file, document_name=document_name, include_matches=include_matches, max_content_matches_per_rule=max_content_matches_per_rule, skip_text_extraction=skip_text_extraction, skip_whitespace_collapse=skip_whitespace_collapse, file=file)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling VeritasInformationClassifierVICApi->classify: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **tenant_id** | **str**| The tenant identifier | [optional] 
 **policy_id** | [**list[str]**](str.md)| One or more policies to use for the classification.  If not specified (and the &#39;policy&#39; parameter is not specified), the tenant&#39;s default policies are used. | [optional] 
 **policy** | **str**| A policy to use for the classification (json).  Normally the policies are specified by policyId, which is a reference to a stored policy.  However this option allows a policy to be supplied by value, which is useful (for example) for testing policies before storing them. | [optional] 
 **metadata** | [**list[str]**](str.md)| One or more items of document metadata to use for classification (along with any content provided).   Each item of metadata is specified as a field/value pair separated by a colon, for example auth:Sue Bloggs.   Note that tools such as Swagger may send each field/value pair as a separate form part, but this is not necessary. It is more efficient to send each pair LF-delimited in a single form part. | [optional] 
 **metadata_file** | **str**| Full path to text file containing metadata to use for classification.  Each piece of metadata is specified as a field/value pair separated by a colon, for example auth:Sue Bloggs.  Multiple items of metadata are separated by a line feed (or CRLF). Multi-valued metadata must be specified as separate field/value pairs, for example recp:Sue\\nrecp:Bob.  The text MUST be UTF-8 or UTF-16LE.  The file SHOULD have a byte order mark indicating the encoding.  If the encoding cannot be determined, UTF-8 is assumed. | [optional] 
 **document_name** | **str**| The document name and extension or full path. If known should include at least name and/or . prefixed extension.   If not supplying the document content in the request body then the document&#39;s full and accessible path is required. | [optional] 
 **include_matches** | **bool**| If true, the response contains details about the document matches used to determine the classification.  This may have a significant impact on classification performance. | [optional] 
 **max_content_matches_per_rule** | **int**| The maximum number of content matches to include in the match details.   Only relevant if includeMatches is true.   This setting does not affect classification - it only affects the verbosity of the match information returned with the results. | [optional] 
 **skip_text_extraction** | **bool**| If true, the content to classify is assumed to be text and no text extraction is performed.   **This optimization should only be used when the client is sure that the content is text.**   The text MUST be UTF-8 or UTF-16LE. If the content is specified by reference to a file, the file SHOULD have a byte order mark indicating the encoding.  If the encoding cannot be determined, UTF-8 is assumed. | [optional] 
 **skip_whitespace_collapse** | **bool**| If true, the content to classify does not have its whitespace collapsed before classification.   **This optimization should only be used when the client is sure that whitespace has already been collapsed.**   Whitespace collapsing means that all sequences or two or more whitespace characters are replaced by a single space character.   This flag is only valid is skipTextExtraction is true. | [optional] 
 **file** | **file**| The document&#39;s binary or text content. Optional when documentName is the document&#39;s full and accessible path.   If multiple files are specified, the first is considered the primary document and the remaining files as attachments. | [optional] 

### Return type

[**ClassificationResultCollection**](ClassificationResultCollection.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


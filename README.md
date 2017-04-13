# swagger_client
APIs

This Python package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: Resource Specific
- Package version: 1.0.0
- Build package: io.swagger.codegen.languages.PythonClientCodegen

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

If the python package is hosted on Github, you can install directly from Github

```sh
pip install git+https://github.com//.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com//.git`)

Then import the package:
```python
import swagger_client 
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import swagger_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
from __future__ import print_function
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

## Documentation for API Endpoints

All URIs are relative to *http://veritas-nonprod-stage.apigee.net/vic/v1/classification*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*VeritasInformationClassifierVICApi* | [**classify**](docs/VeritasInformationClassifierVICApi.md#classify) | **POST** /classify | Determine a document&#39;s classification(s)


## Documentation For Models

 - [ClassificationPolicy](docs/ClassificationPolicy.md)
 - [ClassificationResult](docs/ClassificationResult.md)
 - [ClassificationResultCollection](docs/ClassificationResultCollection.md)
 - [ContentMatch](docs/ContentMatch.md)
 - [ErrorResponse](docs/ErrorResponse.md)
 - [RuleMatch](docs/RuleMatch.md)
 - [Tag](docs/Tag.md)
 - [TagProperty](docs/TagProperty.md)


## Documentation For Authorization


## Bearer

- **Type**: HTTP basic authentication


## Author




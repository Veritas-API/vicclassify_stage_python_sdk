# ClassificationPolicy

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**policy_id** | **str** |  | [optional] 
**tags** | **list[str]** |  | [optional] 
**policy_hash** | **str** | A hash of the policy body and any associated custom patterns.  This can be used to track significant changes to the policy that may warrant re-classification of documents.  Note that built-in pattern bodies are NOT included in the hash, as they are not expected to change significantly over time. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



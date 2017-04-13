# ClassificationResult

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**policy_id** | **str** | The identity of the policy that was matched against. | [optional] 
**policy_name** | **str** | The name of the policy that was matched against. | [optional] 
**tags** | [**list[Tag]**](Tag.md) | Suggested tags to represent the policy match.  A client may want to attach the tags to the original document as a way of recording the classification result. | [optional] 
**rule_matches** | [**list[RuleMatch]**](RuleMatch.md) | Collection of rule matches giving details of how the classification was determined. Optional, so may not be populated. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



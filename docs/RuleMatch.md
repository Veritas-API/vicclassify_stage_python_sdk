# RuleMatch

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**rule_id** | **str** |  | [optional] 
**rule_name** | **str** |  | [optional] 
**confidence** | **float** | Confidence in the rule match, as a percentage.  A higher value means a higher likelihood that the content matches the intent of the rule. | [optional] 
**count** | **int** | The number of individual content matches within the rule match. | [optional] 
**content_matches** | [**list[ContentMatch]**](ContentMatch.md) | A collection of content matches within the overall rule match, if known.  May be empty for certain types of rule. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



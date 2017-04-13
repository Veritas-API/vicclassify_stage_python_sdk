# ContentMatch

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**offset** | **int** | The offset (in characters) of the match within the classified text.  The classified text is the text conversion of the original document, so this offset may not be directly usable by a client with only access to the original document. | [optional] 
**length** | **int** | The length of the content match, in characters. | [optional] 
**location** | **str** |  | [optional] 
**content** | **str** | Content that matched the rule (e.g. a word or phrase), where available. | [optional] 
**context** | **str** | The matching content with some surrounding context, where available. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# Migration from Language Understanding (LUIS) to conversational language understanding (CLU)
## Executive Summary
[Conversational Language Understanding (CLU)]() is one of the cloud-based API services offered by Azure Cognitive Services for Language. It is the newest generation of [Language Understanding Service (LUIS)]() and therefore offers backwards compatibility with previously created LUIS applications. CLU employs state-of-the-art machine-learning intelligence to allow users to build a custom natural language understanding model for the prediction of intents and entities of conversational utterances. 

CLU offers the following advantages over LUIS: 

1. Improved accuracy with state-of-the-art machine learning models for better intent classification and entity extraction. 
2. Multilingual support for model learning and training. 
3. Ease of integration with different CLU and [custom question answering]() projects using [orchestration workflow](), available on the [Language Studio](). 
4. The ability to add testing data easily within the experience using the Language Studio and APIs for model performance evaluation prior to deployment. 

To get started you can [create a new project]() or [import your LUIS application](). 

## Comparison between Language Understanding (LUIS) and conversational language understanding (CLU)
The following table presents a side-by-side comparison between the features of LUIS and CLU; additionally, it highlights the changes to your LUIS application after migrating to CLU.

|LUIS features | Conversational language understanding features | Post migration |
|:------------:|:----------------------------------------------:|:--------------:|
|ML, Structured ML, List, Prebuilt, Regex, Pattern.Any Entities|ML, List, and Prebuilt [entity components](faq2). Regex components to be available in October 2022.|ML (leaf nodes), List, and Prebuilt entities will be transferred as entities in CLU; other entity types will not be transferred.| 
|Single culture for each application|Multilingual model: multiple languages for each project (FAQ4)|The primary language of your project will be set as your LUIS application culture. Your project can be trained to extend to different languages.|
|Entity Roles  |Roles no longer needed (FAQ3)  | Entity Roles will be transferred as entities.|












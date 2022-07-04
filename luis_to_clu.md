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
|Normalize Punctuation, Normalize Diacritics, Normalize Word Form, Use All Training Data  |Settings no longer needed (FAQ6)  |Settings will not be transferred.  |
|Patterns and Phrase list features|Patterns and Phrase list features no longer needed. (FAQ6)|Patterns and Phrase list features will not be transferred.  |
|Entity features| Entity components (FAQ16)| List or Prebuilt entities added as features to an entity will be transferred as added components to that entity. Entity features will not be transferred for intents |
|Intents and utterances| Intents and utterances |All intents and utterances will be transferred; utterances will be labeled with their transferred entities. |
|Application GUIDs |Project names| A project will be created for each migrating application with the application name. |
|Versioning| Can only be stored locally, will be available in October 2022 (FAQ7)| A project will be created for the selected application version. |
|Evaluation using batch testing |Evaluation using testing sets| Uploading your testing dataset will be required.|  
|LUIS Authoring APIs| CLU Authoring APIs| Learn more on how to use the CLU authoring APIs.| 
|Role-Based Access Control (RBAC) for LUIS resources |Role-Based Access Control (RBAC) available for Language resources |Language resource RBAC must be manually added after migration. Learn more. |
|Single training mode| Standard and advanced training modes (FAQ14)| Training will be required after application migration. |
|Two publishing slots and version publishing |Ten deployment slots with custom naming|Deployment will be required after the application’s migration and training. |
|LUIS Authoring SDK support in .NET, Python, Java, and Node.js |Unavailable| Learn more on how to use the CLU authoring APIs. Refactoring will be necessary to use the CLU authoring APIs. |
|LUIS Runtime SDK support in .NET, Python, Java, and Node.js |CLU Runtime SDK support in .NET and Python| Learn more on how to use the CLU runtime SDKs and APIs. Refactoring will be necessary to use the CLU runtime API response. |

## Migration Steps for your LUIS Applications
You can choose to migrate your LUIS applications to the next generation service conversational language understanding programmatically using the Authoring APIs or using the LUIS portal.  

Follow these steps to begin migration using the LUIS Portal: 

1. After logging into luis.ai, click the button on the banner, shown below, to launch the migration wizard or select your LUIS applications from your library and use the migrate button, shown below to begin migrating your applications. Please note that migration will only copy your selected LUIS applications. 
2. The migration overview tab, shown below, provides a brief explanation of conversational language understanding and its benefits. Press Next to proceed.  
3. The next step is to determine the Language resource that you wish to migrate your LUIS application to. If you have already created your Language resource, proceed by first selecting your Azure subscription followed by your Language resource and then press Next, highlighted in the figure below. If you have not previously created your Language resource, click the link to Create a new Language resource, follow the guide. Afterwards, select your options as previously mentioned then press Next. 
4. Select all your LUIS applications that you wish to migrate as well as specify each of their versions and then press Next. Note that if any of your LUIS application names are not supported by Conversational language understanding, you will be prompted to change them. After selecting your application and version, you will be prompted with a message informing you of any features your LUIS application has that will not be carried over, as shown in the figure below. 
5. Once you have completed all the steps (1-4), you can review your Language resource and LUIS applications selections. Press Finish and migrate once you have completed your review. 
6. A popup window, shown below, will allow you to track the migration status of your applications. Applications that have not started migrating will have a status of “Not started”. Applications that have begun migrating will have a status of “In progress” and once they have finished migrating their status will be converted to “Succeeded”. An application status that returns “Failed” means that you must repeat its migration process following steps (1-5). Once the migration has completed for all applications, press Done to move on to Next Steps. 
7. Next steps: 
a.Train your model 
b.Deploy your model 
c.Call your deployed model  

Follow these steps to begin migration programmatically using the CLU Authoring APIs: 

1. Export your LUIS application in JSON format. You can use the LUIS Portal to export your applications or via the LUIS Programmatic APIs.  

2. Import a LUIS application JSON file into Conversational Language Understanding using the CLU authoring REST APIs: 


























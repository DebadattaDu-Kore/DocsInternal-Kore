# **Intent Discovery (Beta)**

The new Intent Discovery module helps you auto-extract popular intents from previous user conversations. It reduces the time and effort to build a virtual assistant and leads to the success of your Conversational AI Journey. This is a beta feature and is available only for the English language and Enterprise users.

You can upload your historical transcripts in CSV format. After the transcripts are uploaded into the bot, the bot uses LLMs to identify the different topics, intents, or conversations between the user and the bot. It intelligently identifies all the intents available. You can review each intent to understand which conversations have resulted in identifying these intents. After the review, you can also see the underline utterances that resulted in identifying an intent. You can either add these intents as new intents for your virtual assistant or pick specific utterances and train them as utterances for your existing dialogs and FAQs. So, it helps both ways – either create new intents or enhance the training you provide to your virtual assistant.

![alt_text](../assets/images/intent-discovery/intent-discovery-intro.png)

The Intent Discovery journey consists of the following steps:

1. [Create a Project](#create-a-project): You may have many business use cases to automate. Projects help manage intent discovery for each business use case separately – a project for a specific use case.
2. [Upload Transcripts](#upload-transcripts): Upload your use case-specific historical transcripts in CSV format. Conversations are extracted from the uploaded transcripts.
3. [Extract Intents:](#extract-intents) Intents and training data are extracted from the conversations.
4. [Train the Utterances](#train-the-utterances) to create new intents or add them as training data: You can add new intents as dialogs or FAQs or train them for existing dialogs or FAQs.

## Create a Project

1. Go to **Build > Tools > Intent Discovery**.

![alt_text](../assets/images/intent-discovery/create-project.png)

2. Click the **Create Project** button.
3. Enter a name and a brief description of the project. Note that the character limit for Project Name is 256, and Description is 1000. Click **Proceed**. 

![alt_text](../assets/images/intent-discovery/enter-project-name-and-desc.png)

The new project is created. You see the Intent Discovery page with the header ‘Projects / {{New Project’s Name}}’.

![alt_text](../assets/images/intent-discovery/upload-transcript.png)

The Intent Discovery landing page lists all the projects with conversational insights for each project, such as the status of the project, number of sessions, intents extracted, and results in terms of added dialogs, added FAQs, trained dialogs, and trained FAQs. Note that the result will be NA for the projects for which intent extraction is incomplete.

The status of a project can be any of the following, displayed in the Status column:

* No Files Uploaded
* Intents Not Extracted
* Intent Extraction In Progress
* Intents Extracted

![alt_text](../assets/images/intent-discovery/intent-discovery-page.png)

**Note**: You can create **a maximum of 10 projects** per VA. You can change an existing project’s name and description anytime.

## Upload Transcripts

On the Intent Discovery page for the new project, you can see a button to initiate the upload of the transcript file(s) and a link to download a sample transcript file.

![alt_text](../assets/images/intent-discovery/upload-transcript.png)

You can download the sample CSV file by clicking the link. Ensure to upload transcripts in the format specified in the sample file. Please note that **all the columns in the file must be filled**.

### Format of the CSV (Transcript) file

![alt_text](../assets/images/intent-discovery/sample-csv-file.png)


<table>
  <tr>
   <td>FIELD NAME
   </td>
   <td>DESCRIPTION
   </td>
  </tr>
  <tr>
   <td>Id
   </td>
   <td>The session ID of the conversation. (For all the conversations in a session, the Id must be the same.)
   </td>
  </tr>
  <tr>
   <td>Sender ID
   </td>
   <td>The ID of the bot or agent.  
   </td>
  </tr>
  <tr>
   <td>Other Party ID
   </td>
   <td>The ID of the user talking to the bot or agent.
   </td>
  </tr>
  <tr>
   <td>Direction
   </td>
   <td>The message direction – in (user input) or out (bot/agent response).
   </td>
  </tr>
  <tr>
   <td>Message
   </td>
   <td>The message shown to the user or the bot/agent, depending on the message direction.
   </td>
  </tr>
  <tr>
   <td>Message Type
   </td>
   <td>Format in which the message is sent or received – text/html.
   </td>
  </tr>
  <tr>
   <td>Created on
   </td>
   <td>Date & time on which the message is sent or received.
   </td>
  </tr>
</table>

### Limitations

* Number of transcripts files allowed: Up to 5 CSV files per project.
* Maximum size of CSV transcript file: 1MB each


### Steps to upload the transcripts:

1. Click the **Upload Transcript** button, and then browse and select the transcripts files (CSV format). The selected files are uploaded, and you see a prompt to manage the transcripts on the next page.


![alt_text](../assets/images/intent-discovery/browse-for-transcript.png)


![alt_text](../assets/images/intent-discovery/upload-transcript-confirmation.png)

If some transcript files are uploaded but No intents extracted so far, the** Manage Transcripts** button is displayed as shown in the screenshot below.

![alt_text](../assets/images/intent-discovery/manage-transcripts.png)


2. On clicking **Manage Transcripts**, you can see the **Transcripts** dialog box with the list of all the transcript files. Below details are displayed on the window:
    1. File Name: Name of the transcript file uploaded
    2. Upload Time: Time of transcript upload
    3. Sessions: Count of sessions in the transcript, gets populated after the successful extraction of conversations. 
    4. Status, which can be one of the following:
        * Conv. Extraction In-progress: 
        * Conversations Extracted
        * Intents Extracted
        * Invalid File
        * Upload Failed



![alt_text](../assets/images/intent-discovery/transcript-list.png)


The dialog box has the provision to download a sample file using the **Sample File** button and upload additional transcript files by clicking the **Upload Transcripts** button.


### View Conversations in the Transcript

Upon successful upload of the transcript(s), the platform extracts the conversations from the uploaded files. You can view all the conversations, and the chat messages exchanged between the end user and the VA/agent.

The platform displays the conversation session summary, which includes the count of the VA messages and user messages. You need to select a **Date Filter** under **Contents** to display the details.


![alt_text](../assets/images/intent-discovery/conversation-in-transcript.png)


If a conversation is not useful or is not contributing to the intent, you can delete the specific conversation. Deleting a conversation also impacts the conversation count and average message count in the columns.


### Delete Transcripts

You can delete the uploaded transcript file if the file is not required anymore, in case the upload was incorrect, or if the conversation has been extracted but the file is not useful.

On hovering any row, the** delete** icon is displayed, which is used to delete that specific Transcript.



![alt_text](../assets/images/intent-discovery/delete-transcript.png)



## Extract Intents

The next step is intent extraction. 

On clicking the **Extract Intents** button on the Transcripts dialog box, you can see a message about intents being extracted. This process may take a few minutes depending on the number and size of the transcript files.

In case the status of one or more transcript files is **Conv. Extraction In-Progress**, you can still initiate intent extraction. In that case, conversation extraction from those transcript files runs in the background, and once that is complete, intent extraction will begin.



![alt_text](../assets/images/intent-discovery/intent-extraction-in-progress.png)


After the intent extraction is completed, you can see the list of extracted intents along with session count, qualified utterances, and actions.



![alt_text](../assets/images/intent-discovery/intents-extracted.png)


You can view the details of the intent action by clicking the **View** icon under the Actions column next to the text.


![alt_text](../assets/images/intent-discovery/click-view-on-intent.png)

![alt_text](../assets/images/intent-discovery/view-intent-activity.png)


### Extracted Intent Details

Clicking anywhere on the extracted Intents row displays a pop-up dialog box to view the details of the extracted Intent. The title of the dialog box is the extracted Intent name.

![alt_text](../assets/images/intent-discovery/extracted-intent-details-slider.png)


The dialog box shows a table with individual rows for each session. The table has below columns: 



* Session ID: The session ID and the Date and Time of the Session.
* Utterances: The list of utterances qualifying the extracted Intent. 
    * The platform shows only 3 utterances per session (row). The remaining count of the utterances is shown as a chip. 
    * On clicking the chip, you see all the utterances for the corresponding session.
    * You can **bookmark **the utterances.
* Status: A dropdown that shows whether the session item has been reviewed. By default, it  shows **Yet to Review**. You can change it to **Reviewed**.
* **View Transcripts** action button: This button is present in the Status column of each row, next to the drop-down. It helps you view the detailed conversion of the Session. On clicking the icon, a new pop-up, **Session Details dialog box**, appears.


A **Status** dropdown is also displayed at the top of the dialog box to mark the status of sessions as **Reviewed** or **Yet to Review**. You can bulk-select sessions and change the status using this option.


### Session Details

This dialog box, titled **Transcript,** shows the summary of the session. The detailed chat is displayed below the summary.


![alt_text](../assets/images/intent-discovery/session-summary.png)



## Train the Utterances

In a scenario where the utterances cannot be mapped to the existing intents, you can create a new intent.

Once the intents are listed, you can perform the following actions for the intents:



* Add a new Dialog Task or FAQ
* Train them for an existing Dialog Task or FAQ
* Change the status of utterances


### Add a new Dialog Task intent



1. Click the **Add/Train** dropdown across the intent, then select the **Dialog Task** option under **Add**. The **Add Dialog Task** dialog box for the intent is displayed. 
2. Provide a name and description for the new intent. 
3. All the utterances qualified for the extracted intent are displayed in a table. The bookmark icon appears if you have bookmarked this utterance in the [Extracted Intent Details](#extracted-intent-details) dialog box. 
4. Select all the required utterances and click the **Add to Bot** button. A confirmation message is shown on adding a new Dialog Task.




![alt_text](../assets/images/intent-discovery/add-dialog-task-st1.png)




![alt_text](../assets//images/intent-discovery/add-dialog-task-st2.png)


The **Actions** column text for the intent will reflect the addition of a dialog task. 

For example:



* If **Added ‘n’ new Dialog Tasks** text/tag is existing, then the count increases by 1. For example: **Added 1 new Dialog Task** will be changed to **Added 2 new Dialog Tasks**.
* If there are no intents created so far, then the text becomes **Added 1 new Dialog Task**. 

Additionally, this  change will reflect under the **Results** column against the project name on the Intent Discovery homepage.

For example:



* If **Added ‘n’ new Dialog Tasks** tag/text is existing, then the count is increased by 1. For example: **Added 1 new Dialog Tasks** will be changed to **Added 2 new Dialog Tasks.**
* If there are no Dialog tasks created so far, then the text becomes  **Added 1 new Dialog Task**.


### Train a Dialog task



1. Click the **Add/Train** dropdown across the intent, then select the **Dialog Task** option under **Train**. The **Train Dialog Task** dialog box for the intent is displayed.
2. Select the dialog task to be trained from the **Intent** drop-down and select all the required utterances from the table below. Click **Add Utterances**.




![alt_text](../assets/images/intent-discovery/train-dialog-task-st1.png)




![alt_text](../assets/images/intent-discovery/train-dialog-task-st2.png)




3. Once the existing Dialog task is trained with the selected Utterances, a confirmation message is shown.




![alt_text](../assets/images/intent-discovery/train-dialog-task-st3.png)


The **Actions** column text for the intent will reflect the training of a new dialog task. 

For example:



* If **Trained ‘n’ new Dialog Tasks** text/tag is existing, then increase the count by 1. For example: **Trained 1 new Dialog Task** will be changed to **Trained 2 new Dialog Tasks.**
* If there are no intents created so far, then append the text with **Trained 1 new Dialog Task**.

Additionally, this change will reflect under the **Results** column against the project name on the Intent Discovery homepage.

For example:



* If **Trained ‘n’ new Dialog Tasks** tag/text is existing, then increase the count by 1. For example: **Trained 1 new Dialog Tasks** will be changed to **Trained 2 new Dialog Tasks**.
* If there are no Dialog Tasks trained so far, then append the text with **Trained 1 new Dialog Task**.


### Add a new FAQ intent



1. Click the **Add/Train **dropdown across the intent, then select the **FAQ** option under **Add**. The **Add FAQ **dialog box for the intent is displayed. 
2. Provide a name and description for the new intent. 
3. All the Utterances qualified for the Extracted Intent are displayed in a table. The bookmark icon appears if the user has bookmarked this utterance in the Session summary dialog box. 
4. Select all the required utterances and click **Next**.



![alt_text](../assets/images/intent-discovery/add-faq-st1.png)




5. On the next dialog box, provide the FAQ question text to be created as an FAQ, along with the required Bot Response to be shown. All the selected utterances from the previous screen are added as alternative questions for this FAQ. 
6. Provide or select other features of the FAQ, like Bot response channel, Display name, reference ID, etc. as per your need and preference, and click the **Add to Bot** button. 



![alt_text](../assets/images/intent-discovery/add-faq-st2.png)


A confirmation message is shown on adding a new FAQ. 




![alt_text](../assets/images/intent-discovery/add-faq-st3.png)


The **Actions** column text for the intent will reflect the addition of an FAQ. 

For example:



* If **Added ‘n’ new FAQs** text/tag is existing, then the count increases by 1. For example:** Added 1 new FAQ** will be changed to **Added 2 new FAQs**.
* If there are no intents created so far, then the text becomes **Added 1 new FAQ**. 

Additionally, the adding will reflect under the **Results** column against the project name on the Intent Discovery homepage.

For example:



* If **Added ‘n’ new FAQs** tag/text is existing, then the count increases by 1. For example: **Added 1 new FAQs** will be changed to **Added 2 new FAQs**.
* If there are no Dialog tasks created so far, then the text becomes **Added 1 new FAQ**. 


### Train an FAQ



1. Click the **Add/Train** dropdown across the intent, then select the **FAQ** option under **Train**. The **Train FAQ** dialog box for the intent is displayed.
2. Select the FAQ to be trained from the **FAQ** drop-down. A label box showing the current Bot Response appears. Select all the required utterances from the table below and click **Add Utterances**.

![alt_text](../assets/images/intent-discovery/train-faq-st1.png)




3. Once the existing FAQ is trained with the selected Utterances, a confirmation message is shown.


![alt_text](../assets/images/intent-discovery/train-faq-st2.png)


The **Actions** column text for the intent will reflect the training of an FAQ. 

For example:



* If **Trained ‘n’ new FAQs** text/tag is existing, then the count increases by 1. For example: **Trained 1 new FAQ** will be changed to **Trained 2 new FAQs**.
* If there are no intents created so far, then the text becomes **Trained 1 new FAQ**.

Additionally, the training will reflect under the **Results** column against the project name on the Intent Discovery homepage.

For example:



* If **Trained ‘n’ new FAQs** tag/text is existing, then the count increases by 1. For example: **Trained 1 new FAQs** will be changed to **Trained 2 new FAQs**.
* If there are no Dialog tasks created so far, then the text becomes **Trained 1 new FAQ**. 


### Change the status of utterances

You can change the status of utterances between **Yet to Review** and **Reviewed**  on the [Extracted Intent Details](#extracted-intent-details) dialog box. You can change the status of one or multiple utterances in a go as per requirement.


## Reusing an existing project

There may be instances where you may need additional intents in an existing project and can achieve the same by adding transcript files to the project. The steps to upload additional transcript files are the same as uploading transcripts to a new project. Intent extraction can be performed multiple times based on need. For example, if, after having extracted intents previously, there is a need to add more intents, you can upload additional transcripts and extract intents again. Also, existing but no longer relevant transcript files can be deleted from a project. These two features ensure that an existing project becomes reusable.

The number of files and the file size limitations remain the same.

Uploading new transcript files will cause deletion of below data from the project:



* Extracted intents
* Summaries generated
* Utterances segregated for each session
* Status flag for each session
* Bookmarks of the utterances

Please note that the previously loaded transcript files will not be deleted while uploading new ones. Re-extraction of intents will restore the above-deleted project data.


## Deleting a project

You can also delete the project if it is no longer required. Since a maximum of 10 projects can be created within a bot, you may need to delete a past, unwanted project to make a place for a new one.


![alt_text](../assets/images/intent-discovery/delete-project.png)

![alt_text](../assets/images/intent-discovery/project-delete-confirmation.png)


When you delete a project, all the corresponding data in the project is automatically deleted, which includes: 



* Transcripts 
* Extracted intents
* Summaries generated
* Utterances segregated for each session
* Status flag for each session
* Bookmarks of the utterances

**Note**: Deletion of a project will have no impact on the Dialog Tasks/FAQ’s that have been trained using the intents extracted from the deleted projects.** **

# **Dashboard Filters**

The dashboard filters are used to filter and view the analytics data for virtual assistants (VAs) on the following dashboards in the **ANALYTICS** section based on the user’s selection(s):



* Overview Dashboard
* Conversations Dashboard
* Users Dashboard
* Performance Dashboard
* NLP Insights
* Conversation Insights
* Conversations History
* Conversation Flows
* Task Execution Logs
* Feedback Dashboard

<img src="../images/list-of-filters.png" alt="List of Filters" title="List of Filters" style="border: 1px solid gray; zoom:80%;">


To understand the filter criteria availability on different dashboards, see the Filter Criteria Matrix.

!!! note

    By default, the VA dashboard displays data for the past 24 hours.


## Filter Criteria Descriptions

The following table describes all the filter criteria available on the Kore.ai XO platform:


<table>
  <tr>
   <td><strong>FILTER</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Date</strong>
   </td>
   <td>Select a specific period to display all the conversations that occurred during the period. The date format is <strong>MM-DD-YYYY</strong>. The following filter criteria are available for the date filter:
<ul>

<li><strong>24 Hours</strong> – Data aggregated immediately preceding 24 hours is displayed. This is the default setting.

<li><strong>7 Days</strong> – Data aggregated over the past seven days is displayed. The start date is the day you select from which this filter is applied. By default, the current day is set as the start date, which you can change.

<li><strong>Custom</strong> – You can choose a custom date range to filter the records. Choose the start date and end date in the calendar and click the <strong>Select</strong> button to filter the records. The Platform stores only the latest six months of data, and you can apply the date filter only for this date range.
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td><strong>Conversation Type</strong>
   </td>
   <td>The data on the relevant dashboard is displayed based on the interactive or non-interactive conversation type. Learn more.  
   
<p>
The Developer Interactions are not included in the Conversation Type filter.
   </td>
  </tr>
  <tr>
   <td><strong>Conversation Status</strong>
   </td>
   <td>The dashboard data is displayed based on the following conversation statuses:
<ul>

<li><strong>Active Conversations</strong>: These are the ongoing conversations where the users interact with the VA.

<li><strong>Closed Conversations</strong>: These are the conversations where an active session between the VA and the customer has ended. Learn more.
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td><strong>UserID</strong>
   </td>
   <td>The UserID of the end-user related to the conversation. The following filter options are available:
<ul>

<li><strong>Kore User ID </strong>– This User ID is generated by the platform when the user registers; or

<li><strong>Channel User ID</strong> – Email address of the user as received from the channels. Developer interactions are available under Channel User ID. \
For ‘Enterprise Bots’, the email address (kore registered email address) is available under Channel ID.

<p>
You can select the user ID from the populate drop-down after you enter the first three alphabets of the user ID.
<p>
You can choose to either <strong>Include</strong> or <strong>Exclude</strong> the selected user ID.
<p>
Channel-specific ids are shown only for the users who have interacted with the VA during the selected period.
</li>
</ul>
   </td>
  </tr>
  <tr>
   <td><strong>Languages</strong>
   </td>
   <td>If it is a multi-lingual VA, you can select specific languages to filter the conversations that occurred in those languages. The page shows the conversations that occurred in all enabled languages by default.
<p>
This criterion is <strong>not available for the Performance tab </strong>of NLP Insights.
   </td>
  </tr>
  <tr>
   <td><strong>Channels</strong>
   </td>
   <td>When the VA is published in multiple channels, select this filter to view the data for various channels enabled for the VA.
<p>
The conversations that occurred in all enabled channels are displayed by default.
   </td>
  </tr>
  <tr>
   <td><strong>Task/Intent</strong>
   </td>
   <td>Select specific tasks or intents to filter the conversation related to those tasks or intents. The page shows the conversations related to all tasks or intents by default.
<p>
This criterion is<strong> not available for the Intent Not Found tab</strong> of NLP Insights.
   </td>
  </tr>
  <tr>
   <td><strong>Utterance Type</strong>
   </td>
   <td>Select the <strong>Trained </strong>option to filter the conversations that only contain trained utterances to the VA.
<p>
To view the conversations that contain untrained utterances, click <strong>Not Trained</strong>. By default, this filter shows the conversations’ data related to both Trained and Not Trained utterances.
<p>
This criterion is<strong> available only for the Intent Found tab</strong> of NLP Insights.
   </td>
  </tr>
  <tr>
   <td><strong>Utterance Status</strong>
   </td>
   <td>The dashboard data is filtered based on the utterance status, <strong>Reviewed</strong> or <strong>Yet to be Reviewed</strong>.
   </td>
  </tr>
  <tr>
   <td><strong>Intent Type</strong>
   </td>
   <td>The dashboard data is filtered based on the conversation skill – <strong>Dialog Tasks, FAQs</strong>, or <strong>Small Talks.</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Dialog Tasks</strong>
   </td>
   <td>The dashboard data is filtered based on the selection of available Dialog Tasks in the <strong>Dialog Tasks</strong> drop-down.
   </td>
  </tr>
  <tr>
   <td><strong>Ambiguous</strong>
   </td>
   <td>Select the <strong>Show Ambiguous</strong> option to filter the conversations that identify multiple tasks or intents and the user is asked to choose from the presented options.
<p>
This criterion is <strong>available only for the Intent Not Found tab</strong> of NLP Insights.
   </td>
  </tr>
  <tr>
   <td><strong>Developer Interactions</strong>
   </td>
   <td>Select ‘<em>Include Developer Interactions</em>’, to include developer interactions in the results. By default, the developer interactions aren’t included. 
<p>
Developers include both the VA owners and shared developers.
   </td>
  </tr>
  <tr>
   <td><strong>Custom Tags</strong>
   </td>
   <td>Select the specific custom tags to filter the records based on the meta-information, session data, and filter criteria. You can add these tags at three levels:
<ul>

<li><strong>User Level</strong>: These tags can be added to the user information.

<li><strong>Message Level</strong>: These tags can be added to the message of the current node. If the current node is not associated with a message, then the tag gets added to the immediate previous node that has a message associated with it.

<li><strong>Session Level</strong>: These tags can be added at the current session of the user.

<p>
You can set the criterion as either <strong><em>Contain</em></strong> or <strong><em>Does Not Contain </em></strong>the specified value.
<p>
This criterion is <strong>not available for the Debug Logs tab</strong> of NLP Insights.
<p>
You can define Tags as key-value pairs from Script written anywhere in the application like Script node, Message, Entity, Confirmation prompts, Error prompts, Knowledge Graph responses, BotKit SDK, etc.
<p>
The following script can be used for adding meta tags:
<ul>

<li>To add a User level tag: \
tags.addUserLevelTag(“tagname”,”tagvalue”)

<li>To add a Session level tag: \
tags.addSessionLevelTag(“tagname”,”tagvalue”)

<li>To add the Message level tag: \
tags.addMessageLevelTag(“tagname”,”tagvalue”)
</li>
</ul>
</li>
</ul>
   </td>
  </tr>
</table>


!!! note

    To see the filter criteria from UserID till Custom Tags listed in the preceding table, click the More Filters drop-down.


<img src="../images/more-filters-drop-down.png" alt="More Filters drop-down" title="More Filters drop-down" style="border: 1px solid gray; zoom:80%;">



## Filter Criteria Matrix

The following matrix shows the availability of filter criteria on different dashboards and their default values:


<table>
  <tr>
   <td><strong>FILTER TYPE</strong>
   </td>
   <td><strong>OVERVIEW</strong>
<p>
<strong>DASHBOARD</strong>
   </td>
   <td><strong>CONVERSATION</strong>
<p>
<strong>DASHBOARD</strong>
   </td>
   <td><strong>USERS</strong>
<p>
<strong>DASHBOARD</strong>
   </td>
   <td><strong>PERFORMANCE</strong>
<p>
<strong>DASHBOARD</strong>
   </td>
   <td><strong>CONVERSATIONS HISTORY DASHBOARD</strong>
   </td>
   <td><strong>NLP INSIGHTS</strong>
   </td>
   <td><strong>CONVERSATIONAL INSIGHTS</strong>
   </td>
   <td><strong>DEFAULT</strong>
<p>
<strong>VALUE</strong>
   </td>
  </tr>
  <tr>
   <td>Date Period
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>24 Hours
   </td>
  </tr>
  <tr>
   <td>Conversation Type
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>Interactive
   </td>
  </tr>
  <tr>
   <td>Conversation Status
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>Closed
   </td>
  </tr>
  <tr>
   <td>Channels
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>ALL
   </td>
  </tr>
  <tr>
   <td>Custom Tags
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>None
   </td>
  </tr>
  <tr>
   <td>Language
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>ALL
   </td>
  </tr>
  <tr>
   <td>UserID
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>✔
   </td>
   <td>X
   </td>
   <td>None
   </td>
  </tr>
  <tr>
   <td>Task / Intent
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>✔
   </td>
   <td>✔
   </td>
   <td>None
   </td>
  </tr>
  <tr>
   <td>Utterance Type
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>✔
   </td>
   <td>X
   </td>
   <td>Both
   </td>
  </tr>
  <tr>
   <td>Developer Interactions
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>✔
   </td>
   <td>X
   </td>
   <td>Checked
   </td>
  </tr>
  <tr>
   <td>Utterance Status
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>✔
   </td>
   <td>Both
   </td>
  </tr>
  <tr>
   <td>Intent Type
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>X
   </td>
   <td>✔
   </td>
   <td>Dialog Tasks
   </td>
  </tr>
</table>
# **Import Bot as a New Bot API**

To create a new bot in the account owner’s Builder Tool using the _File IDs_ generated when uploading the files to the local server.

Please refer to the [Upload File API](https://developer.kore.ai/docs/bots/api-guide/upload-file-api/) for uploading and obtaining the **_File Id_**.

!!! note
    The API requires the JWT generated by an application created only from the **Bot Admin Console**.


<table>
  <tr>
   <td><strong>Method</strong>
   </td>
   <td>POST
   </td>
  </tr>
  <tr>
   <td><strong>Endpoint</strong>
   </td>
   <td><code>https://{{host}}/api/public/bot/import</code>
   </td>
  </tr>
  <tr>
   <td><strong>Content Type</strong>
   </td>
   <td><code>application/json</code>
   </td>
  </tr>
  <tr>
   <td><strong>Authorization</strong>
   </td>
   <td><code>auth: {{JWT}}</code>
<p>
See <a href="https://developer.kore.ai/docs/bots/api-guide/apis/#Generating_the_JWT_Token">How to generate the JWT Token</a>.
   </td>
  </tr>
  <tr>
   <td><strong>API Scope</strong>
   </td>
   <td>
<ul>

<li>Bot Builder: Not Applicable

<li>Admin Console: Bot Definition > Bot Import
</li>
</ul>
   </td>
  </tr>
</table>


## Query Parameters

<table>
  <tr>
   <td><strong>PARAMETER</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
   <td><strong>MANDATE</strong>
   </td>
  </tr>
  <tr>
   <td>host
   </td>
   <td>The environment URL. For example, <code>https://bots.kore.ai</code>
   </td>
   <td>Required
   </td>
  </tr>
</table>

## Sample Request

```json
curl -X POST \
  https://{{host}}/api/public/bot/import \
  -H 'auth: {{YOUR_JWT_ACCESS_TOKEN}}' \
   -H 'content-type: application/json' \
   -d '{
  "botDefinition" : "5bxxxxxxxxxxx4f9",
  "configInfo" : "5bxxxxxxxxxxxxx4fa",
  "botFunctions":["5bxxxxxxxxxxxxxea6"],
  "icon":"5bxxxxxxxxxxxxxxxx4fb"
}'
```

## Body Parameters


<table>
  <tr>
   <td><strong>PARAMETER</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
   <td><strong>MANDATE</strong>
   </td>
  </tr>
  <tr>
   <td><strong>botDefinition</strong>
   </td>
   <td>“Bot definition file id”
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td><strong>configInfo</strong>
   </td>
   <td>“Bot configuration file id”
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td><strong>botFunctions</strong>
   </td>
   <td>“Bot functions File id”
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td><strong>icon</strong>
   </td>
   <td>“Bot icon File id”
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td><strong>name</strong>
   </td>
   <td>“Bot name”
<p>
– If not provided, it is fetched from the existing bot’s copy.
   </td>
   <td>Optional
   </td>
  </tr>
  <tr>
   <td><strong>purpose</strong>
   </td>
   <td>“customer”/”employee”
<p>
– If not provided, it is fetched from the existing bot’s copy.
   </td>
   <td>Optional
   </td>
  </tr>
</table>

## Sample Response

```json
{
    "status": "pending",
    ""streamId": "st-xxxxx-xxx-xxx-xxx-xxxxx",
    "statusLogs": [
        {
            "taskType": "importRequest",
            "taskName": "Welcome",
            "status": "success"
        }
    ],
    "createdBy": "u-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    "requestType": "Botimport",
    "bir": "bir-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "createdOn": "2022-07-29T07:24:17.496Z",
    "__v": 0
}
```
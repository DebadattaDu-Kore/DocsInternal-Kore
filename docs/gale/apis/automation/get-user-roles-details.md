# Get User Roles Details API

To get complete information of all the users and their associated roles in the account.


!!!note
    This API requires JWT generated by an application created only from the Bot Admin Console.


<table>
  <tr>
   <td><strong>Method</strong>
   </td>
   <td>GET
   </td>
  </tr>
  <tr>
   <td><strong>Endpoint</strong>
   </td>
   <td><code>https://{{host}}/api/public/alluserroles?</code>
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
See <a href="https://developer.kore.ai/docs/bots/api-guide/apis/#Generating_the_JWT_Token">How to generate the JWT Token.</a>
   </td>
  </tr>
  <tr>
   <td><strong>API Scope</strong>
   </td>
   <td>
<ul>

<li>Bot Builder: Not Applicable

<li>Admin Console: Profile Management > Role Management
</li>
</ul>
   </td>
  </tr>
</table>


 


## Path Parameters


<table>
  <tr>
   <td><strong>PARAMETER</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
  </tr>
  <tr>
   <td>host
   </td>
   <td>Environment URL, for example, https://bots.kore.ai
   </td>
  </tr>
</table>


 


## Sample Request


```json
curl -X GET \   
  https://{{host}}/api/public/alluserroles?limit=2' \
  -H 'auth: {{YOUR_JWT_ACCESS_TOKEN}}' \
```


 


## Sample Response


```json
{
    "total": 10,
    "availableMore": true,
    "users": [
        {
            "username": "<name>@kore.com",
            "orgUserId": "org assigned user id",
            "accountId": "<id>",
            "isDeveloper": true,
            "canCreateBot": true,
            "userId": "u-xxx-xxx-xxx-xxx-xxxxx",
            "btRoles": [],
            "adminRoles": []
        },
        {
            "username": "<name>@kore.com",
            "orgUserId": "org assigned user id",
            "accountId": "<id>",
            "isDeveloper": true,
            "canCreateBot": true,
            "userId": "u-xxxxx-xxx-xxx-xxx-xxxxx",
            "btRoles": [
                {
                    "roleId": "5c04ae921ad9976d311e9b50",
                    "roleName": "Bot Developer",
                    "groups": [],
                    "botId": "st-fd7c7396-82c1-5916-972d-6bfe6908b5ab",
                    "botName": "Example Bot"
                }
            ],
            "adminRoles": []
        }
    ]
}
```
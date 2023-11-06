# **Adding Glip by RingCentral as a Channel**

The Kore.ai XO Platform now allows you to add **Glip by RingCentral** as a messaging channel to your Virtual Assistants (VAs).

With the **Glip** integration, you can achieve the following:



* Configure the **Glip Sandbox** account for testing the integration.
* Set up the _REST API_ and the authorization flow for events and conversations.
* Enable **Webhook Subscriptions**, **Read Accounts**, and **Team Messaging API** permissions.
* Link the app to the Kore.ai XO Platform using the app’s credentials.
* Authorize the VA for the existing/new **Glip Sandbox** account user.

After the integration, you can do the following:


* Keep track of virtual assistant conversations.
* Listen to new messages from Glip or other sources.
* Have VAs post and respond to messages in Glip conversations.
* Have VAs handle incoming notifications from your apps into Glip teams so you don’t have to check different sites for updates.

To start the integration, you must register an application on RingCentral to gain access to the API and to integrate RingCentral into the Kore.ai XO Platform. To set up **Glip** as a channel, you must create an app in **[RingCentral’s Developer Portal](https://developers.ringcentral.com/)** and enable a **webhook** for the platform to receive messages.

The steps to add the channel are summarized below:


1. [Create a RingCentral App](https://developer.kore.ai/docs/bots/channel-enablement/adding-ringcentral-glip-channel/#Step_1_Create_a_RingCentral_App)
2. [App Set Up on the Kore.ai XO Platform using the Application Key and App secret](https://developer.kore.ai/docs/bots/channel-enablement/adding-ringcentral-glip-channel/#Step_2_Application_Set_up_on_the_Koreai_XO_Platform)
3. [Authorize a valid extension (user) of your RingCentral account to generate the developer access token, access the Glip APIs, and enable the channel](https://developer.kore.ai/docs/bots/channel-enablement/adding-ringcentral-glip-channel/#Step_3_Authorize_Extension_user_of_your_RingCentral_Sandbox_Account)
4. [Test the integration](https://developer.kore.ai/docs/bots/channel-enablement/adding-ringcentral-glip-channel/#Step_4_Test_the_Integration)
5. [(Recommended) Apply for Production](https://developer.kore.ai/docs/bots/channel-enablement/adding-ringcentral-glip-channel/#Recommended_Step_5_Apply_for_Production)


## Step 1: Create a RingCentral App

To enable Glip as a channel for your Kore.ai Virtual Assistant, you must create an application in the Sandbox environment (using a sandbox account) with the steps below:

**For New Users**

1. Log in to the **RingCentral Developer Console**.
2. On the left menu, click **Setup Wizard** under **Getting Started**.
3. In the **Get started to create your first app** panel, click **Create your First App**.

**For Existing Users**

1. Log in to the **RingCentral Developer Console**.
2. Click the **Console** button on the top left.
3. In the **Apps** section, click **Create App**.
![RingCentral developer Console](./images/ringcentral_glip1.png "RingCentral developer Console")

4. Select **REST API App** under **App Type** to call the **RingCentral REST API**.
![RingCentral REST API](./images/ringcentral_glip2.png "RingCentral REST API")

5. Click **Next**.

6. Enter all the required details on the **Create App – REST API App Settings** page and click **Next**.

7. Enter the values to the following fields on the     **App Properties (internal-use only)** page:
 * App Name
 * App Description (optional)
 * Primary Contact
 * Select the relevant option for **Do you intend to promote this app in the RingCentral App Gallery?**
 ![app properties](./images/ringcentral_glip3.png "app properties")

8. (Optional) In the **App Card panel**, enter the values for the given fields to configure how your application will be presented within our App Gallery.

9. In the **Auth** panel, enter the values for the following fields to select the authentication method your app will use:
 * Select **3-legged OAuth flow authorization code**.
 * Select **Server-side web app (most common)** or **Client-side web app** based on your app type for **From what type of app will you be calling the API?**

 ![OAuth flow](./images/ringcentral_glip4.png "OAuth flow")

 * On the Kore.ai XO Platform, copy the **OAuth Redirect URI** under the **Configurations** tab in the **RingCentral Glip** window.
 ![ringcentral glip configuration](./images/ringcentral_glip5.png "ringcentral glip configuration")

 * Paste the copied **OAuth Redirect URI** link in the **Auth** panel.
 * Select **_Yes_** for **Issue refresh tokens?**

10. In the Security panel, to define the permissions to associate with the app, follow the steps below:

11. Select the **Webhook Subscriptions**, **Read Accounts**, and **Team Messaging** permissions from the dropdown list.

 ![webhook subscriptions](./images/ringcentral_glip6.png "webhook subscriptions")

12. Click Create. Your App is created successfully and the system redirects to the **App Dashboard** page.

If you do not have a **Sandbox Account** to test your app in the Sandbox environment, follow the steps below:


* In the following dialog window, click **Next**.
![sandbox account](./images/ringcentral_glip7.png "sandbox account")


* Setup the Password for your **Sandbox** Account.

!!! tip

         The OAuth Redirect URI now includes the **_streamid_** in the API request to identify the virtual assistant being accessed. When an incoming request is qualified with this identifier, it helps with traceability, troubleshooting, and remediation at the network level during anomalies like malicious calls or unusual bot activity.



## Step 2: Application Set up on the Kore.ai XO Platform

After creating the app for the Sandbox/Production environment, you need to configure the app’s credentials on the Kore.ai XO Platform using the **_Client ID_** and **_Client Secret_** from the **RingCentral Glip Application Dashboard** to link the app. To set the credentials, follow the steps below:


1. On the **RingCentral Developer Application** Dashboard, click **Credentials** on the left menu.
![ringcentral developer application](./images/ringcentral_glip8.png "ringcentral developer application")

2. Under **Application Credentials**, click the copy icons for the **_Client ID_** and **_Client Secret_** (tap on click to see first) fields.
![application credentials](./images/ringcentral_glip9.png "application credentials")

3. On the Kore.ai XO Platform, navigate to **Deploy** > **Channels** and click **RingCentral Glip**.
![deploy channel](./images/ringcentral_glip10.png "deploy channel")

4. In the **RingCentral Glip** window, click the **Configurations** tab.
5. Paste the copied **_Client ID_** to the **Application Key** input field, and the **_Client Secret_** to the **_Application Secret_** input field.
6. Click **Save**.
![save app](./images/ringcentral_glip11.png "save app")



## Step 3: Authorize Extension (user) of your RingCentral Sandbox Account

The virtual assistant on the Kore.ai XO Platform must be associated with the extension (user) on your RingCentral account to access the **Glip API** via the developer access token. To enable this, you should authorize the virtual assistant with an existing or new extension user’s credentials. To add a new (non-admin) user, follow the steps below:

1. Log in to your RingCentral Sandbox account.
2. Click the **Users** tab.
3. Click **Users with Extension** on the left menu.
4. Click **+Add User**.
 ![user extension](./images/ringcentral_glip12.png "user extension")

5. On the **Add Users and Phones** dialog box, select **Add Users without Phone**, and follow the instructions on the page.
6. Click **Unassigned Extensions** on the left menu.
7. Click **Add Unassigned Ext**.
![unassigned extension](./images/ringcentral_glip13.png "unassigned extension")

8. On the **user profile information** page, enter all the required information.
1. Click **Save & Enable** to enable the extension.

!!! note

    Please provide a meaningful name like _Travel Bot_ or _HR Assistant_ to the virtual assistant inside **Teams Messaging**.



Notes

*  If you receive an account activation email on your registered email address, please note the username and password to authorize the virtual assistant on the Kore.ai XO Platform.

* Alternatively, select the “pre-assigned credentials” option and just provide/save the password.**.

* If you receive an account activation email on your registered email address, please note the username and password to authorize the virtual assistant on the Kore.ai XO Platform.
* Alternatively, select the “pre-assigned credentials” option and just provide/save the password.


### Step 3(a): Test the Validation

To access the admin portal from the Sandbox account screen and test the validation, follow the steps below:

1. Go to the **Sandbox Account** section and click the [link](https://app.devtest.ringcentral.com/) in the **Team Messaging** section.
![team messaging](./images/ringcentral_glip14.png "team messaging")

2. Navigate to **Messages** on the left menu.
3. In the **Direct Messages** section, click the **+** icon to start a new DM with the virtual assistant.
4. Find the virtual assistant using either the name or email address you used in _Step 3_.
5. Send the virtual assistant an opening message, such as “_Hello_” or “_good afternoon_”. The VA should respond based on the default behavior configured for **Dialog Tasks**.


### Step 3(b): Channel Setup on the Platform

On the Kore.ai XO Platform, navigate to **RingCentral Glip** > **Configurations** and follow the steps below:


1. In the **RingCentral Glip** window, click the **Authorize** button.
 ![authorize app](./images/ringcentral_glip15.png "authorize app")

2. In the **Sign-in** window, click **Continue as **to sign in with the existing user’s account, or click **Use Another Account**.

 ![use another account](./images/ringcentral_glip16.png "user another account")

3. Click **Authorize** on the **Access Request** page.
4. Once the access token is obtained successfully, authorization is complete.
![access request](./images/ringcentral_glip17.png "access request")

5. On the Kore.ai XO Platform, select **_Yes_** for the **Enable Channel** option under the **RingCentral Glip** > **Configurations** tab.
6. Click **Save** to enable the channel and Publish the Virtual Assistant. [Learn more](https://developer.kore.ai/docs/bots/publish/publishing-bot/).
![enable ringcentral](./images/ringcentral_glip18.png "enable ringcentral")


## Step 4: Test the Integration

Please follow the steps given [here](https://developers.ringcentral.com/guide/team-messaging/bots/walkthrough#step-5-send-your-first-message-to-the-bot) to test the integration.


## (Recommended) Step 5: Apply for Production

Once your app is tested in the Sandbox environment and ready for production, follow the RingCentral app graduation process mentioned [here](https://developer.ringcentral.com/library/getting-started.html#ApplyForProduction) to apply for production after meeting all the graduation requirements for your app as shown below:
![apply for production](./images/ringcentral_glip19.png "apply for production")


Once your app is production ready, follow the steps below on the Kore.ai XO Platform:


1. Navigate to **Deploy** > **Channels** > **RingCentral Glip**.
2. Under the **Configurations** tab, select **Production for Ringcentral Environment**.
3. Follow [these](https://developer.kore.ai/docs/bots/channel-enablement/adding-ringcentral-glip-channel/#Step_3b_Channel_Setup_on_the_Platform) steps to complete the configuration.

Congratulations! You have now completed the **Glip by RingCentral** channel enablement. To learn how to enable other business messaging channels, click [here](https://developer.kore.ai/docs/bots/channel-enablement/adding-channels-to-your-bot/).
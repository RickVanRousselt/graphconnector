# Office 365 Node.js Connect sample using Microsoft Graph in a docker container

This code is a copy found in the examples on Office development.
I've added a Dockerfile here so that this code can run from a docker container.
This code is linked to https://hub.docker.com/r/rickvanrousselt/graphconnector/ where after a commit it will automatically build a new docker image.

The sample uses the v2.0 authentication endpoint, which enables users to sign in with either their personal or work or school Microsoft accounts.
 
![Office 365 Node.js Connect sample screenshot](./readme-imgs/screenshot.PNG)
> Note: For an in-depth look at the code for calling the Microsoft Graph API in a Node.js app, see [Call Microsoft Graph with a Node.js app](https://graph.microsoft.io/docs/platform/nodejs).

<a name="prerequisites"></a>
## Prerequisites

To use the Office 365 Node.js Connect sample, you need the following:
 * Either a [Microsoft](www.outlook.com) or [Office 365 for business account](https://msdn.microsoft.com/en-us/office/office365/howto/setup-development-environment#bk_Office365Account).
 * [Node.js](https://nodejs.org/) version 4 or 5.

<a name="register"></a>
##Register and configure the app

1. Sign into the [App Registration Portal](https://apps.dev.microsoft.com/) using either your personal or work or school account.
2. Select **Add an app**.
3. Enter a name for the app, and select **Create application**.
	
	The registration page displays, listing the properties of your app.
 
4. Under **Platforms**, select **Add platform**.
5. Select **Web**.
6. Add the following to the list of **Redirect URIs**:

    ```
    http://localhost/login
    ```    
    
7. Under **Application Secrets** click **Generate New Password**.
8. Copy the **New password generated** and **Application Id**, you'll need them in the next section.
9. Click **Save**.

## Configure and run the app

1. Update [```authHelper.js/client_id```](authHelper.js#L7) with your application id
2. Update [```authHelper.js/client_secret```](authHelper.js#L8) with your password

To run the app, type the following into your command line:

docker run -d -p 80:3000 rickvanrousselt/graphconnector

## Launch the app in your browser
Once the application server has been started, open your web browser to ```http://localhost```

## Questions and comments

  
## Additional resources

* [Office 365 APIs platform overview](https://msdn.microsoft.com/office/office365/howto/platform-development-overview)
* [Getting started with Office 365 APIs](http://dev.office.com/getting-started/office365apis)
* [Overview of Microsoft Graph](http://graph.microsoft.io)
* [Office UI Fabric](https://github.com/OfficeDev/Office-UI-Fabric)

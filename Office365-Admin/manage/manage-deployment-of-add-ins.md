---
title: "Manage deployment of Office 365 add-ins in the Office 365 admin center"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_AdminOfficeAddins'
- 'O365M_AdminOfficeAddins'
- 'O365E_AdminOfficeAddins'
- 'AdminOfficeAddins'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: "Learn to deploy add-ins to users and groups in your organization by using Centralized Deployment in the admin center."
---

# Manage deployment of Office 365 add-ins in the Office 365 admin center

Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). As an Office 365 admin, you can deploy Office add-ins for the users in your organization. You can do this using the Centralized Deployment feature in the Office 365 admin center.
  
Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization. For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your Office 365 organization](centralized-deployment-of-add-ins.md).
  
Centralized Deployment provides the following benefits:
  
- A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the tenant.
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- Add-ins will no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.
    
> [!NOTE]
>  For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Office 365 and/or support for SharePoint add-ins required. >  For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Office 365. > 
  
## Recommended approach for deploying Office add-ins

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. Full rollout to target audience of users.
    
Depending on the size of the target audience, you may want to add or remove roll-out steps.
  
## Deploy an Office add-in using the Office 365 admin center

Before you begin, see [Determine if Centralized Deployment of add-ins works for your Office 365 organization](centralized-deployment-of-add-ins.md).

  
1. [Where to sign in to Office 365 for business](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account. 
    
2. Select **Admin** ![App launcher icon in Office 365](../media/admincentericon.png) from the list of apps.<br/> TIP: **Admin** appears only to Office 365 admins. 
  
3. In the navigation menu, choose **Settings** \> **Services &amp; add-ins**. 
    
4. Choose **Deploy Add-in** at the top of the page. You will see the following introduction. 

![Add-in dialog introducing Centralized Deployment](../media/centralizeddeploymentstep1.png)

If you do not wish to see this every time you deploy, check the box before choosing **Next**.
    
5. Choose from one of the following options on the **Centralized Deployment** page: 
    
  - **I want to add an Add-in from the Office Store**
    
  - **I have the manifest file (.xml) on this device**: For this option, select **Browse** to locate the manifest file (.xml) that you want to use. 
    
  - **I have a URL for the manifest file**: For this option, type the URL in the field provided. 
    
![Add-in dialog for Centralized Deployment](../media/centralizeddeploymentstep2.png)
  
6. Select **Next**. 
    
7. If you selected the option to add an add-in from the Office Store, you can now make your add-in selection. Notice that you can view available add-ins via categories of **Suggested for you**, **Rating**, or **Name**. Only free add-ins are available to add from the Office Store. Paid add-ins aren't supported currently. Once you've selected your add-in, you will need to agree to some additional terms and conditions in order to proceed. <br/> NOTE: With the Office Store option, updates and enhancements to the add-in will automatically be made available to users without your intervention.<br/> ![Select an Add-in dialog for the Office Store](../media/centralizeddeploymentstep3.png)
  
8. In **Specify who has access**, select **Everyone**, **Specific users/groups** or **Just me** to specify who the add-in is deployed to. Use the Search box to find the users or groups who you want to deploy the add-in to. <br/>NOTE: Learn about the other states that apply to an add-in. See [Add-in states](#add-in-states) later in this topic.<br/>![Centralized Deployment page for the Power BI Tiles add-in](../media/centralizeddeploymentstep4.png)
  
9. Select **Deploy Now**.
  
10. The add-in has now been deployed. A green tick will appear when this has been completed. You can follow the on page instructions in order to test that the add-in has deployed successfully.

![Centralized Deployment page success](../media/centralizeddeploymentstep6.png)

> [!NOTE]
> Users may need to relaunch Office to see the add-in icon appear on the ribbon of app. Outlook add-ins can take up to 12 hours to appear on users' ribbons.
    
11. When finished, choose **Next**. If you've deployed to just yourself, you can choose **Change who has access to add-in** in order to deploy to more users.

![Centralized Deployment page for just me deployments](../media/centralizeddeploymentstep7.png)

If you've deployed the add-in to members of your orgnisation other than yourself, follow the instructions displayed in order to effectively announce the deployment of the add-in. <br/>You now see your add-in along with other apps in Office 365.<br/>![Office 365 admin center deployed Add In](../media/centralizeddeploymentstep8.png)
  
It's a good idea to inform the users and groups who you deployed the add-in to so that they know that it's available. Consider sending an email to them that describes when and how to use the add-in and explains how the add-in can help them do their job better. Include or link to relevant Help content or FAQs that might help if users have any problems with the add-in.
  
### Considerations when assigning an add-in to users and groups

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- **Just me**: If you assign an add-in to just yourself, this assigns the add-in to only your account. This is ideal if you wish to test out the add-in first.
    
The option that is right for your organization depends on your configuration. However, we recommend making assignments via groups. As an admin, you might find it easier to manage add-ins using groups and control the membership of those groups rather than having to change the users assigned each time. On the other hand, in some situations, you may want to restrict access to a very small set of users and therefore make assignments to specific users. As a result, you will need to manage the assigned users manually.
  
### Add-in states

An add-in can either be in the **On** or **Off** state.
  
|**State**|**How the state occurs**|**Impact**|
|:-----|:-----|:-----|
|**Active**  <br/> |Admin uploaded the add-in and assigned it to users or groups.  <br/> |Users and groups assigned to the add-in see it in the relevant clients.  <br/> |
|**Turned off**  <br/> |Admin turned off the add-in.  <br/> |Users and groups assigned to the add-in no longer have access to it.  <br/> If the add-in state is changed to Active, the users and groups will have access to it again.  <br/> |
|**Deleted**  <br/> |Admin deleted the add-in.  <br/> |Users and groups assigned the add-in no longer have access to it.  <br/> |
   
Consider deleting an add-in if no one is using it any more. Turning off an add-in may make sense if an add-in is used only during specific times of the year.
  
### Security of Office add-ins

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Display data.
    
- Read a user's document to provide contextual services.
    
- Read and write data to and from a user's document to provide value to that user.
    
For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362), especially the section "Anatomy of an Office Add-in."
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Updates for add-ins happen as follows:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
    
### Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)

> [!NOTE]
> Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/en-us/library/jj943754%28v=exchg.150%29.aspx).

As an organization you may wish to prevent the download of new Office add-ins from the Office Store. This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.
  
To turn off add-in acquisition:
  
1. Go to the [Office 365 admin center](https://go.microsoft.com/fwlink/?linkid=869152).
    
2. Click **Settings** \> **Services &amp; add-ins**.
    
3. Click **Office Online**.
    
4. Click the toggle next to **Allow peple to use third-party hosted storage services** so that it's in the **Off** position. 
    
This will prevent all users from acquiring the following add-ins from the store.
  
- Add-ins for Word, Excel, and PowerPoint 2016 from:
    
  - Windows
    
  - Mac
    
  - Office Online
    
  - iOS
    
- Acquisitions starting within **AppSource**
    
- Add-ins within Office 365
    
A user who tries to access the store will see the following message: **Sorry, Office 365 has been configured to prevent individual acquisition of Office Store add-ins.**
  
Support for turning off the Office Store is available in the following versions:
  
- Windows: 16.0.9001 - Currently available in monthly channel. Available in semi-annual release in July 2018.
    
- Mac: 16.10.18011401 - Currently available.
    
- iOS: 2.9.18010804 - Currently available.
    
- Office Online - Currently available.
    
This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.
  
To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account. For more information, look [here](https://technet.microsoft.com/EN-US/library/jj683102%28v=office.16%29.aspx).
 
  
## Minors and acquiring add-ins from the Store

The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018. It gives users rights to and protection of their data. One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved. The specific age defined as a minor depends on the region where the individual is located.
  
Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union. For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired. For countries without statutory regulations, there will be no download restrictions.
  
A user is determined to be a minor based on data specified in Azure Active Directory. The tenant admin is responsible for declaring the legal age group and the parental consent for that user.
  
If the parent/guardian consents to a minor using a specific add-In, then the tenant admin can use centralized deployment to deploy that add-In to all minors who have consent.
  
To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.
  
 **For Word, Excel, PowerPoint, and Project**: 
  
|||
|:-----|:-----|
|**Platform** <br/> |**Build number** <br/> |
|Office 2016 ProPlus Monthly for Windows  <br/> |9001.2138   <br/> |
|Office 2016 ProPlus Semi-Annual  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Office 2016 for iOS  <br/> |2.12.18032600  <br/> |
|Office Online  <br/> |N/A  <br/> |
   
 **For Outlook**: 
  
|||
|:-----|:-----|
|**Platform** <br/> |**Build number** <br/> |
|Outlook 2016 for Windows (MSI)  <br/> |Build No TBD  <br/> |
|Outlook 2016 for Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook mobile for iOS  <br/> |2.75.0  <br/> |
|Outlook mobile for Android  <br/> |2.2.145  <br/> |
|Outlook Online  <br/> |N/A  <br/> |
   
 **Office 2013 requirements**
  
Word, Excel, and PowerPoint 2013 for Windows will support the same minor checks if Active Directory Authentication Library (ADAL) is enabled. There are two options for compliance, as explained next.
  
- **Enable ADAL**. This article explains how to enable ADAL for Office 2013: [Using Office 365 modern authentication with Office clients](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).<br/>You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).<br/>Additionally, you need to install the following April updates for Office 2013:
    
  - [Description of the security update for Office 2013: April 10, 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [April 3, 2018, update for Office 2013 (KB4018333)](https://support.microsoft.com/en-us/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Don't enable ADAL**. If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the office clients. Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).
    
## End user experience with add-ins

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). The add-in will appear on all platforms that the add-in supports.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![Office ribbon with Search Citations](../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**. 
  
### In Word 2016, Excel 2016, or PowerPoint 2016

1. Choose **Insert \> My Add-ins**. 
    
2. Select the **Admin Managed** tab in the Office Add-ins window. 
    
3. Double-click the add-in you deployed earlier (in this example, **Citations** ). <br/>![Admin Managed tab of the Office Add-ins page](../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### In Outlook

1. On the **Home** ribbon, choose **Get Add-ins**.<br/>![Store button in Outlook](../media/getaddinsicon.png)
  
2. Choose **Admin-managed** in the left nav.
  
## Learn more

Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9).
  
[Troubleshoot: User not seeing add-ins](../troubleshoot-issues-for-admins/user-not-seeing-add-ins.md)


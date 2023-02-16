---
title: "Manage Yammer users across their lifecycle from Office 365"
f1.keywords:
- NOCSH
ms.author: pamgreen
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 6c4c8fff-6444-404a-bffc-f9da0bcc3039
description: "Manage Yammer Enterprise users in Office 365. As you create, delete, and restore users in Office 365, they will be created, deactivated, and reactivated in Yammer."
---

# Manage Yammer users across their lifecycle from Office 365

There are many types of users in Yammer and managing each of them is different.

- Users with Azure Active Directory-identity
- Users without Azure
- And other guest users

As a global administrator, you control the lifecycle for Yammer users through the Microsoft 365 admin center, in addition to managing them through Yammer.

All communities and groups from Yammer networks that are in Native Mode will be managed through these admin centers. Some of the management capabilities regarding community or group members or users that can be done through the Microsoft 365 admin center includes:

- Add or remove community or group members
- Manage community or group ownership
- Delete a community or group
- Restore a community or deleted group
- Rename the community or group
- Update the community or group description
- Change the community's or group's privacy setting

When you create users in Office 365, they can log on to Yammer with their Office 365 credentials. When a user is deleted from Office 365, he or she is automatically deactivated or suspended in Yammer. When a user is restored in Office 365, he or she is reactivated in Yammer.
  
The user's profile properties (such as name and department) from Azure Active Directory are automatically populated in the user's Yammer profile, and any changes to the profile properties in Azure Active Directory are reflected in Yammer as well. 

If users have an Office 365 account, they will not be able to update their information directly in Yammer. If users want to change their information, such as photos, phone numbers, and other data, they will need update it through their Office 365 profile just as they would with other Office 365 apps. Depending on the organization, users may be able to update through Office Delve or the user might need to ask their IT administrator to assist.

> [!Important]
> If a user had a customized profile prior to April 2020, it will be overwritten with their AAD identity to create a single source of truth.


The user's Yammer language setting is taken from Office 365 when the user's Yammer account is activated. If the user changes their Office 365 language setting or if the setting is changed directly in Azure Active Directory, Yammer does not pick up this change. The user can change their Yammer language setting in their Yammer profile on the **Preferences** tab.

This change will also mean that we retire properties that aren’t synced today like user’s personal email account information. If you’d like to maintain information data from the **About Me** settings – such as Schools, Expertise, and Interest - we recommend that you export this and update the users’ Office profile via Microsoft Graph, or ask users to update it directly in Microsoft Delve.

## How are user photos managed?

If new users in your network already have the correct user photo from AAD, it will continue working after this change.

If your organization usually uploads photos from Yammer, you can follow these steps:

1. Export the list of users,
2. Use that list of users to export their photos via a script.
3. Re-upload them via Microsoft Graph to make it their photo in the rest of Office.
  
## Create a user

The user creation varies depending on when the Yammer network was created.

### Networks created before March 2019

Beginning in March 2019, we started transitioning how Yammer users are created. During the transition, which will occur during through 2020, the process will be different for existing Office 365 users and new Office 365 users.

- **Pre-March 2019**: Yammer users are created when they use Yammer for the first time. 
 
    > [!NOTE]
    > During the rest of 2019, Office 365 users who have not yet used Yammer will be converted to "pending" Yammer users. 

    ![Diagram that shows when an Office 365 admin creates a user, the user can log on to Office 365 then navigate to Yammer from the App Launcher, at which point the user is created in Yammer.](../media/410ab6f2-e8ed-4b66-a8cf-f087b3e57ec3.png)

    The process of creating a user requires these steps:
  
    1. The Office 365 admin creates a user in Office 365.
    
    2. The user logs on to Office 365 using the identity provider that is configured for the tenant.
    
    3. The user clicks the Yammer tile in the Office 365 app launcher to go to Yammer.
    
    4. A new Yammer user is created for the Office 365 user. The user's profile properties and language setting from Azure Active Directory are automatically populated in the user's Yammer profile.

### New networks, Native Networks, and Enforced Office 365 Identity Networks 

When **Enforce Office 365 identity** is selected in Yammer (including when in Native Mode), as Yammer-eligible users are added to Office 365, they are automatically added as new pending users in Yammer. Their status changes from **Pending** to **Active** the first time they use Yammer.

![Diagram that shows new process for creating a Yammer user, where the new user is created automically as "pending" in Yammer](../media/yam_newuserprocess.jpg)

> [!Note]
> If you have Viva Core licensed to your users, they will instead show up as 'active' instead of 'pending'.

The process follows these steps:
  
1. The Office 365 admin creates a user in Office 365.
    
2. A pending user is created in Office 365. The first time the user uses Yammer, the pending user becomes an active user.


- **During transition**: Different actions are taken for different user categories:

    |**Type of user**|**Yammer network configuration**|**Way that they are added**| 
    |:-----|:-----|:-----|
    |New users added to your Office 365 tenant|**Enforce Office 365 identity** selected|Users are automatically added as pending users in Yammer. 
    | Existing users in your Office 365 tenant|**Enforce Office 365 identity** selected|Office 365 users must still use Yammer in order to be added as a Yammer user. |

    
## Block a user

An administrator can block a user in Microsoft 365 or Office 365, and the user will be logged out of Yammer as well as all the other Office 365 services. Here's a diagram that shows how this works.
  
![The Office 365 administrator blocks a user in Office 365 and the user is logged out of Yammer.](../media/86303509-db4e-4d80-9f7c-3b2ddbcd1f17.png)

The process follows these steps:
  
1. The Office 365 administrator sets the user's sign-in status to **Block the user from signing in**.
    
    To do this:
    
    1. In the Microsoft 365 admin center, select a user and choose **Edit User**. The **Sign-in status** is shown in the user details, as in this screenshot. 
    
        ![Screenshot of a users's sign-in status in Office 365.](../media/3003a58e-1294-460a-a174-2be67b1dc462.png)
  
    2. Click **Edit** next to **Sign-in status** to switch between **Allow the user to sign in** and **Block the user from signing in**, as in this screenshot.
    
        ![Sign-in status dialog box in Office 365.](../media/c06def75-bb12-4dea-ae2b-325ee410c5ed.png)
  
    3. This action flows into Yammer, and the corresponding user is logged out of Yammer (on all devices). When this user tries to login to Yammer again from any device, he or she will be prompted to login with their Office 365 credentials. However, the user will not be able to login because their sign-in status is set to blocked. As a Yammer verified administrator, you can go to the Network Admin area, and look at the Account activity section to verify that the Yammer user has been logged out, as in the following screenshot, where the user has no active Yammer sessions.
    
        ![Account Activity for a user showing no active Yammer sessions (logged out).](../media/c0704de5-d3c4-4b34-9bbb-f3cf31799734.png)
  
## Delete a user

If an employee leaves the company, you can delete the user from Office 365. When the user is deleted from Office 365, the corresponding user is deactivated (also known as suspended) in Yammer. The following diagram shows how this works:
  
![Diagram that shows when an Office 365 admin deletes a user, the user is deactivated in Yammer. After 30 days, the user data is deleted from Office 365 and after 90 days, the user is permanently removed from Yammer but their Yammer messages remain.](../media/8aba30a5-2636-4acf-9224-4a18bbe7fec1.png)
  
The process follows these steps:
  
1. An admin deletes a user from Office 365, as shown in the following screenshot:
    
    ![Screenshot showing the command to delete a user in Office 365 administration.](../media/b0922976-84c0-4c3d-ade0-710cf3ce69b2.png)
  
2. The user deletion in Office 365 flows into Yammer, and the corresponding Yammer user is deactivated in Yammer. Specifically, the operation is equivalent of navigating to Yammer administration, choosing **Remove Users**, and then selecting **Deactivate this user**, as shown in the following screenshot:
    
    ![Screenshot showing how to deactivate a user in Yammer.](../media/91299919-212c-41f9-b6dd-185c0b81de65.png)
  
    Users who are deactivated (or suspended) this way will show up in Yammer administration pages as being deactivated by **System Administrator**, as shown in the following screenshot: 
    
    ![Screenshot that shows a user removed by System Administrator.](../media/b0ac3142-1fba-4c52-95d8-bbbb063cdaa2.png)
  
3. When you delete a user in Office 365, the user becomes inactive. After approximately 30 days, user data gets permanently deleted. See [Delete a user from your organization](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
    
    Similarly, when a user is deactivated in Yammer, that user becomes inactive in Yammer. After approximately 90 days, deactivated users are permanently removed, but their name, files, messages and activity data are retained. 
    
    > [!IMPORTANT]
    > When you delete a user from Office 365 and this flows through to Yammer, the user's name, files, messages, and activity data remain in Yammer even though the user is deleted. For options that remove a user in a way that the user's name and data are also deleted from Yammer, see [Remove users](add-block-or-remove-users.md#RemoveUsers) and [Manage GDPR data subject requests in Yammer Enterprise](../manage-security-and-compliance/gdpr-requests-in-yammer-enterprise.md). 
  
## Restore a user

When an administrator restores a Yammer-eligible user in Office 365, the user will be reactivated in Yammer. The following diagram shows how this works:
  
![Diagram that shows when an Office 365 admin restores a user, the user is then activated again in Yammer.](../media/f2dbf5f2-ba25-419e-802c-ac89e0bdeb7f.png)
  
The process follows these steps:
  
1. The Office 365 administrator can restore a deleted user in Office 365, as shown in the following screenshot:
    
    ![Screenshot showing the command to restore a user in Office 365 administration.](../media/b30aa7c8-2e2d-45ed-9c0a-2bf9730c8b30.png)
  
2. This action flows into Yammer as well, and the previously deactivated user in Yammer is reactivated.
    
## User profile information

The user profile experience differs depending on whether or not the account is connected to Azure Active Directory (Azure AD).

### For AAD-connected accounts

Office 365 uses the cloud-based service Azure Active Directory (Azure AD) to manage users. You can either manage users directly in the cloud or use [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/article/06a189e7-5ec6-4af2-94bf-a22ea225a7a9) to create and synchronize users and communities or groups from your on-premises environment. 

When Office 365 users who are new to Yammer access Yammer for the first time using their Azure AD credentials, a Yammer user is created, and the Yammer user profile is populated with the Azure AD user properties. And when the user's profile properties are edited in Azure AD, they are updated in the existing user's Yammer profile. Say, the user's department changed in Azure AD, they will appear in Yammer as well. 
  
User profiles that they see in Yammer are their Office 365 profile, if their organization uses Azure AD to manage user credentials.
  
- To view their profile in Office 365, users can click on their profile picture and choose **My account**.
    
    ![Office 365 profile picture.](../media/yammer-identity-user-profile.png)
  
    This lets them view their account information for Office 365. If the organization allows editing personal information, then users can click **Personal Info**, and add the information they want. If the organization doesn’t allow editing, then the settings will not be editable and users will see a ****Why can’t I edit** link they can click for more information.

    User photos will also be synced from Office. To prepare for this change, make sure your organization’s photos can be found in any one of the following places:

    - Go to the All users list in the AAD portal and then click the desired user for picture.
    - Confirm the My account page in the Office portal has the photo.
    - Get the Photo API using the Microsoft Graph beta.
    - Get-the UserPhoto Exchange Online cmdlet, if applicable.

    
- To view their profile in Yammer, users can choose **Edit Settings**, and then **Profile**.
    
  
### For non-AAD accounts

If your Yammer users are not in AAD, then they can update their profiles in Yammer by clicking Edit Settings, and then Profile.
  
![A sample user profile.](../media/e9378a05-bb94-4775-9336-818333e65edf.png)
  
The Office 365 administrator can edit user properties from the Microsoft 365 admin center.
  
 **To edit user properties in Microsoft 365 or Office 365**
  
1. In the Microsoft 365 admin center, go to the **Users** section, and select or search for a user, as shown in the following screenshot. 

   ![Screenshot showing the Users section of Microsoft 365 admin center.](../media/b045e652-c971-46c2-a37a-a2d2cc872838.jpg)
  
2. Click on the user, and choose **Edit** to change the properties, such as Username or Contact information. 
    
    ![Screenshot showing editing profile properties.](../media/57657206-20e3-4c1e-811a-dd6b0df1beaa.jpg)
  
Azure AD updates the following Yammer properties:
  
|**Property in Azure AD**|**Property in Yammer**|
|:-----|:-----|
| Email address  <br/>  Display Name  <br/>  Job Title  <br/>  Department  <br/>  Office  <br/>  Office phone  <br/>  Mobile phone  <br/>  Description  <br/> | Email  <br/>  Display Name  <br/>  Job Title  <br/>  Department  <br/>  Location  <br/>  Work phone  <br/>  Mobile phone  <br/>  About Me  <br/> |
   
In Office 365, you can see the user properties that will be updated for Yammer in the following dialog boxes:
  
- **Edit email addresses** dialog box 
    - **Edit contact information** dialog box 
    
    ![Screenshot showing editing contact information.](../media/78cb9ff3-a1a3-4bff-be12-e584c36063f8.jpg)
  
  
## FAQ

### Q: Are user profile pictures updated from Office 365 to Yammer?

A: Yes. The profile will be updated with the user's Office 365 profile picture. This update is initiated when the user clicks the Yammer tile from Office 365 or logs in to Yammer for the first time, and will be reflected in the Yammer profile within few hours. If the user later updates his or her profile picture, the Yammer profile picture will also update after the user next uses Yammer.
  
### Q: When an email address is changed in Office 365, does it trigger an email address change in Yammer?

A: Yes.
  
### Q: What happens when a user leaves the company?

A. When a user leaves the company and Azure Active Directory is updated, their Yammer profile content is replaced with their start and end dates, and their title is changed to **Former member**. All the messages and files they posted remain in Yammer. 

   ![Yammer profile content.](../media/yam_former_member.png)

### Q: My company has a configuration where not all Yammer users are yet in Office 365. How does life cycle management work in this case?

A: The users who log on to Yammer with Office 365 credentials can be managed in Office 365. You can continue to manage the users who don't use their Office 365 credentials the same way you manage them today. Eventually, when you move everyone to Office 365, you will have one single place to manage all your users (including those who use Yammer).
  
## Related articles

[Manage a Yammer community or group](https://support.office.com/article/12ce0216-0618-4576-b87a-a8c189cee0f8)

[Change my profile settings](https://support.office.com/article/cb9b9f8b-391d-424b-b752-5e23619fadec)

[Add, block, or remove Yammer users](../manage-yammer-users/add-block-or-remove-users.md)

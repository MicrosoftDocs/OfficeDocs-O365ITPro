---
title: "Create, edit, or delete a custom user view in Office 365"
ms.author: twerner
author: twernermsft
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_ESUsersFilter'
- 'O365M_ESUsersFilter'
- 'O365E_ESUsersFilter'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: "Learn to use filters to create, edit, or delete custom user view in Office 365."
---

# Create, edit, or delete a custom user view in Office 365

If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.
  
## Custom user views in the admin center


When you create, edit, or delete a custom user view, the changes will be shown in the **Filters** list of views that all admins in your company see when they click the **Users** page. You can create up to 50 custom views. 
  
> [!NOTE]
>  Standard user views are displayed by default in the **Filters** drop-down list. The standard filters include **All users**, **Licensed users** **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Password admins**, **Service admins**, and **User management admins**. You can't edit or delete standard views. A few things to note about standard views: >  Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box. >  If you didn't purchase Office 365 from Microsoft, **Billing admins** don't appear in the standard views list. For more information, see [Assigning admin roles](assign-admin-roles.md). 
  
## Choose the filters for your custom user view


You can create and edit your custom views on the **Custom filter** page. If you select multiple filter options, you get results that contain users who match all the selected criteria. The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada. 
  
![Custom filter conditions](../media/0fbf9bcb-b467-4a74-aae9-4bf467f32ad3.png)
  
 **A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available. 
  
 **B - Sign-in status** Choose users that are allowed or blocked. 
  
 **C - Location** Choose a location from a drop-down list of countries. 
  
 **D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization. Use this filter to show users who have the license you selected assigned to them. Users may also have additional licenses. 
  
You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.
  
 **Other conditions:**
  
- **Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not. 
    
- **Users with errors** Select this box to show users who may have provisioning errors. 
    
- **Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.
    
- **Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Office 365 license. The results of this filter include users who have or who were assigned an Exchange archive. 
    
> [!NOTE]
> If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted. In this case, use the search box to find users or **Edit filter** to refine your search. 
  
## Create a custom user view


1. Navigate to **Admin** \> **Office 365** \> **Users**.
    
2. On the **Active users** page, click **Filters** and select **Add custom filter**.
    
    ![Add custom filter](../media/a16229d7-0476-4559-a637-43532c410726.png)
  
3. On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then click **Save** \> **Close**. Your custom view is now included in the drop-down list.
    
## Edit a custom user view


1. Navigate to **Admin** \> **Office 365** \> **Users**.
    
2. On the **Active users** page, click the drop-down arrow next to the **Filters** box and select the custom view that you want to edit. 
    
    > [!NOTE]
    > You can edit only custom views. 
  
3. Click **Edit this filter**.
    
    ![Delete custom filter](../media/115f62a6-2224-418c-888e-2374dcfd7f57.png)
  
4. On the **Custom filter** page, edit the information as needed, and then click **Save** \> **Close**.
    
## Delete a custom user view


1. Navigate to **Admin** \> **Office 365** \> **Users**.
    
2. On the **Active users** page, click the drop-down arrow next to the **Filters** box and select the custom view that you want to delete. 
    
    > [!NOTE]
    > You can delete only custom views. 
  
3. Click **Edit this filter**.
    
4. On the **Custom filter** page, at the bottom of the page, click **Delete custom filter**, and then click **Close**.
    


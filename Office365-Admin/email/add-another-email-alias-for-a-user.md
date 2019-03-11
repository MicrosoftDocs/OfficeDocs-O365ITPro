---
title: "Add another email alias for a user"
ms.author: kwekua
author: kwekua
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Top
- Core_O365Admin_Migration
- MiniMaven
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: "Learn how you can have more than one email address, called email alias, associated with your Office 365 for business account. "
---

# Add another email alias for a user

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end
  
This article is for Office 365 global admins who have business subscriptions. It's not for home users.
  
A primary email address in Office 365 is usually the email address a user was assigned when their account was created. When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps. They can also have more than one email address associated with their Office 365 for business account. These additional addresses are called aliases. 
  
For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name. You can create aliases for her so that both email addresses go to Jenna's inbox.
<br><br>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fdd6503-e7e2-42d4-8a11-67f92dcaf1ce?autoplay=false]
  
You can create up to 400 aliases for a user. No additional fees or licenses are required.
  
> [!Tip]
> If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox. To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).
  
## Add email aliases to a user
<a name="AddEmailPreview"> </a>

You must have [admin permissions](../add-users/about-admin-roles.md) to do this. 
  
1. In the admin center, go to the <a href="" target="_blank">Active users</a> page, or choose **Users** \> **Active users**.

    ::: moniker range="o365-germany"
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page. 
    
    ::: moniker-end

    ::: moniker range="o365-21vianet"

    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page. 

    ::: moniker-end
    
2. On the **Active Users** page, select the name of the person you want to edit. 
    
3. On the right, in the **Username / Email Aliases** row, choose **Edit**.
    
    > [!Important] 
    > If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call Support and they will do a full sync for you.
    
4. On the **Edit email addresses** page, in the text box under **Alias**, type the first part of the new email alias. If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list. Then choose **Add**.
    
    > [!IMPORTANT]
    > If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console. 
  
    > [!TIP]
    > The email alias must end with a domain from the drop-down list. To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx). 
  
    ![The Edit email addresses and username pane](../media/2518a8b8-1136-4639-b159-35ad21f61437.png)
  
5. When you're done, choose **Save**.
    
6. Wait 24 hours for the new aliases to populate throughout Office 365.
    
    The user now has a primary address and an alias. All mail sent to Eliza@NodPublishers.com and Sales@NodPublishers.com will go to Eliza's Inbox.
    
    ![This user has a primary address and two aliases.](../media/df6af45a-37a2-4d31-88f3-c788ac978643.png)
  
7. **When the user replies, the *From*  address will be her primary email alias.** For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox. When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com. 
    
## Did you get "A parameter cannot be found that matches parameter name 'EmailAddresses"?
<a name="AddEmailPreview"> </a>

If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call Support and they will do a full sync for you.
  
## Did you purchase your subscription from GoDaddy or another Partner?
<a name="AddEmailPreview"> </a>

If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.
  
## See Also
<a name="AddEmailPreview"> </a>

[Send email from a different address](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)
  


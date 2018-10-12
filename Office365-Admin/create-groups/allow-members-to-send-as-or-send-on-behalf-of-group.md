---
title: "Allow members to send as or send on behalf of a Group"
ms.author: dianef
author: dianef77
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: "Learn how to allow members to send email as an Office 365 Group or send email on behalf of an Office 365 Group in the Exchange admin center in Exchange Online."
---

# Allow members to send as or send on behalf of a Group

A member of an Office 365 Group who has been granted **Send as** or **Send on behalf** permissions can now send email as the group, or on behalf of the group. This topic explains how an admin can set these permissions in the Office 365 admin center or by using PowerShell. Learn more about [Office 365 Groups](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).
  
For example, if Allie Bellew is part of **Training** Office 365 Group in your organization, and has **Send as** permissions on the group, if she sends an email as the Office 365 Group, it will look like the **Training** department from your organization sent the email. 
  
The **Send on Behalf** permission lets a user send email on behalf of an Office 365 Group. For example, if Donald Forster is a part of the **Marketing** Office 365 Group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Donald Forster on behalf of Marketing Team**.
  
## What do you want to do?

- [Allow members to send email as an Office 365 Group](allow-members-to-send-as-or-send-on-behalf-of-group.md#BKMK_SendASGroup)
    
- [Allow members to send email on behalf of an Office 365 Group](allow-members-to-send-as-or-send-on-behalf-of-group.md#BKMK_SendonBehalfofGroup)
    
## Allow members to send email as an Office 365 Group
<a name="BKMK_SendASGroup"> </a>

This section explains how to allow users to send email as an Office 365 Group in the [Exchange admin center (EAC) in Exchange Online](http://go.microsoft.com/fwlink/?LinkID=837684).
  
1. In the EAC, go to **Recipients** \> **Groups**.
    
2. Select **Edit** on the Office 365 Group that you want to allow users to send as. 
    
3. Select **group delegation**.
    
4. In the Send As section, choose the **+** sign to add the users that you want to send as the Office 365 Group. 
    
    ![Choose the plus sign to add the users that you want to send as the Office 365 Group](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Type to search or pick a user from the list. Click **OK** and **Save**.
    
    ![Type to search or pick a user from the list](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from an Office 365 Group. 
  
 **Allow users to send email as an Office 365 Group using Powershell**
  
Send as permission can be set for a group using the [Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960) cmdlet in PowerShell. 
  
```
Add-RecipientPermission traininggroup@contoso.com -AccessRights SendAs -Trustee myuser1@contoso.com
```

Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for more details on using Exchange Online PowerShell. 
  
## Allow members to send email on behalf of an Office 365 Group
<a name="BKMK_SendonBehalfofGroup"> </a>

This section explains how to allow users to send email on behalf of an Office 365 Group in the Exchange admin center (EAC) in Exchange Online.
  
1. In the EAC, go to **Recipients** \> **Groups**.
    
2. Select **Edit**![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Office 365 Group that you want to allow users to send as. 
    
3. Select **group delegation**.
    
4. In the Send on Behalf section, choose the **+** sign to add the users that you want to send as the Office 365 Group. 
    
    ![choose the plus sign to add the users that you want to send as the Office 365 Group](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Type to search or pick a user from the list. Click **OK** and **Save**.
    
    ![Type to search or pick a user from the list](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
    Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from an Office 365 Group. 
    
 **Allow users to send email as an Office 365 Group using Powershell**
  
Send as permission can be set for a group using the [Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189) cmdlet in PowerShell. 
  
```
Set-UnifiedGroup <group_smtp_address> -GrantSendOnBehalfTo <user_smtp_address>
```

Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for more details on using Exchange Online PowerShell. 
  


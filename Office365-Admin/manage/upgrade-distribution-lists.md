---
title: "Upgrade distribution lists to Office 365 Groups in Outlook"
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: get-started-article
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
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: "Learn how to upgrade one or many distribution lists to Office 365 Groups in Outlook, and how to use PowerShell to upgrade several distribution lists simultaneously."
---

# Upgrade distribution lists to Office 365 Groups in Outlook
  
You can upgrade distribution lists to Office 365 Groups with Outlook. This is a great way to give your organization's distribution lists all the features and functionality of Office 365 groups. [Why you should upgrade your distribution lists to groups in Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)
  
You can upgrade DLs one at a time, or several at the same time.
  
## Upgrade one or many distribution lists to Office 365 Groups in Outlook

You must be an Office 365 global admin or Exchange admin to upgrade a distribution list.
  
1. Sign in with your Office 365 admin account at [https://aka.ms/admincenter](https://aka.ms/admincenter).

2. Go to **Admin centers** \> **Exchange**. 
    
3. In the Exchange Admin Center, go to **Recipients** \> **Groups**.<br/>You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Office 365 groups.<br/> ![Click on Get started](../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)
  
4. Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.<br/>![Select a distribution group](../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)
  
5. Choose the upgrade icon.<br/>![Upgrade to Office 365 groups icon](../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)
  
6. On the information dialog, choose **Yes** to confirm the upgrade. The process begins immediately. Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.<br/>If the distribution list can't be upgraded, a dialog appears saying so. See [Which distribution lists can be upgraded?](#which-distribution-lists-can-be-upgraded).
    
7. If you're upgrading multiple distribution lists, use the drop down to filter which distribution lists have been upgraded. If the list isn't complete, wait a while longer and then choose **Refresh** to see what's been successfully upgraded.<br/>There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**. 
    
8. If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).
    
> [!NOTE]
> If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) for more information about digest emails. 
  
## What to do if the upgrade doesn't work

Distribution lists that fail to upgrade remain unchanged.
  
If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.
  
It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.
  
## How to use PowerShell to upgrade several distribution lists at the same time

If you're experienced at using PowerShell, you might want to go this route instead of using the UI. We have a set of cmdlets that will help you upgrade distribution lists. See below.
  
### Upgrade a single DL

To upgrade a single DL run the following command:
  
`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
  
For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:
  
`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
  
> [!NOTE]
> You can also upgrade a single distribution list to an Office 365 group using the [New-UnifiedGroup](http://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 
  
### Upgrade multiple DLs in a batch

You can also pass multiple DLs as a batch and upgrade them together:
  
```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
  
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:
  
`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`
  
### Upgrade all eligible DLs

There are two ways in which you can upgrade all the eligible DLs.

> [!NOTE]
> The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.
  
1. Get the eligible DLs in the tenant and upgrade them using the upgrade command:
    
```
Get-EligibleDistributionGroupForMigration | Foreach-Object{ 
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress 
} 
```
2. Get the list of all DLs and upgrade only the eligible DLs:
```
Get-DistributionGroup| Foreach-Object{ 
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress 
} 
```
  
## FAQ about upgrading distribution lists to Office 365 Groups in Outlook

### Which distribution lists can be upgraded?

You can only upgrade cloud-managed, simple, non-nested distribution lists. The table below lists distribution lists that CANNOT be upgraded.
  
|**Property**|**Eligible?**|
|:-----|:-----|
|On-premises managed distribution list.  <br/> |No  <br/> |
|Nested distribution lists. Distribution list either has child groups or is a member of another group.  <br/> |No  <br/> |
|Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |No  <br/> |
|Distribution list which has more than 100 owners  <br/> |No  <br/> |
|Distribution list which only has members but no owner  <br/> |No  <br/> |
|Distribution list which has alias containing special characters  <br/> |No  <br/> |
|If the distribution list is configured to be a forwarding address for Shared Mailbox  <br/> |No  <br/> |
|If the DL is part of **Sender Restriction** in another DL.  <br/> |No  <br/> |
|Security groups  <br/> |No  <br/> |
|Dynamic Distribution lists  <br/> |No  <br/> |
|Distribution lists which were converted to **RoomLists**  <br/> |No  <br/> |
|Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**  <br/> |No  <br/> |
   
### How do I check which DLs are eligible for upgrade?

If you want to check whether a DL is eligible or not, you can run the below command:
  
`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroup` 
  
If you want to check which DLs are eligible for upgrade just run the following command:
  
`Get-EligibleDistributionGroup`
  
### Who can run the upgrade scripts?

People with Office 365 global admin or Exchange admin rights.
  
### Why is the contact card still showing a distribution list? What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?

- For Outlook: When someone tries to send an email in Outlook by typing the Office 365 group name after migration, the recipient will be resolved as the distribution list instead of the Office 365 group. The contact card of the recipient will be the distribution lists contact card. This is because of the recipient cache or nick name cache in Outlook. The email will be sent successfully to the Office 365 group, but might cause confusion to the sender.<br/>You can perform the steps in this topic, [Information about the Outlook AutoComplete list](http://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue. 
    
- For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache. You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the Office 365 group contact card. 
    
### Do new group members get a welcome email in their inbox?

No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.
  
### What if one or some of the DLs are not upgraded?

There are some cases in which though DL is eligible but could not be upgraded. The DL does not get upgraded and remains as a DL.
  
- Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded 
    
- DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded
    
### What happens to the DL if the upgrade from EAC fails?

The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.
  


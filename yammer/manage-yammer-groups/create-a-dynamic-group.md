---
title: "Create a dynamic group in Yammer"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 9/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: 6d2a6ec7-1d65-46bb-b253-1bf441ec80a5
description: "Use dynamic groups in Yammer to easily manage group membership through Active Directory."
---

# Create a dynamic group in Yammer

Dynamic groups update automatically as people join, leave, or move within your organization, whenever the user's Azure Active Directory attributes are updated. Dynamic groups work well for large organizations where people change teams, roles, and locations often. Dynamic groups can be created based on a variety of attributes, including role, geography, and department. 
  
## ﻿Requirements

|||
|:-----|:-----|
|**Requirement** <br/> |**Learn more** <br/> |
|Your organization must be using Azure Active Directory Premium.  <br/> |[Azure Active Directory](https://go.microsoft.com/fwlink/?linkId=869572) <br/> |
|Your organization must have a license for Azure Active Directory Premium for each user added to at least one dynamic group.  <br/> |[Azure Active Directory pricing](https://go.microsoft.com/fwlink/?linkId=869572) <br/> |
|The person setting up the groups must have permissions to update Azure Active Directory.  <br/> |[Built-in roles for Azure role-based access control](https://go.microsoft.com/fwlink/?linkId=869570) <br/> |
|Creating dynamic groups requires using PowerShell to change the associated Active Directory group to make it dynamic.  <br/> |[Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540) <br/> |
|Only Office 365 connected Yammer groups can be set up as dynamic groups. This means you must be enforcing Office 365 identity in Yammer, and your Yammer network must have existing Office 365 connected groups.  <br/> |[Yammer and Office 365 Groups](yammer-and-office-365-groups.md) <br/> [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md) <br/> [Create a group in Yammer](https://support.office.com/article/b407af4f-9a58-4b12-b43e-afbb1b07c889) <br/> |
   
## Create a dynamic group in Yammer

1. Create an Office 365 connected group in Yammer. 
    
2. Use PowerShell to change membership management for an Active Directory group to make it dynamic. For instructions, see [Dynamic membership rules for groups in Azure Active Directory](https://go.microsoft.com/fwlink/?linkId=869529)
    
## FAQ

 **Q: Are there limits to the number of members in dynamic groups?**
  
A: Yes. Dynamic groups in Yammer have a limit of 100K members. After 100K members, new members will not be synced to the group in Yammer.
  
 **Q: Do users experience any differences in Yammer when using a dynamic group?**
  
A: Yes. Groups with dynamic membership do not have the **Join** and **Leave** buttons in the top navigation. Instead, users either see **Member** for dynamic groups to which they belong, or **Reserved** if they are not members of the group. 
  
![Top navigation for dynamic groups that you are a member of](../media/9d0bb1db-2575-4bb9-bd02-869a05a7cc89.png)
  
![Top navigation for dynamic groups that you are not a member of](../media/d1d48f64-896e-466d-96f8-007f36188991.png)

**Q: What is the difference between an Office 365 connected group and a dynamic group?**
A. For an [Office 365 connected group](yammer-and-office-365-groups.md), group membership changes made in any Office 365 app such as Outlook, are available in the group in Yammer. For a dynamic group, changes made in the group membership in Azure Active Directory (AAD) are available in the Yammer group. 

Typically large organizations use dynamic groups if they use AAD to track department membership, roles, and location, and have Office 365 connected groups for each department, role, and location. Organizations which don't use AAD in this way typically don't use dynamic groups.
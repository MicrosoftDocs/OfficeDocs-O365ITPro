---
title: Set up the organization directory for Kaizala
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
audience: Admin
ms.date: 05/08/2019
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.reviewer: nitinjms2
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to set up the organization directory for Kaizala.
---
# Set up the organization directory for Kaizala

[!INCLUDE [retirement-note](includes/retirement-note.md)]

Kaizala organization admins can define and manage user attributes for an organization. They can add custom user attributes (such as employee ID or manager) in the Kaizala management portal, which makes it easier for admins and other users to identify a user.

Organization admins can add new attributes and define settings that each attribute can have.
  
## Set up attributes for all users in the organization

1. On the [Kaizala management portal](https://manage.kaiza.la), from the left navigation bar, select **Directory** > **More**.
2. Select **Manage Attributes** from the drop-down menu. 
3. To add a new attribute, select **Add New**. Then choose from a range of pre-defined suggested attributes or add a new one. 
    
For a new attribute, you can enter the name of the attribute, select its type (string, number, Yes/No, and date/time), and determine whether the values for the attribute are required or not. For each attribute, the following property needs to be set:
 
 |&nbsp; |&nbsp; | Default value | Behavior|
 |:--:  |:------------:|:------:|:-------:|
    | Allow users to edit values for themselves | ON | If set ON, users themselves and tenant admins can edit values for the attributes. <br>If set OFF, only tenant admins can edit values. |
    | Show this column to all users | ON | If set ON, this particular column is visible to all users. <br>If set OFF, only tenant admins can see this column. ||
    
  - You can add multiple attributes at the same time.
  - When you've finalized the list of attributes, select **Save** to add the new changes to the organization's attribute list.

---
title: "Limited functionality in Yammer in Internet Explorer 10 document mode"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MET150
ms.assetid: ca3f639d-2843-4ebb-9b54-95ebd2b8ecf1
description: "When posting a message to Yammer using Internet Explorer 10 document mode, at-mentions and link previews are not available."
---

# Limited functionality in Yammer in Internet Explorer 10 document mode

If you are using an older SharePoint site with an embedded Yammer conversation, as of March 5, 2018, some functionality will no longer be available.
  
- You can't use @mention to make sure a specific person gets notified about your post. Instead, click **Add people to notify**.

    ![Click to notify people about your post.](../media/455b84df-defb-4da6-92f7-0ca21cc8d930.png)
  
- When you copy and paste a link in your post, a preview for the link won't be created. There is no workaround. 

    ![The link preview will not be visible in Internet Explorer 10 document mode.](../media/dc472543-7c58-486a-b72b-4cb22cc750aa.png)
  
This happens when your SharePoint site is set to use Internet Explorer 10 Document mode. This setting is controlled by your SharePoint site owner.
  
## What are the system requirements for Yammer?

Yammer follows the [Office 365 system requirements](https://go.microsoft.com/fwlink/?linkid=809136). Office 365 does not support Internet Explorer 10 or earlier versions.

> [!NOTE]
> Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting November 30, 2020.) [Learn more](https://aka.ms/AA97tsw). Please note that Internet Explorer 11 will remain a supported browser. Internet Explorer 11 is a component of the Windows operating system and [follows the lifecycle policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is installed.
  
## What is Internet Explorer 10 document mode?

[Document modes](/openspecs/ie_standards/ms-iedoco/d3fffb13-31cc-4dd0-b38c-2b6aaabc153e) are used by web developers to specify which Internet Explorer versions a website is designed for. SharePoint site owners can choose compatibility with specific document modes.
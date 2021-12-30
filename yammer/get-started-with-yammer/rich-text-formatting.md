---
title: "Rich text formatting for Yammer messages"
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
description: "Users can now format Yammer posts using bold, italic, bullets, numbered lists, and links. "
---

# Rich text formatting Yammer messages
 
Beginning March 15, 2019, we are rolling out rich text formatting for Yammer posts. This includes bold, italic, links, bullets, and numbered lists.

Composing messages with rich text formatting is only available on the web client and Yammer desktop.

- Mobile Yammer apps will display formatted messages, but users can't edit those messages or format new messages from the mobile device.

- Composing and viewing formatted messages won't be available immediately on the Yammer SharePoint web part or Yammer tab in Teams. This functionality will be added later in 2019.

## How do I know if we have rich text available?

If your organization has received this new feature, when you post a new message, here's what the bottom of the message looks like:

![Yammer message with rich text formatting.](../media/with-rich-text.png)

If you don't have rich text, here's what the bottom of the message looks like:

![Yammer message without rich text formatting.](../media/without-rich-text.png)

## Implications for export

When you export formatted messages using [Export Network Data](../manage-security-and-compliance/export-yammer-enterprise-data.md) two columns for the message text are included in messages.csv and messageVersions.csv:
- **body**: includes the unformatted message text 
- **html_body**: includes the message text formatted with HTML

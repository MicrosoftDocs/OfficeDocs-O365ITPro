---
title: "FAQ: eDiscovery in Yammer"
f1.keywords:
- NOCSH
ms.author: pamgreen
author: ToniSFrench
manager: pamgreen
ms.date: 11/25/2019
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid: 
- MET150
- YAE150
ms.assetid: a9a25f87-e643-41ce-9630-b74d10e40b1a
description: Answers to frequently asked questions about eDiscovery in Yammer.
ROBOTS: NOINDEX, NOFOLLOW 
---

# FAQ: eDiscovery in Yammer networks

Here are answers to frequently asked questions about eDiscovery in Yammer networks.

## General

**Q: What is eDiscovery?**

A: Electronic Discovery (commonly referred to as “eDiscovery”) refers to the process by which electronic documents are obtained during the “discovery” phase of legal proceedings. eDiscovery is subject to rules of civil procedure and agreed-upon processes, often involving review for privilege and relevance before data are turned over to the requesting party.

**Q: How does Security & Compliance Center for Microsoft 365 support eDiscovery?**

A: Security and Compliance Center offers eDiscovery and Advanced eDiscovery, which you can use to search for content in Exchange Online mailboxes, Microsoft Teams, Yammer conversations, SharePoint Online content, and more. You can use eDiscovery cases in the Security and Compliance Center to identify, hold, and export content found in mailboxes and websites.

See more information and examples about [eDiscovery](/office365/securitycompliance/ediscovery).

**Q: How does Yammer support eDiscovery?**

A: Yammer supports eDiscovery (E3) and Advanced eDiscovery (E5) in the Security and Compliance Center. Once a Yammer Enterprise network is in [Native Mode for Microsoft 365](../configure-your-yammer-network/overview-native-mode.md), all messages and files are discoverable.

**Q: What is Advanced eDiscovery for Microsoft 365?**

A: Advanced eDiscovery (E5) builds on eDiscovery (E3) and helps you analyze unstructured data within Microsoft 365, perform more efficient document reviews, and make decisions to reduce data for eDiscovery.

See more advanced information about [eDiscovery in Microsoft 365](/office365/securitycompliance/office-365-advanced-ediscovery).

**Q: Can users see that Yammer is storing their messages for eDiscovery?**

A: eDiscovery will put a copy of all Yammer messages into a hidden folder in the user’s Exchange mailbox. If a user searches their mailbox for keywords contained in their Yammer messages, these messages will be visible in their mailbox.

## Native Mode

**Q: What is Native Mode?**

A: In Native Mode, all Yammer users are in AAD, all groups are Microsoft 365 Groups, and all files are stored in SharePoint Online. As of November 2019, all new Yammer Networks start in Native Mode. Existing Yammer Networks can [migrate to Native Mode](../configure-your-yammer-network/native-mode.md).

## Workflow

**Q: How do I discover all Yammer messages where a custodian is a participant?**

A: eDiscovery (E3) has no pre-defined concept of a custodian. Within Advanced eDiscovery (E5), you can define a custodian through the custodian workflow. To capture Yammer messages, select Exchange as a data source. Once the custodian is defined, you can select the custodian from within the search workflow and use the Type condition to select all Yammer message types.

**Q: How do I discover all messages and files in Yammer groups a custodian is a member of?**

A: eDiscovery (E3) has no pre-defined concept of a custodian. In Advanced eDiscovery (E5), you can select additional data sources from the Add Custodians workflow to select the Yammer groups of which the custodian is a member. Messages and files are available for discovery for all groups you select when the custodian is selected during search.  

**Q: How do I search for Yammer messages of a specific type?**

A: On the Search criteria page of the search workflow within Microsoft 365 Security & Compliance center, select **Add conditions**. From the condition selector, choose **Type**, > **Add/Remove** more options. This will bring up the advanced Type selection box where you can choose from the following Yammer Message Types: Yammer standard messages, Yammer praise messages, Yammer poll messages, Yammer question messages.

**Q: How do I search for Yammer messages in non-custodial locations?**

A: You can search group mailboxes for messages and SharePoint sites for files. You can access these locations through the Non-Custodial locations page of the search workflow.

**Q: How do I search all files in Yammer for my entire organization??**

A: From the search workflow, click **Next** until you get to the Non-custodial locations screen. In the second section of this screen, you will see “Yammer sites” alongside “SharePoint sites” and other options. Flip the switch for **Select all** to access Yammer files for the entire network.

**Q: How do I search for files within specific groups?**

A: From the search workflow, click **Next** until you get to the Non-custodial locations screen. In the second section of this screen, you will see “Yammer sites” alongside “SharePoint sites” and other options. To search for the files within specific groups, select **Choose sites** to open the Edit locations screen. Select **Choose sites**, then type the URL for the SharePoint site associated with the group you want to search. The search results will not be limited to the Files that have been uploaded through Yammer, but will include all Files added to that SharePoint site from any source.

## User Scenarios

**Q: When are messages and files subject to a litigation hold?**

A: Messages and files are subject to a hold when the location they are stored (e.g., custodian of the message or file in Advanced eDiscovery, or the Exchange Online Mailbox or SharePoint Online site where the message or file in eDiscovery), is on hold.

**Q: What happens to a message when it is subject to a litigation hold?**

A: Messages subject to a hold will be treated as follows for the duration of the hold:

**User Actions:**

- *Delete*: Custodians will no longer see the message in Yammer, but the message will be discoverable in the Security & Compliance Center.

- *Edit*: Custodians will only see the most recent version of the message in Yammer, but each version of the message generated during the hold will be discoverable (historical versions pre-dating the hold are not held).

- *Move*: Custodians will only see the message in its new group in Yammer, but the message will be discoverable in all groups where it existed during the hold.

- *React*: Custodians will only see the current state of reactions on a message, and only the current state of reactions is discoverable.

**Q: What happens to a message when it is *not* subject to a litigation hold?**

A: In the absence of a hold, messages will be treated as follows:

**User Actions:**

- *Delete*: Message is removed from all mailboxes and is placed in a recoverable items folder where it will stay for less than 30 days before being fully deleted. It is discoverable while in recoverable items, but once it is deleted from that folder, it is no longer discoverable.

- *Edit*: Only the current version is discoverable.

- *Move*: The message is only discoverable in its current group in Yammer.

- *React*: Only the current state of reactions to a message are discoverable.

**Q: What happens to a file when it is subject to a litigation hold?**

A: Files subject to a hold will be treated as follows for the duration of the hold:

**User Actions:**

- *Delete*: Message is removed from all mailboxes and is placed in a recoverable items folder where it will stay for less than 30 days before being fully deleted. It is discoverable while in recoverable items, but once it is deleted from that folder, it is no longer discoverable.

- *Edit*: Only the current version is discoverable.

- *Move*: The message is only discoverable in its current group in Yammer.

- *React*: Only the current state of reactions to a message are discoverable.

**Q: What happens to a file when it is not subject to a litigation hold??**

A: In the absence of a hold, files will be treated as follows:

**User Actions:**

- *Delete*: The file is removed from the group and is no longer discoverable.

- *Edit*: Only the current version is discoverable.

- *Move*: The file is only discoverable in its current group.

**Q: Are private messages discoverable?**

A: Yes.

**Q: Are messages in groups discoverable?**

A: Yes, all message types, except for system messages, are discoverable within the group search workflow detailed above.

**Q: Are files attached to group messages discoverable?**

A: Yes. Files attached to messages in groups are discoverable.

**Q: Are messages in All Company discoverable?**

A: Yes, all user generated messages in the All Company group are discoverable. System messages are excluded.

**Q: Are Polls discoverable?**

A: Polls are discoverable for the author and anyone who has voted. The Poll results at the time of the search will be returned.

**Q: Are Q&A messages discoverable?**

A: Yes. Questions have a special message type which can be filtered on. eDiscovery does not record which answer was marked the best answer.

**Q: Are GIFs in messages discoverable?**

A: If the GIF is an attachment to a message, it will be discoverable the same as any other attachment. If a GIF is present from a hyperlink, the hyperlink and the GIF will be displayed in the Security and Compliance Center results. In the case of a hyperlink, the GIF displayed will be whatever is associated with that link at the time it is being viewed. If the owner of the GIF content changes the content at that link, the changed content will be shown (both in Yammer and in eDiscovery).  

**Q: Are system messages discoverable?**

A: Messages that are generated by the system and not a user (such as, notifications about a user being added to a group) are not discoverable on their own. If a user replies to a system message, the system message will be shown as a part of the conversation when Advanced eDiscovery (E5) returns the user generated reply in search results or a working set. In eDiscovery (E3), only the user-generated reply will be discoverable.

**Q: What happens when a user leaves the company and their mailbox is deleted?**

A: If the user is on hold, all their discoverable content will be stored until the hold is released. Once the user mailbox has been deleted, they are no longer a custodian.
If the user has messages in a group, those messages will still be discoverable in the group mailbox.

**Q: What happens to private messages when all people on the message have their mailboxes deleted?**

A: When all users in a conversation have their mailboxes deleted, the message will no longer be discoverable.

**Q: Is rich text formatting of a message captured when a message is discovered?**

A: Yes. Rich text formatting will be visible in the search results when a message is discovered. This includes emojis, which should show up in eDiscovery the same way they are displayed in Yammer.

**Q: What happens when a group is renamed?**

A: When a group is renamed, you will only be able to discover the group using its new name. All messages and files in the group continue to be discoverable.

**Q: Is Yammer content in external networks discoverable in the Security and Compliance Center?**

A: No.

**Q: Is Yammer content for users who have on-premise mailboxes discoverable in the Security and Compliance Center?**

A: Yes.

**Q: What happens if a user is removed from a private conversation?**

A: Once a user is removed from a private conversation, they are no longer a custodian of any messages in that conversation unless their mailbox is on hold.

**Q: What happens if a user is removed from a private group?**

A: Once a user is removed from a private group, they will still be considered a custodian of the messages they are CC’ed on, but not any other messages in the group.

**Q: What happens when a user is added to an existing private message conversation?**

A: When a user is added to an existing private message conversation, they become a custodian of all the messages within that conversation.

**Q: What happens if someone is CC’ed in a message and then the CC is removed?**

A: If a user is CC’ed in a message and then the CC  is removed, they will no longer have access to that message unless it is public.

> [!NOTE]
> CC is often referred to as @mention.

## See also

[eDiscovery in Microsoft 365](/office365/securitycompliance/ediscovery)

[Overview of the advanced eDiscovery solution in Microsoft 365](/office365/securitycompliance/office-365-advanced-ediscovery)
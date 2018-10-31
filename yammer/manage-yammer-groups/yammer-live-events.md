---
title: "Live events in Yammer"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 8/5/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOP150
- MOE150
- MEW150
- MED150
ms.assetid: 4ece0ee2-c268-4636-bf2a-16e454befe57
description: "Learn what's needed to host live video events for Yammer users."
---
# Live events in Yammer

> [!NOTE]
> The information in this topic applies to the public preview release of live events supported by Yammer, Teams, and Stream.

Yammer is where communities thrive - a community centered around leaders engaging with their employees, a community of common interest, a community of people who share an identity, or a community of learning and shared practices. To bring the members of a community together centered around an event, Yammer group admins can host a live video event using Yammer, Teams, and Stream. Each event includes Yammer conversations before, during, and after the event.

Due to the open nature of Yammer conversations, Yammer is a particularly well-suited place to foster connection and engagement between leaders and employees at every level in your organization. Hosting your next live event in your Leadership Connection community is a great way for leadership teams to drive alignment of your people around shared purpose and goals. Leaders realize that organizations who do this well have an advantage in attracting and retaining an engaged workforce.

You can create a public group to reach all employees, or use a private group for your live events, and only those with membership in the group can participate. Before the event, you have a place in Yammer to direct employees and/or group members to where you can show preview clips to generate buzz, announce an open call for questions in a Q&A segment, or just a place for people to chat about the upcoming event. 

Following an event, it’s easy to make the recording available on an event page, allowing employees to watch the event on their own schedule. For employees who are in different time zones or unable to attend live, the conversation keeps going so they still feel connected to leaders and peers, helping to overcome geographical or organizational boundaries.

For information about what a live event looks like, see [Attend a live event in Yammer](https://support.office.com/en-us/article/attend-a-live-event-in-yammer-4b08133c-9ebb-47b0-ab60-4dbfd4bfc965). For steps to create a live event, see [Organize a live event in Yammer](https://support.office.com/en-us/article/organize-a-live-event-in-yammer-105dd7af-9caf-4a5e-8a44-56d203e96551).

## Requirements

Here’s what needs to be in place for your organization to create a live event:

- Everyone who participates in the meeting must have an Office 365 subscription that includes licenses for Yammer, Teams, and Stream (An Office 365 Enterprise E3, E5 subscription). If you are new to Teams, visit the [Microsoft Teams help center](https://support.office.com/en-us/Teams). If you are new to Stream, visit the [Microsoft Stream help center](https://docs.microsoft.com/en-us/stream/). 

- In Yammer, your organization must have Enforce Office 365 identity selected, and you must be using Office 365 connected groups. For more information see [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md) and [Yammer and Office 365 groups](../manage-yammer-groups/yammer-and-office-365-groups.md).

- You must have a Yammer group that includes everyone who will be invited to the live event. For more information, see [Create a group in Yammer](https://support.office.com/en-us/article/create-a-group-in-yammer-b407af4f-9a58-4b12-b43e-afbb1b07c889) and [Manage a group in Yammer](https://support.office.com/en-us/article/manage-a-group-in-yammer-6e05c6d6-5548-4c88-89cd-e6757a514ef2). The All Company group can’t be used for live events.

- Your organization must have enabled Teams in order to enable event creation. For steps to enable Teams, see [Microsoft Teams getting started guide for IT admins](https://support.office.com/en-us/article/microsoft-teams-getting-started-guide-for-it-admins-e7b992dc-de27-4303-8973-7a1ca8ad7cfb). 
    - For External Encoder events, attendees do not need Teams enabled, as they attend directly from Yammer. 
    - For QuickStart events, attendees need Teams enabled.  
    More information on these options can be found below.

## Live event options

There are three general methods of creating a live event: a Yammer live event, a Stream-only live event, or a Microsoft Teams live event. What you choose depends on your needs and your audience.

### Yammer live event

To view your event directly inside of Yammer, create the live event from an Office 365 Group connected Yammer group inside of Yammer.

1. As a Yammer group admin, select **Group Actions** > **Create a Live Event**. This will open Teams.

2. Fill out the **Title**, **Date**, and **Time**.

3. On the following screen, select one of the following Live event production types:

    - **Quick start**: Quick start uses the Microsoft Teams client as your producer experience. This is a lightweight option to create the event and invite remote presenters and panelists to participate. This option lets you easily broadcast web cams, slides, screen sharing, etc. If you pick this option viewers will be linked back into Microsoft Teams to watch the broadcast.
    
    - **External encoder**: For a higher quality production value, the live event is produced using an external hardware or software encoder via Microsoft Stream. Use this option if you already have a production setup (for example, media mixers) that supports streaming to an RTMP service. This method is typically used in auditorium events, such as town halls, where a stream from a media mixer is broadcast to the audience.

        After the live event is done the same URL/embed code will convert into a recording of the live event and be available immediately in Stream. If you pick this option viewers will be able to watch the live event directly inside of Yammer or in Stream.

### Stream-only live event

For a Stream-only live event, create your live event directly from within Microsoft Stream.

> [!IMPORTANT]
> This live event is not connected to either Yammer or Teams.

The live event is produced using an external hardware or software encoder via Microsoft Stream. Use this option if you already have a production setup (for example, media mixers) that supports streaming to an RTMP service. This method is typically used in auditorium events, such as town halls, where a stream from a media mixer is broadcast to the audience.

For full setup information, see [Creating a live event in Microsoft Stream](https://docs.microsoft.com/en-us/stream/live-create-event).

### Teams live event
Live events can be directly set up from Microsoft Teams, but these live events won't be connected to a Yammer group.

If you pick a **Quick start** event to use the Microsoft Teams client as the producer experience, the live event will not show up in Microsoft Stream.

If you pick an **External encoder** event, the live event will show up both in Microsoft Teams and in Microsoft Stream.
 
## See also

[Microsoft Teams live event overview](https://support.office.com/en-us/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US)

[Microsoft Stream live event overview](https://docs.microsoft.com/en-us/stream/live-event-overview)
---
title: "Live events in Yammer"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 5/28/2019
audience: Admin
ms.topic: overview
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOP150
- MOE150
- MEW150
- MED150
ms.assetid: 4ece0ee2-c268-4636-bf2a-16e454befe57
description: "Learn what's needed for group admins to host live video events for Yammer users."
---
# Live events in Yammer

To bring the members of a community together centered around an event, Yammer group admins can host a live video event including Yammer conversations before, during, and after the event. Live events can be held in a public group to reach all employees or in a private group so that only those with membership in the group can participate. 

This article lists the Yammer network requirements, licenses, and permissions for organizing and participating in live events.

- For an overview of how to plan, staff, and communicate your live event, see [How to host a Live Event in Yammer: A step-by-step playbook](https://aka.ms/LiveEventsinYammerplaybook).

- To download templates for communications, go to [Live Event Yammer templates](https://aka.ms/LiveEventYammerTemplates) 
 
- For steps to create a live event in Yammer, see [Organize a live event in Yammer](https://support.office.com/article/organize-a-live-event-in-yammer-105dd7af-9caf-4a5e-8a44-56d203e96551).

- To see what a live event in Yammer looks like, see [Attend a live event in Yammer](https://support.office.com/article/attend-a-live-event-in-yammer-4b08133c-9ebb-47b0-ab60-4dbfd4bfc965). 

## Types of live events

To understand how Yammer, Stream, and Teams work together in live events, see [Overview of live events](https://docs.microsoft.com/microsoftteams/teams-live-events/what-are-teams-live-events#overview). 
Live events can be created and viewed in Yammer, Stream, or Teams. This article explains the requirements for creating and viewing a live event in Yammer. 

There are two ways live events in Yammer can be produced. The requirements depend on which video production methods you intend to use in your organization.

- **Use an external encoder to produce your live event**: 
    - This type of event is typically used for large scale events such as executive town halls, where a single stream from a media mixer is broadcasted to the audience. 
    - You need to use an an external encoder to produce the event.
    - You need a Stream license, as this type of event is powered by Stream.
    - Attendess can view the event in Yammer.
    - The Yammer Live Event feed can be viewed in Yammer, Streams, and Teams.

- **Use Teams to produce your live event**:  
    - This type of event uses Teams to encode the broadcast stream.
    - This is used for simple events when all you need are the audio and video devices connected to the presenter's computer, or when you're inviting a remote presenter for the event. 
    - Use Teams to share content from the presenters webcab and screen.
    - This type of event requires a Teams license.
    - The Yammer Live Event feed can be viewed in Yammer, Streams, and Teams.
    - Attendees can view this event in Teams only.

## Yammer network and group requirements

 - To host a live event in Yammer, your organization must have **Enforce Office 365 identity** selected, and you must be using Office 365 connected Yammer groups. For more information see [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md) and [Yammer and Office 365 groups](../manage-yammer-groups/yammer-and-office-365-groups.md).

- The event must be held in either a public Yammer Office 365 connected group, or a private Yammer Office 365 connected group that includes everyone who will be invited to the live event. For more information, see [Create a group in Yammer](https://support.office.com/en-us/article/create-a-group-in-yammer-b407af4f-9a58-4b12-b43e-afbb1b07c889) and [Manage a group in Yammer](https://support.office.com/en-us/article/manage-a-group-in-yammer-6e05c6d6-5548-4c88-89cd-e6757a514ef2). 

- The All Company group can’t be used for live events.

## Requirements for live event attendees

- Everyone who attends a Yammer live event must have an Office 365 subscription that includes a license for Yammer (Office 365 A3, A5, F1, E1, E3, or E5).

- Everyone with a Yammer license can attend live events in public groups. 

- For live events in private groups, attendees must be members of the private group in which the live event is hosted. 

## Permissions for scheduling, creating, and producing live events in Yammer

Yammer has partnered with Teams and Stream to provide the best technology for running your live event. Because of this, creation and production of live events require Stream and/or Teams licenses and specific permissions. These permissions are not controlled in Yammer settings. The requirements depend on the production methods you plan to use.

- **Scheduling**:

    - A Teams license is required to schedule a Yammer live event.

    - Only Yammer group admins can create and schedule a live event.

- **Producing**:
    - **Events produced using an external app or device**:
        For external app or device events, the person who presents or produces the event must have a Stream license and permission to create live events. By default, only Microsoft Stream administrators have permission to create live events. Use the Stream admin settings to give permission to specific users. For steps to grant or remove permissions in Stream, see [Administration controls for live events in Stream](https://docs.microsoft.com/en-us/stream/live-event-administration).

    - **Events produced using Teams**:
        The person who presents or produces the event must have a Teams license and specific policies set in Teams. For requirements, see [Who can create and schedule live events in Teams](https://docs.microsoft.com/microsoftteams/teams-live-events/plan-for-teams-live-events#who-can-create-and-schedule-live-events). For steps to set policies, see [Set up live events policies](https://docs.microsoft.com/microsoftteams/teams-live-events/set-up-for-teams-live-events#step-3-set-up-live-events-policies). 
 
### Restrict creation of live events in Yammer

You can prevent creation of live events produced in teams, live events produced with other tools, or both.

- To prevent creation of live events produced in Teams, remove permissions in Teams for live event scheduling. If a user does not have a license or permission to create a live event in Teams, when they create a live event in Yammer, the produce in Teams option is unavailable.

- To prevent external production for live events, don't give Stream permissions to any users. If a user does not have a license or permission to create a live event in Stream, when they try to create a live event in Yammer, the external production option is are unavailable.

- To prevent both types of live events, make sure Yammer users do not have permission to create live events in Teams and in Stream.

## FAQ

**Q: How many participants can view a live event at once?**

A. Currently the limit is 10,000 participants.

## See also

[Organize a live event in Yammer](https://support.office.com/article/organize-a-live-event-in-yammer-105dd7af-9caf-4a5e-8a44-56d203e96551)

[Microsoft Teams live event overview](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US)

[Microsoft Stream live event overview](https://docs.microsoft.com/en-us/stream/live-event-overview)
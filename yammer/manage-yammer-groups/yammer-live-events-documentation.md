---
title: "Yammer Live Events Convergence Preview Documentation"
description: "Yammer Live Events Convergence Preview Documentation"
ms.author: jebizie
author: v-jebizie
manager: dmillerdyson
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: yammer
ms.localization_priority: Priority
search.appverid:
- MET150
---

# Introduction 
Yammer Live Events create connection and engagement between leaders and employees, bringing live video and interactive discussions to a whole new level.

As a part of bringing new Teams experiences into Yammer, we’re delighted to announce the public preview of broadcasting Yammer Live Events over the Teams player instead of using Microsoft Stream. This means that attendees will view newly created Live Events over the Teams Embed Player instead of the Microsoft Stream player. To learn about participating in the Yammer Live Events Convergence Preview, please see the [Preview Terms & Conditions and FAQ](microsoft.sharepoint-df.com/:w:/t/moderatedqainteamspoweredbyyammer/EcuX4_rPu3pCgzqEoUzLm5QBHSKvmsRt4h8_L2PzsXXYeQ?e=Y0DsTy).

There are two **new** ways in which Yammer Live Events can be produced: 
1.	**Microsoft Teams QuickStart (new)**: Use Microsoft Teams to produce your live event. This is used for simple live events where all you need are the audio and video devices to the presenter’s computer, or when you are inviting a remote presenter for the event.
(a) This type of event uses Teams to encode the broadcast stream.
(b)	Use Teams to share content from the presenter’s webcam and screen.
(c)	Attendees can view this event on Yammer.

2.	**Microsoft Teams external app or device (new)**: Use this This type of event is typically used for large-scale events such as executive town halls, where a single stream from a media mixer is broadcasted to the audience.
(a)	This type of event uses Teams to encode the broadcast stream.
(b)	You need to use an [external encoder (app or device)](docs.microsoft.com/stream/live-encoder-setup) to produce the event.
(c) Attendees view the event in Yammer.

## Yammer network and group requirements
* To host a live event in Yammer, your organization must have **Enforce Office 365** identity selected, and you must be using Microsoft 365 connected Yammer groups. For more information see Enforce Office 365 identity for [Yammer users](/yammer/configure-your-yammer-network/enforce-office-365-identity) and [Yammer and Microsoft 365 groups](/yammer/manage-yammer-groups/yammer-and-office-365-groups).
* The event must be held in either a public Yammer Microsoft 365 connected group, or a private Yammer Microsoft 365 connected group that includes everyone who will be invited to the live event. For more information, see [Create a group in Yammer](support.office.com/article/create-a-group-in-yammer-b407af4f-9a58-4b12-b43e-afbb1b07c889) and [Manage a group in Yammer](support.office.com/article/manage-a-group-in-yammer-6e05c6d6-5548-4c88-89cd-e6757a514ef2).

## Requirements for Live Event Attendees
*	Everyone who attends a Yammer live event must have a Microsoft 365 or an Office 365 plan that includes a license for Yammer (for example, Office 365 A3, A5, F1, E1, E3, or E5).
*	Only members of your Yammer network can attend live events. Guests and external users do not have access to live events.
*	To attend a live event in Teams, a Teams license is required.
 
## Permissions for scheduling, creating, and producing live events in Yammer
Yammer has partnered with Teams to provide the best technology for running your live event. Because of this, creation and production of live events require Teams licenses and specific permissions. These permissions aren't controlled in Yammer settings. The requirements depend on the production methods you plan to use.

*	**Scheduling**:
    *	Only Yammer Community managers can create and schedule a live event in Yammer.
    
    *	When a live event is scheduled in Yammer, the organizer, any co-producers, and presenters will receive a calendar invite with information about this live event (as a placeholder). This invite is not sent to attendees.

*	**Producing**:
    *	**Events produced using an external app or device**: To produce any kind of event in Yammer, you will need to have your Microsoft Teams license enabled. For external app or device events, the person who presents or produces the event must have a Teams license and permission to create live events. By default, only Microsoft Stream administrators have permission to create live events. Use the Stream admin settings to give permission to specific users. For steps to grant or remove permissions in Stream, see [Administration controls for live events in Stream](docs.microsoft.com/stream/live-event-administration).

    * **Events produced using Teams**: The person who presents or produces the event must have a Teams license and specific policies set in Teams. For requirements, see [Who can create and schedule live events in Teams](/microsoftteams/teams-live-events/plan-for-teams-live-events#who-can-create-and-schedule-live-events). For steps to set policies, see [Set up live events policies](/microsoftteams/teams-live-events/set-up-for-teams-live-events#step-3-set-up-live-events-policies).

## FAQ
1.	**How many participants can view a live event at once?** 
Currently, the limit is 10,000 participants. 

2.	**What media player is used for live events?** 
Events produced using Teams or an external app use the Teams player. Both work for attendees to view on Yammer Web, and mobile devices (iOS and Android).

3.	**Why can't I view the video?**
To maintain the privacy of live event content, only authorized users can join a live event and are authenticated as they load the live event page. If authentication isn't successful, you won't be able to view the video. To fix this, use your browser's settings to make sure that cookies are enabled and that any extensions that block tokens are disabled. After changing the settings, refresh the event page.

4.	**Where are the videos stored once they are produced?**
The Video-on-Demand is stored in the SharePoint Community where the event was hosted is automatically shared with members of the private community, or with everyone across the Yammer network if the event was produced in a public community.

5.	**Can Event Producers edit videos?**
Yes, the videos can be edited in SharePoint. The edited video in SharePoint is automatically 	updated for attendees to watch. Please note that it could take 10 minutes before producers can 	edit their videos after the event is completed. 

6.	**What happens to the old live events videos that were broadcast via Microsoft Stream?**
Live Events videos created using Stream will continue to function – attendees can continue to watch those videos on demand broadcasted on Microsoft Stream. We will announce a process to migrate the Stream videos to SharePoint in the future.




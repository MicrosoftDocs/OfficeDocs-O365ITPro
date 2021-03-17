---
title: "Collaborate with guests in a Yammer community"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 03/15/2021
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn more your options for working with guests in a Yammer community, depending on how your organization's Yammer network is structured."
---

# Collaborate with guests in a Yammer community

External collaboration is a key ingredient for the success of any organization. Yammer guests allow you to call in experts, such as consultants or vendors, from outside your organization. Users can invite guests to a community and quickly start a rich conversation by sharing access to community resources like files. This ease-of-use makes external collaboration one of the most- used features in Yammer today.

![Yammer business-to-business guest support](../media/yammer-b2b-azure-guests.png)

There are two methods of working with guests, depending on how your organization’s Yammer network is structured. A Yammer network [aligned to native mode](../configure-your-yammer-network/overview-native-mode.md) leverages the Azure AD-B2B guest framework to power external users while a Yammer network that is currently not aligned to native mode uses the Yammer- specific guest framework.

## Comparison of guest experiences

| Yammer community aligned to Native Mode <br/> | Yammer community NOT not aligned to Native Mode <br/> |
|:-----|:-----|
|Guests are powered by the AzureAD-B2B guest framework |Guests are powered by the Yammer guest framework. |
| External users can be added as guests to any Yammer community. |External users can be added as guests only in external communities |
| Only community admins can add guests to a community.  |Group members can add guests to external communities. |
| Guests can be added to communities in Yammer networks hosted in both the United States and EU Geo regions.  |Guests can be added to external communities in Yammer networks hosted in the United States. Yammer communities in EU Yammer networks cannot host external communities' regions.  |
| Simplified guest modes: External users can be added as guests to Yammer communities. The scope of access for guest mode is the community boundary. |Three guest modes are supported: thread-level guests, community level guests, and network-level guests with access scoped to a Yammer thread, community, and network respectively. <br/> |

## Learn more about guests and external networks

The Yammer guests feature allows organizations to call in experts such as vendors, suppliers, or consultants from outside the organization. Yammer networks aligned to native mode use Azure Active Directory Business-Business (AzureAD-B2B), a secure, compliant external collaboration framework, to power guests To learn more about AzureAD-B2B guests in Yammer, visit AzureAD-B2B guests in Yammer.

To work with external users, if your organization isn’t using native mode, you can create an external group. You must create the group as an external group--you can't change an existing internal group to be an external group. To learn more about guests in non-native Yammer networks, visit  here.

## Related articles

[Overview of Native Mode](../configure-your-yammer-network/overview-native-mode.md)
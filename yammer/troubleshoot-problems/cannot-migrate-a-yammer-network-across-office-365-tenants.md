---
title: You can't migrate a Yammer network across Office 365 tenants
description: Describes an issue in which you can't migrate a Yammer network across Office 365 tenants.
author: TeresaFG-writer
manager: pamgreen
audience: ITPro
ms.service: sharepoint-online
ms.topic: article
f1.keywords:
- NOCSH
ms.author: v-njeremy
---

# Cannot migrate a Yammer network across Office 365 tenants

## Problem

You either plan to add or migrate a network domain from one Office 365 tenant to another Office 365 tenant, or have already done so. Now you want to associate your Yammer network, which is mapped from the domain of your original tenant, with your new tenant. In this situation, you may experience one or more of the following symptoms:

- Users in specific domains can't sign in to a Yammer network when they use their Office 365 sign-in for Yammer.

- You want to migrate a network to your Yammer primary network. However, the domain doesn’t appear in the Network Migration Wizard.

## Solution

This is expected behavior. Migrating Yammer networks across Office 365 tenants isn't supported. For more information, see the following Microsoft websites:

- The "Network migration" section of [Administration and security features in Yammer](/office365/servicedescriptions/yammer-service-description/administration-and-security-features-in-yammer).

- [Yammer admin help](/yammer/yammer-landing-page)

## More information

You can consolidate multiple Yammer networks, when the domains are verified in the same tenant. For more information, see [Network migration - Consolidate multiple Yammer networks](../configure-your-yammer-network/consolidate-multiple-yammer-networks.md).

---
title: "Set up the Standard or Targeted release options in Office 365"
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_FirstRelease'
- 'O365M_FirstRelease'
- 'O365E_FirstRelease'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: "Learn how to set up the release option for new product and features updates in the Microsoft 365 admin center."
---

# Set up the Standard or Targeted release options in Office 365

With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.
  
> [!IMPORTANT]
> The Office 365 updates described in this article apply to Office 365 Suites, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates. 
  
## How it works - release validation

Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft. After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in. At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics. This series of progressive validation is in place to make sure the worldwide-release is as robust as possible. The releases are pictured in the following figure. 
  
![Release validation rings for Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap). As an update gets closer to rolling out, it is communicated through your [Office 365 Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).

> [!NOTE]
> You need an Office 365 or Azure AD account to access your Message Center through the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center). Office 365 home plan users do not have an admin center.


## Standard release

This is the default option where you and your users receive the latest updates when they're released broadly to all Office 365 customers.
  
A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives. 
  
> [!NOTE]
> If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet. 
  
## Targeted release

With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.
  
> [!IMPORTANT]
> Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release. 
  
### Targeted release for entire organization

If you [Set up the release option in the Microsoft 365 admin center](#set-up-the-release-option-in-the-microsoft-365-admin-center) for this option, all your users will get the Targeted release experience. For organizations with more than 300 users, we recommend using a test subscription for this option. For test subscription information, please reach out to your Microsoft contact. 
  
### Targeted release for selected users

If you [Set up the release option in the Microsoft 365 admin center](#set-up-the-release-option-in-the-microsoft-365-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality. 
  
## Benefits of Targeted release

Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:
  
- Test and validate new updates before they are released to all the users in the organization.
    
- Prepare user notification and documentation before updates are released worldwide.
    
- Prepare internal help-desk for upcoming changes.
    
- Go through compliance and security reviews.
    
- Use feature controls, where applicable, to control the release of updates to end users.
    
## Set up the release option in the Microsoft 365 admin center

You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.
  
> [!IMPORTANT]
> It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet. 
  
1. Sign in to Office 365 with your work or school account. 
    
2. Go to the [Microsoft 365 admin center](../admin-overview/about-the-admin-center.md).
    
3. Navigate to **Settings** \> **Organization profile**.<br/>![Navigate to Settings and then Organization profile](../media/74ed60b3-c8b9-4752-a598-52d72cf46f46.png)
  
4. Next to **Release preferences**, click **Edit**.
    
5. To disable targeted release, choose **Standard release**, then click **Next**, and say **Yes** to the confirmation. Skip to the last step. 
    
6. To enable targeted release for all users in your organization, choose **Targeted release for everyone**, then click **Next**, and say **Yes** to the confirmation. Skip to the last step. 
    
7. To enable targeted release for some people in your organization, choose **Targeted release for selected users**, then click **Next**, and say **Yes** to the confirmation. 
    
8. Choose **Add people** to add users individually. Search for their names and click **+** to **Add**.
    
9. When you're done adding users, click **Save** and then **Close**.

## To add users in bulk
  
1. Next to Release preferences, click **Actions** \> **+ Bulk add people for first release** under the **Standard release** heading. 
    
2. Choose **Browse** to select a file containing each person's email address. 
    
3. Click **Next** and then **Close**.

## Get the Targeted release version of Office

To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.
  
## Learn more

Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.

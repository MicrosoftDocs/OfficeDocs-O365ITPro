---
title: "Cancel your subscription"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_CancelSubscription'
- 'O365E_CancelSubscription'
- 'O365P_EarlyTermFee'
- 'O365M_EarlyTermFee'
- 'O365E_EarlyTermFee'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: b1bc0bef-4608-4601-813a-cdd9f746709a
description: "Learn how you cancel your Office 365 for business or Microsoft 365 trial or paid subscription by using the Microsoft 365 admin center, or calling the Support."
---

# Cancel your subscription

You can cancel your trial or paid subscription online in the admin center at any time, if you have fewer than 25 licenses assigned to users. Any prorated credit will be returned to you within the next billing cycle.
  
In some cases, you might have to [call support to cancel your subscription](../contact-support-for-business-products.md):
  
- If you have more than 25 licenses assigned to users.

- For any other subscriptions (like Microsoft Dynamics 365 or Microsoft Intune, or if the **Cancel subscription** option is unavailable). 
  
## Before you begin: Change custom domain settings

If you use a custom domain with your subscription, there are a few extra steps that you need to do before you can cancel your subscription. If you don't have a custom domain, you can skip ahead to [Step 1: Save your data](#step-1-save-your-data).
  
### Change your domain's NS records (if needed)

If you set up a custom domain, you added DNS records so the domain would work with Office 365 services. Before you remove your domain, be sure to update the DNS records, such as your domain's MX record, at your DNS host.
  
For example, change the MX record at your DNS host so email sent to your domain stops coming to your Office 365 address and goes to your new email provider instead. (An MX record determines where email for your domain is sent.)
  
- If your nameserver (NS) records [are pointing to Office 365 nameservers](../setup/add-domain.md), changing your MX record won't take effect until you change your NS records to point to your new DNS host (see Step 2).

- Before you update the MX record, let your users know the date you'll be switching their email, and the new email provider you'll be using. Also, they'll need to take extra steps if they want to move their existing Office 365 email to the new provider.

- On the day you change the MX record, follow the rest of the steps in this article.

### Update your domain's MX and other DNS records (if you're using a custom domain)

If you switched your nameserver (NS) records to Office 365 when you set up your domain, you must set up or update your MX record and other DNS records at the DNS host you're going to use, and then change your NS record to that DNS host.
  
If you didn't switch NS records when you set up your domain, when you change the MX record, your mail will start going to the new address right away.
  
For more information, see [How does Office 365 manage my DNS records?](../setup/domains-faq.md#how-does-office-365-manage-my-dns-records). To change your NS records, see [Remove a domain from Office 365](../get-help-with-domains/remove-a-domain.md).
  
## Step 1: Save your data

Your users lose access to their data when the cancellation becomes effective, so have your users save their OneDrive for Business or SharePoint Online files to another location before you cancel the subscription. Any customer data that you leave behind may be deleted after 90 days, and will be deleted no later than 180 days after cancellation.
  
- To move email, contacts, tasks, and calendar information to another account, see [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx).

- To save a document library or list content (such as contacts) from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Manual migration of SharePoint Online content](http://support.microsoft.com/kb/2783484).

## Step 2: Cancel your subscription

If you added your own domain name to use with your subscription, you must remove the domain before you cancel your subscription. For more information, see [Remove a domain from Office 365](../get-help-with-domains/remove-a-domain.md).

::: moniker range="o365-worldwide"

### Use the admin center (preview) to cancel your subscription

The preview is available to all Microsoft 365 admins, you can opt in by selecting **Try the preview** toggle located at the top of the Home page. For more information, see [About Microsoft 365 admin center preview](../microsoft-365-admin-center-preview.md).

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.

2. Find the subscription that you want to cancel, under **Settings & Actions**, choose **Cancel subscription**.

3. Review the important dates, provide feedback about why you are cancelling, then choose **Cancel subscription**.

    Your subscription will now appear in a **Disabled** state, and will have reduced functionality until it is deleted. For more information about what you can expect when a paid Office 365 for business subscription is cancelled, see [What happens to my data and access when my Office 365 for business subscription ends?](what-if-my-subscription-expires.md)

::: moniker-end

::: moniker range="o365-worldwide"
### Use the old admin center to cancel your subscription
::: moniker-end
  
1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Subscriptions</a> page.

    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.

    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.

2. On the **Subscriptions** page, choose a subscription.

3. From the **More actions** menu, choose **Cancel subscription**.

    ![Close up of the More Actions menu.](../media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)
  
4. Review the important dates, provide feedback about why you are cancelling, then choose **Cancel subscription**.

    Your subscription will now appear in a **Disabled** state, and will have reduced functionality until it is deleted. For more information about what you can expect when a paid Office 365 for business subscription is cancelled, see [What happens to my data and access when my Office 365 for business subscription ends?](what-if-my-subscription-expires.md)

## Step 3: Uninstall Office (optional)

If you cancelled your subscription, and didn't move users to a different subscription that includes Office, Office 365 will run in reduced functionality mode. When this happens, users can only read and print documents, and Office 365 applications will show [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). To avoid any confusion, have your users [uninstall Office](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx) from their machines.
  
## Related topics

[Renew your subscription](renew-your-subscription.md)
  
[Reactivate your subscription](reactivate-your-subscription.md)
  
[Switch to a different plan or subscription](switch-to-a-different-plan.md)
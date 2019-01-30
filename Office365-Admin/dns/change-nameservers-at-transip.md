---
title: "Change nameservers to set up Office 365 with TransIP"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_TransIP1'
- 'O365M_DOM_TransIP1'
- 'O365E_DOM_TransIP1'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5d4ee399-0ad6-43c5-b977-4cba390b3f64
description: "Learn to set up your Office 365 custom domain with TransIP if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with TransIP

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at TransIP](create-dns-records-at-transip.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domain-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. 3.In the DNS section, in the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the TTL and Type values from the drop-down lists.)
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**Value** <br/> |
|@  <br/> |1 Hour  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Choose **Save**.
    
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain.*  com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. When you have completed the steps in this section, the only nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.
  
1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domain-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. In the **Nameservers** section, delete each of the currently listed nameservers listed by selecting it and then pressing the **Delete** key on your keyboard. 
    
    (You may have to scroll down.)
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (That is, delete only any current nameservers that are not named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
    ![TransIP-BP-Redelegate-1-1](../media/2d005ad7-4c5f-4c91-9ff1-a5eaed94193d.png)
  
4. In the **Primary nameserver** and **Secondary nameserver** boxes, type or copy and paste the values from the following table. 
    
|
|:-----|:-----|
|**Primary nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondary nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Tertiary nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![TransIP-BP-Redelegate-1-2](../media/bca6e3e0-b7ed-40e7-9cba-4afd4322c365.png)
  
5. Choose **Save**.
    
    ![TransIP-BP-Redelegate-1-3](../media/e6b0f86f-9e24-4f91-8e50-b2d8d82b3a57.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

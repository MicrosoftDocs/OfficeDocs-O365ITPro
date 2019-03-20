---
title: "Change nameservers to set up Office 365 with Dreamhost"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
ms.custom:
- Adm_O365
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e170116-e550-430b-aba9-c317de2d35ed
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Dreamhost."
---

# Change nameservers to set up Office 365 with Dreamhost

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Dreamhost](create-dns-records-at-dreamhost.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to sign in.
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. On the **Dashboard** page, choose **Domains**, and then choose **Manage Domains**.
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. On the **Manage Domains** page, in the **Domain** section, choose **DNS** for the domain that you want to edit. 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Select the **Type** value from the drop-down list.) 
    
|**Name**|**Type**|**Value**|**Comment**|
|:-----|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/>   |(This field is optional.)  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. Choose **Add Record Now!**
    
    ![Dreamhost-BP-Verify-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. On the **Dashboard** page, choose **Domains**, and then choose **Manage Domains**.
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. On the **Manage Domains** page, in the **Domain** section, choose **DNS** for the domain that you want to edit. 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
In the following two steps, you will first remove all of the nameservers that are currently listed and then add the two nameservers that you need for Office 365.
  
1. In the **Change  *domain_name's*  whois nameservers ** section, delete each nameserver entry by selecting the entry and then pressing the **Delete** key on your keyboard. 
    
    > [!IMPORTANT]
    > Be sure to use the **Delete** key on your keyboard for this action, and not the **Delete** control on the screen, which has a different effect. 
  
    ![Dreamhost-BP-Redelegate-1-1](../media/ef683dd6-ae4c-4e61-89d9-953a4cd4e714.png)
  
2. Type or copy and paste the values from the following table in the **Nameserver 1** to **Nameserver 4** boxes. 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 2 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Dreamhost-BP-Redelegate-1-2](../media/10f6a2f4-63d4-49a8-b239-de7571f1b285.png)
  
3. Choose **Set the nameservers for  *domain_name*  ! **
    
    ![Dreamhost-BP-Redelegate-1-3](../media/691ec788-2d38-4809-a281-19dd3a491d1a.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


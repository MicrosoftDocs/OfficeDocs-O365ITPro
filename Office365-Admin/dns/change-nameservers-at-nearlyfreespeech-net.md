---
title: "Change nameservers to set up Office 365 with NearlyFreeSpeech.net"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 4a004de9-82fd-4275-9eae-395311df2bbf
description: "Learn to set up your Office 365 custom domain with NearlyFreeSpeech.net if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with NearlyFreeSpeech.net

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at NearlyFreeSpeech.net](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/login/domains?). You'll be prompted to log in first
    
2. In the **Domains** section, find the name of the domain that you want to edit and then, in the **DNS** column for that domain, choose **Manage**.
    
3. On the **DNS** page, in the **Actions** area, choose **Add a DNS Resource Record**.
    
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|Name  <br/> |Type  <br/> |Data  <br/> |TTL  <br/> |
|(Leave this field empty  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/>           |3600  <br/> |
   
5. Choose **Add record**.
    
6. Choose **Click here to continue...** to return to the **DNS** page. 
    
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Microsoft 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: 
  
1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/login/domains?). You'll be prompted to log in first
    
2. In the **Domains** section, find the name of the domain that you want to edit and then, in the **Registrar** column for that domain, choose **Manage**.
    
    ![NearlyFreeSpeech-BP-Redelegate-1-1](../media/9bef75c8-a2c4-4a81-9653-cce112b46fc9.png)
  
3. On the **Registration Details** page, in the **Actions** area, choose **Edit Name Servers**.
    
    ![NearlyFreeSpeech-BP-Redelegate-1-2](../media/882b75bf-92f2-4b1c-9c52-a73c45f07b10.png)
  
4. Select **I want to specify my own name servers**.
    
    ![NearlyFreeSpeech-BP-Redelegate-1-3-1](../media/8a4f4040-d5e4-40fa-9992-2f45b2fe17e3.png)
  
5. Then choose **Continue**.
    
    ![NearlyFreeSpeech-BP-Redelegate-1-3-2](../media/137c2d28-da33-4f63-a917-cc30e6cc0b62.png)
  
    > [!NOTE]
    > In the following two steps, you will first remove all of the nameservers that are currently listed, and then add the two nameservers that you need for Office 365. 
  
6. In the **Enter Your Name Servers** section, delete each nameserver entry by selecting that entry and then pressing the **Delete** key on your keyboard. 
    
    ![NearlyFreeSpeech-BP-Redelegate-1-4](../media/9cc2d8be-7da1-4d82-91c1-9b5f59aa589a.png)
  
7. When you have deleted all existing nameserver entries, type or copy and paste the values from the following table in the boxes labeled **1**, **2**, **3**, and **4**.
    
|||
|:-----|:-----|
|**1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![NearlyFreeSpeech-BP-Redelegate-1-5](../media/213e0450-65b5-4e41-aeae-841dce754136.png)
  
8. Choose **Continue**.
    
    ![NearlyFreeSpeech-BP-Redelegate-1-6](../media/de74ee3d-c2c7-41cb-bedb-d0526fba0b03.png)
  
9. Choose **Click here to continue** to return to the **DNS** page.
    
    ![NearlyFreeSpeech-BP-Redelegate-1-7](../media/e0ff26ae-65a8-4eff-aa1f-9a0d27176e7f.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
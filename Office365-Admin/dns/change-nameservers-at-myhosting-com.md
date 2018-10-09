---
title: "Change nameservers to set up Office 365 with myhosting.com"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 7/5/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_myh1'
- 'O365M_DOM_myh1'
- 'O365E_DOM_myh1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7edf96e3-2c02-4df5-94df-7bf398769280

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at myhosting.com."
---

# Change nameservers to set up Office 365 with myhosting.com

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyHosting](create-dns-records-at-myhosting-com.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-myhosting-com.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-myhosting-com.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-myhosting-com.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/single.mdl). You'll be prompted to log in first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
4. Choose the **DNS** tab, and then choose **DNS Records**.
    
5. Choose **Add New DNS Record**.
    
6. 6.In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the DNS Record Type value from the drop-down list.)
    
|||||
|:-----|:-----|:-----|:-----|
|**DNS Record Type** <br/> |**Domain** <br/> |**Data** <br/> |**TTL** <br/> |
|TXT  <br/> |(Leave this field empty)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Enter the value **3600**.  <br/> |
   
7. Choose **Finish**.
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: 
  
1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/single.mdl). You'll be prompted to log in first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, locate the domain that you want to edit, and then choose its ** *domain_name* **. 
    
    ![MyHosting-BP-Redelegate-1-1](../media/6d5037a4-0d08-41d8-b73b-51babe2b8f34.png)
  
4. In the **Name Servers** section, choose **Manage Nameservers**.
    
    ![MyHosting-BP-Redelegate-1-2](../media/8d6a4812-56b9-46eb-8eed-fcf904b242e2.png)
  
5. In the **Domain Name Servers** section, delete each nameserver by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![MyHosting-BP-Redelegate-1-3](../media/37d3de2e-0a58-470e-97bd-49e589adfeb4.png)
  
6. Still in the **Domain Name Servers** section, in the **Primary Name Server** through **Fourth Name Server** boxes, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**Primary Name Server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondary Name Server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third Name Server** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth Name Server** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![MyHosting-BP-Redelegate-1-4](../media/61452a33-ba4b-49b6-acde-260b2c928d8f.png)
  
7. Choose **Update Name Server**.
    
    ![MyHosting-BP-Redelegate-1-5](../media/d574a517-b7df-440e-a3ea-0fe173618183.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


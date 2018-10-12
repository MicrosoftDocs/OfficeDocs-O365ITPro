---
title: "Change nameservers to set up Office 365 with 123-reg.co.uk"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_123RegCoUK1'
- 'O365M_DOM_123RegCoUK1'
- 'O365E_DOM_123RegCoUK1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8d7237cc-be6b-4cc3-be67-e96d8eb232d1
description: "Learn how you can set up Office 365 to manage your DNS records at 123-reg.co.uk. "
---

# Change nameservers to set up Office 365 with 123-reg.co.uk

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at 123-reg.co.uk](create-dns-records-at-123-reg-co-uk.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-123-reg-co-uk.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-123-reg-co-uk.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-123-reg-co-uk.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.
    
2. On the **Domain name overview** page, under **DOMAIN NAME**, select the name of the domain that you want to edit.
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. On the **Manage your DNS** page, choose the **Advanced DNS** tab. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
||||
|:-----|:-----|:-----|
|**Hostname** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
|@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Choose **Add**.
    
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
>  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.
    
2. On the **Domain name overview** page, under ** DOMAIN NAME **, select the name of the domain that you want to edit.
    
3. On the **Manage domain** page for your domain, in the **Advanced domain settings** section, choose **Change Nameservers (DNS)**.
    
    ![123Reg-BP-Redelegate-1-1](../media/a9f9eb81-6387-4e26-986e-3cc2e4a9e89d.png)
  
4. On the **Nameserver management** page, in the **Nameserver** boxes, delete each of the default nameservers by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![123Reg-BP-Redelegate-1-2](../media/1bccdbcd-4b0d-4d1a-b57f-6e802cd1b069.png)
  
5. In the **Nameserver** boxes that are labeled as **Required**, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![123Reg-BP-Redelegate-1-3](../media/48954f63-b125-432a-a1a6-f51b0e70d66b.png)
  
6. Choose **Update**.
    
    ![123Reg-BP-Redelegate-1-4](../media/7c086547-369a-4f96-b629-c0d6a660b448.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 

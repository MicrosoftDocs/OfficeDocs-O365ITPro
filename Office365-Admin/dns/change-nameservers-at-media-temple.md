---
title: "Change nameservers to set up Office 365 with Media Temple"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f2f38ba0-b6da-4194-ad97-69f92e267dd3
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Media Temple."
---

# Change nameservers to set up Office 365 with Media Temple

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can manage all your Office 365 DNS records at Media Temple.).
  
Here's what you need to do. ([Still need help?](change-nameservers-at-media-temple.md#BKMK_NeedHelp))
  
- [Lower the TTL value](change-nameservers-at-media-temple.md#BKMK_TTL)
    
- [Add a TXT record for verification](change-nameservers-at-media-temple.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-media-temple.md#BKMK_Nameserver)
    
## Lower the TTL value

By default, Media Temple uses a TTL of 43200 seconds (12 hours). To speed up the Office 365 verification process, we recommend setting the TTL to 3600 (1 hour). Since Media Temple does not support arbitrary TTL values, use the following procedure to lower the TTL during the interval required to verify your Office 365 DNS records. You only need to do this once, at the start of the verification process.
  
1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Additional Zone Actions** section, choose **Lower TTL**.
    
    (You may have to scroll down.)
    
    ![MediaTemple-BP-Configure-1-6](../media/8cbaf91f-f77a-4088-b241-b67685b17c9a.png)
  
6. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-7](../media/4a09010b-4ea4-4170-aa20-69572304d25f.png)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the ** Control Panel ** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the ** Zone Records ** section, choose **+ Add Row**. 
    
6. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Select the Type value from the drop-down list.)
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**Data** <br/> |
|(Leave this field empty.)  <br/> |(This value cannot be changed.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Choose **Save Changes**.
    
8. Choose **OK**.
    
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. When you have completed the steps in this section, the only nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.
  
1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit.
    
4. On the **Control Panel** page for your domain, in the **Domain Tools** section, choose **Edit Nameservers**.
    
    ![MediaTemple-BP-Redelegate-1-1](../media/e6bb3585-8738-4bc3-93e7-a5c2fcfd7424.png)
  
5.  > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)
  
    Delete each of the nameservers currently listed by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![MediaTemple-BP-Redelegate-1-2-1](../media/5ca19988-5878-46b9-865c-e09644624b22.png)
  
6. Choose **Add another nameserver**.
    
    ![MediaTemple-BP-Redelegate-1-2-2](../media/e16a9c39-35bf-4d44-8871-a62726db740c.png)
  
7. In the **Name server details** section, in the boxes for the new records, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Additional nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Additional nameserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MediaTemple-BP-Redelegate-1-3](../media/92a049ee-aecd-407e-acea-2e2e8434a967.png)   
    
8. Choose **Save**.
    
    (You may need to scroll down.)
    
    ![MediaTemple-BP-Redelegate-1-4](../media/c4cf21af-98d3-46e5-987b-0df24081490c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
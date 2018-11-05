---
title: "Change nameservers to set up Office 365 with Netfirms"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Netf1'
- 'O365M_DOM_Netf1'
- 'O365E_DOM_Netf1'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: d527984f-dd46-43ef-996f-5492be04591e
description: "Learn to set up your Office 365 custom domain with Netfirms if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Netfirms

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Netfirms](create-dns-records-at-netfirms.md).)
  
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Netfirms by using [this link](https://www2.netfirms.com/controlpanel/domaincentral). You'll be prompted to log in first.
    
2. In the **My Favorites** section, choose **Domain Central**.
    
3. In the **Domain** column, choose the name of the domain that you want to edit. 
    
4. In the **Overview** row, choose **DNS**.
    
5. In the **Modify** drop-down list, choose **TXT/SPF Record**.
    
6. Under **Content**, in the box for the new record, type or copy and paste the value from the following table.
    
||
|:-----|
|**Content** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/> |
||
   
7. Choose **Add**.
    
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
  
1. To get started, go to your domains page at Netfirms by using [this link](https://www2.netfirms.com/controlpanel/domaincentral). You'll be prompted to log in first.
    
2. In the **My Favorites** section, choose **Domain Central**.
    
3. In the **Domain** column, choose the name of the domain that you want to edit. 
    
4. In the **Overview** row, choose **Nameservers**.
    
    ![Netfirms-BP-Redelegate-1-1](../media/9599c296-9712-4ec8-87d4-fc1a076f5f7d.png)
  
5. In the **Update Name Servers** section, select **Use different name servers**.
    
    ![Netfirms-BP-Redelegate-1-2-1](../media/94de7177-f059-4e89-9552-2fee901595bf.png)
  
6. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.
    
### If the correct nameservers ARE already listed

- If the correct nameservers are already listed, you can skip this step.
    
    ![Netfirms-BP-Redelegate-1-2-2](../media/92583632-3ef5-4350-be6d-d9a32f2c29c1.png)
  
### If the correct nameservers are NOT already listed

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. Delete the existing nameservers by selecting the entries and then pressing the **Delete** key on your keyboard. 
    
    ![Netfirms-BP-Redelegate-1-3](../media/76d289cf-16d1-48d9-a7f3-ca46c746185b.png)
  
2. Choose **Add More** twice to add two new Nameserver rows. 
    
    ![Netfirms-BP-Redelegate-1-3-2](../media/edf0acab-8553-4a56-b5c6-b085c1c9775b.png)
  
3. In the boxes for the records, type or copy and paste the nameserver values from the following table.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Netfirms-BP-Redelegate-1-4](../media/e9ff6407-3395-47d9-a7e7-325b78b53d3b.png)
  
4. Choose **Save**.
    
    ![Netfirms-BP-Redelegate-1-5](../media/6c40b569-a0cc-4a5e-8851-0d4b3b4eac70.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
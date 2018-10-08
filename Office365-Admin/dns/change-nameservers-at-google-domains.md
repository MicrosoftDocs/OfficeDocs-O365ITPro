---
title: "Change nameservers to set up Office 365 with Google Domains"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 5/2/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_GoogleDomains1'
- 'O365M_DOM_GoogleDomains1'
- 'O365E_DOM_GoogleDomains1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Google Domains."
---

# Change nameservers to set up Office 365 with Google Domains

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-google-domains.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-google-domains.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-google-domains.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
>  This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Google Domains by using this link. You'll be prompted to sign in. To do so:
    
1. Choose **Sign In**.
    
2. Enter your login credentials, and then again choose **Sign In**.
    
2. On the **Domains** page, in the **Domain** section, choose **Configure DNS** for the domain that you want to edit. 
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Choose **Add**.
    
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
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain.*  com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: 
  
1. To get started, go to your domains page at Google Domains by using this link. You'll be prompted to sign in. To do so:
    
1. Choose **Sign In**.
    
2. Enter your login credentials, and then again choose **Sign In**.
    
2. On the **Domains** page, in the **Domain** section, choose **Configure DNS** for the domain that you want to edit. 
    
3. On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.
    
    ![Google-Domains-BP-Redelegate-1-1](../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](change-nameservers-at-google-domains.md#BKMK_ProcedureWithOUT).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](change-nameservers-at-google-domains.md#BKMK_ProcedureWITH).
    
### If there are NO nameservers already listed
<a name="BKMK_ProcedureWithOUT"> </a>

1. Add the first nameserver.
    
    In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table. 
    
|||
|:-----|:-----|
|**First name server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second name server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third name server** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth name server** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Google-Domains-BP-Redelegate-1-2](../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Choose the **+ (add)** control to create an empty row. 
    
    ![Google-Domains-BP-Redelegate-1-3](../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. Add the other three Nameserver records.
    
    In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then choose the **+ (add)** control to add another row. 
    
    Repeat this process until you have created all four Nameserver records.
    
4. Choose **Save**.
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed
<a name="BKMK_ProcedureWITH"> </a>

1. If there are any other nameservers listed, choose **Edit**.
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. Delete each one by selecting it, and then pressing the **Delete** key on your keyboard. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**First name server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second name server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third name server** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth name server** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Google-Domains-BP-Redelegate-1-7](../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Choose the **+(add)** control to create an empty row. 
    
    ![Google-Domains-BP-Redelegate-1-8](../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Add the other two Nameserver records.
    
    In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then choose the **+(add)** control to add another row. 
    
    Repeat this process until you have created all four Nameserver records.
    
6. Choose **Save**.
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
## Still need help?
<a name="BKMK_NeedHelp"> </a>

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


---
title: "Change nameservers to set up Office 365 with Names.co.uk"
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
ms.assetid: 8646cd83-e3ca-4517-bd40-2cce164c580c
description: "Learn to set up your Office 365 custom domain with Names.co.uk if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Names.co.uk

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Names.co.uk](create-dns-records-at-names-co-uk.md).)
  

    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-Configure-1-2](../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    (If you need to add a row, choose ** ADD A/CNAME RECORDS (+) **.)
    
    (You may have to scroll down.)
    
|**Host name**|**Type**|**Result**|
|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.    [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/>       |


   ![NamesUK-BP-Verify-1-1](../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. Choose **Save**.
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-Verify-1-2](../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
1. To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **Manage Domain** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-Redelegate-1-1](../media/26bbd964-7d4f-46c9-96ae-fe67e8dd1cd8.png)
  
3. On the **Summary Info** page, under **Domain Names**, choose **DNS &amp; Transfer Options**.
    
    ![NamesUK-BP-Redelegate-1-3-1](../media/daaa5f9f-5c52-45e8-a00f-148c40ef250b.png)
  
4. Under **DNS &amp; Transfer Options**, choose **Change Nameservers**.
    
    ![NamesUK-BP-Redelegate-1-3-2](../media/b54cba6d-3724-436d-9ce0-3f1eca6b2ece.png)
  
5. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).
    
### If there are NO nameservers already listed

1. In the boxes in the **New nameservers** area, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**First nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth nameserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![NamesUK-BP-Redelegate-1-4](../media/c7b31801-5f52-4348-b953-3abddc51bb4a.png)
  
2. Choose **UPDATE**.
    
    ![NamesUK-BP-Redelegate-1-5](../media/be465928-aa6e-4e9d-88fe-fac0f4c029b5.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. If there are any other name servers listed in the **New nameservers** area, delete each of them by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![NamesUK-BP-Redelegate-1-6](../media/67ffb25b-dc4d-43da-9e61-b3bbddb3de49.png)
  
2. Still in the **New nameservers** area, type or copy and paste the values from the following table into the first two boxes. 
    
|||
|:-----|:-----|
|**First nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth nameserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![NamesUK-BP-Redelegate-1-4](../media/c7b31801-5f52-4348-b953-3abddc51bb4a.png)
  
3. Choose **UPDATE**.
    
    ![NamesUK-BP-Redelegate-1-5](../media/be465928-aa6e-4e9d-88fe-fac0f4c029b5.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
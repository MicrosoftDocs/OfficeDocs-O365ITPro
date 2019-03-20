---
title: "Change nameservers to set up Office 365 with United Domains"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_UD1'
- 'O365M_DOM_UD1'
- 'O365E_DOM_UD1'
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
ms.assetid: 513cd5bc-46ad-48e8-bb11-af90b455d474
description: "Learn to set up your Office 365 custom domain with United Domains if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with United Domains

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at United Domains](create-dns-records-at-united-domains.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit.
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. In the **DNS Records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may need to scroll down.)
    
    (Select the **Record Type** value from the drop-down list.) 
    
|**Subdomain**|**Record Type**|**Value**|
|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |TXT Record  <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          <br/>

   ![UnitedDomains-BP-Verify-1-1](../media/b596efe5-3a06-4104-ac26-8e470d69c2db.png)
  
4. Choose the **Save** control that is indicated in the following illustration. 
    
    ![UnitedDomains-BP-Verify-1-2](../media/b47b6111-387a-4cf0-9eec-f16d50b91c03.png)
  
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
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**. The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.
  
1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit. 
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. On the **Manage DNS / NS for** page, in the **Set Nameservers / Parking** section, select **Use other nameservers**.
    
    ![UnitedDomains-BP-Redelegate-1-1](../media/4ad20ff5-21e3-4659-80c8-160cd4e56eba.png)
  
4. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).
    
### If there are NO nameservers already listed

1. In the **Use other nameservers** section, type or copy and paste the nameserver values from the following table. 
    
|||
|:-----|:-----|
|First **NS** field  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second **NS** field  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third **NS** field  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth **NS** field  <br/> |ns4.bdm.microsoftonline.com  <br/> |

   ![UnitedDomains-BP-Redelegate-1-2](../media/996bca3d-36fa-4eee-9ccf-b0198ee2675b.png)

2. Choose **Save.**
    
    ![UnitedDomains-BP-Redelegate-1-3](../media/3dcda956-ee1f-419f-9358-e7b6801ac90e.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![UnitedDomains-BP-Redelegate-1-4](../media/377801c8-f742-41f8-a822-3f6b81685353.png)
  
2. Still on the **Edit Nameserver** page, in the first and second **NS** fields, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|First **NS** field  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second **NS** field  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third **NS** field  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth **NS** field  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![UnitedDomains-BP-Redelegate-1-2](../media/996bca3d-36fa-4eee-9ccf-b0198ee2675b.png)
  
3. Choose **Save.**
    
    ![UnitedDomains-BP-Redelegate-1-3](../media/3dcda956-ee1f-419f-9358-e7b6801ac90e.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

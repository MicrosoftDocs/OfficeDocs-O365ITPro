---
title: "Change nameservers to set up Office 365 with Network Information Center (NIC)"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_NIC1'
- 'O365M_DOM_NIC1'
- 'O365E_DOM_NIC1'
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
ms.assetid: a8007416-0da5-4df5-b85f-105f8368e6b4
description: "Learn to set up your Office 365 custom domain with Network Information Center (NIC) if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Network Information Center (NIC)

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Network Information Center (NIC)](create-dns-records-at-nic.md).)
  
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.
  
1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose **Manage DNS** for the domain that you want to edit. 
    
4. On the **DNS Management** page, in the **Records** section, choose **Add**.
    
    (You may have to scroll down.)
    
5. Choose **TXT** from the **Type** drop-down list. 
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the TTL value from the drop-down list.)
    
|||||
|:-----|:-----|:-----|:-----|
|**TYPE** <br/> |**HOST** <br/> |**TXT VALUE** <br/> |**TTL** <br/> |
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1 Hour  <br/> |
   
7. Choose **Save**.
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.
  
1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose ** Manage DNS ** for the domain that you want to edit. 
    
4. On the **DNS Management** page, scroll to the **Nameservers** section, and then choose **Change**.
    
    ![NIC-BP-Redelegate-1-1](../media/42e32425-1b43-4308-82d4-c2067122ab04.png)
  
5. In the **Nameserver** section, select **Custom** from the **Choose your new nameserver type** drop-down list. 
    
    ![NIC-BP-Redelegate-1-2-1](../media/6229708f-41dc-47c2-85c9-10f4fe11d0e2.png)
  
6. Depending on whether or not there are already nameservers listed, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).
    
### If there are NO nameservers already listed

1. Choose **Add Nameserver** twice to add two new Nameserver rows. 
    
    ![NIC-BP-Redelegate-1-2-2](../media/40cdb38e-7149-4325-9572-c9fb8a9f3776.png)
  
2. In the **Nameserver** section, type or copy and paste the nameserver values from the following table. 
    
|||
|:-----|:-----|
|First **Nameserver** field  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second **Nameserver** field  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third **Nameserver** field  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth **Nameserver** field  <br/> |ns4.bdm.microsoftonline.com  <br/> |
        
![NIC-BP-Redelegate-1-3](../media/1b1455ba-7614-49b1-9a7e-be8560b77325.png)
  
3. Choose **Save**.
    
    ![NIC-BP-Redelegate-1-4](../media/3dafd84a-34f6-4c46-986d-0d8f7cf18774.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)
  
1. If there are any other nameservers listed, delete each of the other nameservers by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![NIC-BP-Redelegate-1-5](../media/83285a3d-3d4b-4573-bac9-816a9b9ea4cf.png)
  
2. Choose **Add Nameserver** twice to add two new Nameserver rows. 
    
    ![NIC-BP-Redelegate-1-2-2](../media/40cdb38e-7149-4325-9572-c9fb8a9f3776.png)
  
3. Still in the **Nameserver** section, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|First **Nameserver** field  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second **Nameserver** field  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third **Nameserver** field  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth **Nameserver** field  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![NIC-BP-Redelegate-1-3](../media/1b1455ba-7614-49b1-9a7e-be8560b77325.png)
  
4. Choose **Save**.
    
    ![NIC-BP-Redelegate-1-4](../media/3dafd84a-34f6-4c46-986d-0d8f7cf18774.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
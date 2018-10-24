---
title: "Change nameservers to set up Office 365 with Freenom"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 03599896-4b0a-4edb-abfb-ca3f16325d84

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Freenom."
---

# Change nameservers to set up Office 365 with Freenom

[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
> [!CAUTION]
> The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider. 
  
To learn about webhosting and DNS for websites with Office 365, see﻿ [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Freenom by using this link. You'll be prompted to log in.
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Choose **Services**, and then choose **My Domains**. 
    
    ![Freenom select Services and My Domains](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. For the domain that you want to edit, choose **Manage Domain**. 
    
    ![Freenom select Manage Domain](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Choose **Manage Freenom DNS**. 
    
    ![Freenom Manage Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Under **Add Record**, in the **Type** column, choose **TXT** from the menu. 
    
    ![Freenom Add Record type TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
|**Name**|**Type**|**TTL**|**Target**|
|:-----|:-----|:-----|:-----|
|(leave blank)  <br/> |TXT  <br/> |3600 (seconds)  <br/> |MS=msXXXXXXXX  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/>   |
   
   ![Freenom TXT values for verification](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Choose **Save Changes**. 
    
    ![Freenom TXT record Save Changes](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
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
  
1. To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Freenom login](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Go to **My Domains**
    
3. Click on **Manage Domain**
    
4. Click on **Management Tools**
    
5. Click on **Nameservers**
    
6. Enter these values in the nameserver fields
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
7. Press **Change Nameservers**
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


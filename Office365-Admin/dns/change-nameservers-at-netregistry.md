---
title: "Change nameservers to set up Office 365 with Netregistry"
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
ms.assetid: 97e9642f-48a6-4b73-8ddd-6160a300955e
description: "Learn to set up your Office 365 custom domain with Netregistry if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Netregistry

[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.
  
If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you change your NS records at Netregistry, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Next to the domain you want to manage, select **Manage**.
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Select **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. Under **Add a zone record**, choose **TXT Record**from the list, and then select **Create new record**.
    
    ![Netregistry_TXT_select](../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
5.  **NOTE**: You must use quotation marks before and after the entry in the TXT box.
  
    In the **New TXT Record** form, type or copy and paste the values from the following table. 
    
|**Name**|**TTL (SEC)**|**TXT (Points to address or value)﻿**|
|:-----|:-----|:-----|
|(leave blank)  <br/> |3600 (seconds)  <br/> |"MS=msXXXXXXXX"  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
       
![Netregistry_verificationTXTvalues](../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Choose **Add record**.
    
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
  
## Change your nameservers

1. To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Next to the domain you want to manage, select **Manage**.
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. On the next page click **Domain Name**.
    
4. Scroll down to the **Domain Delegation** section.
    
5. Edit your nameservers to the addresses below and click on "**Update Name Servers**."
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
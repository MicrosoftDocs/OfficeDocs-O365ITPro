---
title: "Change nameservers to set up Office 365 with Strato"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8d1f0c62-5bec-44ac-8329-f985caefb367
description: "Learn to set up your Office 365 custom domain with Strato if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Strato

[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.
  
If Strato.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at Strato.com, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](../setup/domains-faq.md).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select **Domains**.
    
    ![Strato_domains](../media/ae990bf2-6f98-4dd6-9aef-f65d2888091a.png)
  
3. Select **Domain management**.
    
    ![strato_domainManagement](../media/eced1360-f207-4b5e-bd61-848a70dc44a9.png)
  
4. On the **Domain management** page, next to the domain you want to manage, select **manage**.
    
    ![strato_manage](../media/2d9bd3ae-e4bc-459b-8539-206768b60a9b.png)
  
5. Under **Settings (domain)**, expand **DNS Settings**.
    
    ![strato_DNSsettings](../media/fb83450b-f638-4cd6-a844-5eab442424ae.png)
  
6. Next to **TXT records, including SPF and DKIM settings**, select **manage**.
    
    ![strato_TXT_manage](../media/e0277f36-af91-45b9-8242-fcebbb5502c7.png)
  
7. In the boxes for the new record, type or copy and paste the following values.
    
|**Prefix**|**Type**|**Value**|
|:-----|:-----|:-----|
|(leave blank)  <br/> |TXT  <br/> |MS=msXXXXXXX  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
8. Select **Accept settings**.
    
    ![Strato_TXT_values_accept](../media/72828ff3-9a67-4de4-97fb-41b9eb43d909.png)
  
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
## Change your nameservers
<a name="bkmk_ns"> </a>

1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select the menu option **Manage domains**.
    
3. Expand **DNS Administration** and click **manage** in the NS Record column. 
    
4. Select **Personal name server**.
    
5. Edit your nameservers to the addresses below and click " **Accept Settings**."
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   


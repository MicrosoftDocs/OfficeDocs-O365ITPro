---
title: "Create DNS records at West263 for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
 - Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: bb6be17f-c497-4c72-9e0d-861b0dc83739
description: "Learn to setup your own DNS records at West263 for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at West263 for Office 365

> [!CAUTION]
> The WEST263 website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at WEST263, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.

    
After you add these records at WEST263, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/4fdcd8d5-2c99-47fe-a506-199899ae0369), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [your domains list at WEST263](http://west263.com/manager/domain) and sign in. 
    
    ![Sign in to WEST263](../media/c1042b3b-9560-4383-ba24-ae1f522b17c5.png)
  
2. In the right pane, in the **管理** ( management) column for the domain that you want to update, click **管理** ( management). 
    
    ![Click "管理"](../media/a1fc5365-da24-4d6f-b51b-706485e1a065.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/5263e2de-81f1-4cdf-805e-4e2d0ce62bae.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **解析类型** (type): **TXT记录**
    
  - **对应值** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **TTL**: **3600**
    
    ![Select "TXT记录"](../media/5e34c5cd-72d0-46dd-9c8c-05258d1108d0.png)
  
5. Click **确定添加** (add). 
    
    ![Add TXT record](../media/6d00a4e5-d332-4514-b7c1-1a0267c7516d.png)
  
6. In the confirmation dialog box, click **OK**.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
## Add an MX record to route email
<a name="BKMK_add_MX"> </a>

1. In your browser, go to the [your domains list at WEST263](http://west263.com/manager/domain) and sign in. 
    
    ![Sign in to WEST263](../media/c1042b3b-9560-4383-ba24-ae1f522b17c5.png)
  
2. In the right pane, in the **管理** ( management) column for the domain that you want to update, click **管理** ( management). 
    
    ![Click "管理"](../media/a1fc5365-da24-4d6f-b51b-706485e1a065.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/5263e2de-81f1-4cdf-805e-4e2d0ce62bae.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **解析类型** (type): **MX记录**
    
  - **对应值** (value): Paste the **Points to address** value value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **TTL**: **3600**
    
  - **优先级** (priority): **1**
    
    ![Select "MX记录"](../media/07067d99-c7b7-45b3-9a81-bd93832118dc.png)
  
5. Click **确定添加** (add). 
    
    ![Add MX record](../media/f4ec7f52-fe98-4f7b-8bef-4ca3f5defa8a.png)
  
6. In the confirmation dialog box, click **OK**.
    
7. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. On the row of the obsolete record, click **删除** (remove). 
    
    2. In the confirmation dialog box, click **OK**.
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to the [your domains list at WEST263](http://west263.com/manager/domain) and sign in. 
    
        ![Sign in to WEST263](../media/c1042b3b-9560-4383-ba24-ae1f522b17c5.png)
  
    2. In the right pane, in the **管理** ( management) column for the domain that you want to update, click **管理** ( management). 
    
        ![Click "管理"](../media/a1fc5365-da24-4d6f-b51b-706485e1a065.png)
  
    3. Click the **域名解析** (domain name resolution) tab. 
    
        The DNS records page for your domain opens.
    
        ![Click "域名解析"](../media/5263e2de-81f1-4cdf-805e-4e2d0ce62bae.png)
  
    4. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **autodiscover**
    
        - **解析类型** (type): **CNAME记录**
    
        - **对应值** (value): **autodiscover.partner.outlook.cn**
    
        - **TTL**: **3600**
    
        ![Select "CNAME记录"](../media/af227397-ae2d-4ab4-b9d2-a22240f0cccf.png)
  
    5. Click **确定添加** (add). 
    
        ![Add CNAME record](../media/3c4f1b68-fb2c-4ae8-89ab-5022a504ee7b.png)
  
    6. In the confirmation dialog box, click **OK**.
    
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **lyncdiscover**
    
        - **解析类型** (type): **CNAME记录**
    
        - **对应值** (value): **webdir.online.partner.lync.cn**
    
        - **TTL**: **3600**
    
    2. Click **确定添加** (add). 
    
    3. In the confirmation dialog box, click **OK**.
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **sip**
    
        - **解析类型** (type): **CNAME记录**
    
        - **对应值** (value): **sipdir.online.partner.lync.cn**
    
        - **TTL**: **3600**
    
    2. Click **确定添加** (add). 
    
    3. In the confirmation dialog box, click **OK**.
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **msoid**
    
        - **解析类型** (type): **CNAME记录**
    
        - **对应值** (value): **clientconfig.partner.microsoftonline-p.net.cn**
    
        - **TTL**: **3600**
    
    2. Click **确定添加** (add). 
    
    3. In the confirmation dialog box, click **OK**.
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to the [your domains list at WEST263](http://west263.com/manager/domain) and sign in. 
    
    ![Sign in to WEST263](../media/c1042b3b-9560-4383-ba24-ae1f522b17c5.png)
  
2. In the right pane, in the **管理** ( management) column for the domain that you want to update, click **管理** ( management). 
    
    ![Click "管理"](../media/a1fc5365-da24-4d6f-b51b-706485e1a065.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/5263e2de-81f1-4cdf-805e-4e2d0ce62bae.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **解析类型** (type): **TXT记录**
    
  - **对应值** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **TTL**: **3600**
    
    ![Select "TXT记录"](../media/5e34c5cd-72d0-46dd-9c8c-05258d1108d0.png)
  
5. Click **确定添加** (add). 
    
    ![Add TXT record](../media/6d00a4e5-d332-4514-b7c1-1a0267c7516d.png)
  
6. In the confirmation dialog box, click **OK**.
    


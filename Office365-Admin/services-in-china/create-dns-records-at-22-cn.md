---
title: "Create DNS records at 22.cn for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_22cn'
- 'O365M_DOM_22cn'
- 'O365E_DOM_22cn'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: e59285bf-fdc2-4149-9bdf-4cbe354fa5e8
description: "Learn to setup your own DNS records at 22.cn for Office 365 operated by 21Vianet in China."
---

# Create DNS records at 22.cn for Office 365

> [!CAUTION]
> The 22.cn website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at 22.cn, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
     
After you add these records at 22.cn, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/458df053-2c8f-4d96-9488-4d2f1aa01e68), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [your domains list at 22.cn](https://www.22.cn/) and sign in. 
    
    ![Sign in to 22.cn](../media/6aeb0d2e-4844-499d-9cdf-278c5490e40b.png)
  
2. In the right pane, click the name of the domain that you want to update.
    
    ![Click the domain you want to update](../media/9118a9a5-0815-4254-be7e-fbfb3570af0e.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/2fd80f2c-30ad-4ba3-a376-4afb54ae3ced.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (type): **TXT**
    
  - **IP地址/主机名** (value): Paste the **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **线路类型** (network): Use the default value. 
    
    ![Click "TXT"](../media/58ad8a10-fac6-4231-aca4-c7763873a8ef.png)
  
5. Click **添加一条** (add). 
    
    ![Add TXT record](../media/f8755878-41aa-4c92-a409-8ebbb3c271f3.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
## Add MX record
<a name="BKMK_add_MX"> </a>

1. In your browser, go to the [your domains list at 22.cn](https://www.22.cn/) and sign in. 
    
    ![Sign in to 22.cn](../media/6aeb0d2e-4844-499d-9cdf-278c5490e40b.png)
  
2. In the right pane, click the name of the domain that you want to update.
    
    ![Click the domain you want to update](../media/9118a9a5-0815-4254-be7e-fbfb3570af0e.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/2fd80f2c-30ad-4ba3-a376-4afb54ae3ced.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (type): **MX**
    
  - **IP地址/主机名** (value): Paste the **Points to address** value rom Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **优先级** (priority): **0**
    
  - **线路类型** (network): Use the default value. 
    
    ![Select "MX"](../media/24926b7b-7ba0-45c0-9752-6752483a7321.png)
  
5. Click **添加一条** (add). 
    
    ![Add MX record](../media/b3fd9715-d206-4c16-afaa-3d45d7695551.png)
  
6. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. On the row of the obsolete record, click **删除** (remove). 
    
    2. In the confirmation dialog box, click **确定** (OK). 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to the [your domains list at 22.cn](https://www.22.cn/) and sign in. 
    
        ![Sign in to 22.cn](../media/6aeb0d2e-4844-499d-9cdf-278c5490e40b.png)
  
    2. In the right pane, click the name of the domain that you want to update.
    
        ![Click the domain you want to update](../media/9118a9a5-0815-4254-be7e-fbfb3570af0e.png)
  
    3. Click the **域名解析** (domain name resolution) tab. 
    
        The DNS records page for your domain opens.
    
        ![Click "域名解析"](../media/2fd80f2c-30ad-4ba3-a376-4afb54ae3ced.png)
  
    4. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机记录** (host name): **autodiscover**
    
        - **记录类型** (type): **CNAME**
    
        - **IP地址/主机名** (value): **autodiscover.partner.outlook.cn**
    
        - **线路类型** (network): Use the default value. 
    
        ![Click "CNAME"](../media/617dd0ac-867f-40d9-a021-e9d8edc36e8f.png)
  
    5. Click **添加一条** (add). 
    
        ![Add CNAME record](../media/28aab97c-ab54-4f54-8a26-f8bef9bd5ddd.png)
  
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机记录** (host name): **lyncdiscover**
    
        - **记录类型** (type): **CNAME**
    
        - **IP地址/主机名** (value): **webdir.online.partner.lync.cn**
    
        - **线路类型** (network): Use the default value. 
    
    2. Click **添加一条** (add). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机记录** (host name): **sip**
    
        - **记录类型** (type): **CNAME**
    
        - **IP地址/主机名** (value): **sipdir.online.partner.lync.cn**
    
        - **线路类型** (network): Use the default value. 
    
    2. Click **添加一条** (add). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机记录** (host name): **msoid**
    
        - **记录类型** (type): **CNAME**
    
        - **IP地址/主机名** (value): **clientconfig.partner.microsoftonline-p.net.cn**
    
        - **线路类型** (network): Use the default value. 
    
    2. Click **添加一条** (add). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to the [your domains list at 22.cn](https://www.22.cn/) and sign in. 
    
    ![Sign in to 22.cn](../media/6aeb0d2e-4844-499d-9cdf-278c5490e40b.png)
  
2. In the right pane, click the name of the domain that you want to update.
    
    ![Click the domain you want to update](../media/9118a9a5-0815-4254-be7e-fbfb3570af0e.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/2fd80f2c-30ad-4ba3-a376-4afb54ae3ced.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (type): **TXT**
    
  - **IP地址/主机名** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Click "TXT"](../media/58ad8a10-fac6-4231-aca4-c7763873a8ef.png)
  
  - **线路类型** (network): Use the default value. 
    
5. Click **添加一条** (add). 
    
    ![Add TXT record](../media/f8755878-41aa-4c92-a409-8ebbb3c271f3.png)
  


---
title: "Create DNS records at HiChina for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_HiChina'
- 'O365M_DOM_HiChina'
- 'O365E_DOM_HiChina'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: 0d38b34f-c31d-4b26-81e1-1df83b2592ae
description: "Learn to setup your own DNS records at HiChina Services for Office 365 operated by 21Vianet in China."
---

# Create DNS records at HiChina for Office 365

If HiChina is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
    
After you add these records at HiChina, your domain will be set up to work with Office 365 services.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/53b93948-1dee-40e6-b463-1cfc47fd86c5), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domain and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
2. Click **新增解析** (add a record). 
    
    ![Click "新增解析"](../media/438d0bda-f2ff-46b6-a5c0-ca89315908f0.png)
  
3. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **记录类型** (record type): **TXT**
    
  - **主机记录(RR)** (host name): **@**
    
  - **解析线路** (network): Use the default value 
    
  - **记录值** (record value): Paste **Destination or Points to Address** from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **TTL**: **10分钟** (10 minutes) 
    
    ![Add TXT record](../media/246931a5-7541-4524-9912-a672f46c5d01.png)
  
4. Click **保存** (save). 
    
## Add an MX record to route email
<a name="BKMK_add_MX"> </a>

Add an MX record so email for your domain will come to Office 365.
  
1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domain and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
2. In the left pane, click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/ad8821b9-d7a7-4915-9aec-255e4c5bed93.png)
  
3. Click **新增解析** (add a record). 
    
    ![Click "新增解析"](../media/438d0bda-f2ff-46b6-a5c0-ca89315908f0.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **记录类型** (record type): **MX**
    
  - **主机记录(RR)** (host name): **@**
    
  - **解析线路** (network): Use the default value 
    
  - **记录值** (record value): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from Office 365. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **MX优先级** (MX priority): **1**
    
  - **TTL**: **10分钟** (10 minutes) 
    
    ![Add MX record](../media/6c46b33c-2b4e-4ec2-aa49-fe6caffeccdc.png)
  
5. Click **保存** (save). 
    
6. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. Find the obsolete record. 
    
    2. In the **操作** (actions) column for the record, click **删除** (remove). 
    
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domain and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
2. In the left pane, click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/ad8821b9-d7a7-4915-9aec-255e4c5bed93.png)
  
3. Add the email (Exchange) Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, click **新增解析** (add a record). 
    
        ![Click "新增解析"](../media/438d0bda-f2ff-46b6-a5c0-ca89315908f0.png)
  
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
    - **记录类型** (record type): **CNAME**
    
    - **主机记录(RR)** (host name): **autodiscover**
    
    - **解析线路** (network): Use the default value 
    
    - **记录值** (record value): **autodiscover.partner.outlook.cn**
    
    - **TTL**: **10分钟** (10 minutes) 
    
        ![Add CNAME record](../media/39f5e4dd-7c32-4845-a58a-0b4af904de3b.png)
  
    3. Click **保存** (save). 
    
4. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, click **新增解析** (add a record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **记录类型** (record type): **CNAME**
    
        - **主机记录(RR)** (host name): **lyncdiscover**
    
        - **解析线路** (network): Use the default value 
    
        - **记录值** (record value): **webdir.online.partner.lync.cn**
    
        - **TTL**: **10分钟** (10 minutes) 
    
    3. Click **保存** (save). 
    
5. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, click **新增解析** (add a record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **记录类型** (record type): **CNAME**
    
        - **主机记录(RR)** (host name): **sip**
    
        - **解析线路** (network): Use the default value 
    
        - **记录值** (record value): **sipdir.online.partner.lync.cn**
    
        - **TTL**: **10分钟** (10 minutes) 
   
    3. Click **保存** (save). 
    
6. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, click **新增解析** (add a record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **记录类型** (record type): **CNAME**
    
        - **主机记录(RR)** (host name): **msoid**
    
        - **解析线路** (network): Use the default value 
    
        - **记录值** (record value): **clientconfig.partner.microsoftonline-p.net.cn**
    
        - **TTL**: **10分钟** (10 minutes) 
    
    3. Click **保存** (save). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domain and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
2. In the left pane, click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/ad8821b9-d7a7-4915-9aec-255e4c5bed93.png)
  
3. Click **新增解析** (add a record). 
    
    ![Click "新增解析"](../media/438d0bda-f2ff-46b6-a5c0-ca89315908f0.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **记录类型** (record type): **TXT**
    
  - **主机记录(RR)** (host name): **@**
    
  - **解析线路** (network): Use the default value 
    
  - **记录值** (record value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **TTL**: **10分钟** (10 minutes) 
    
    ![Add TXT record](../media/246931a5-7541-4524-9912-a672f46c5d01.png)
  
5. Click **保存** (save). 
    
## Add SRV records
<a name="BKMK_add_SRV"> </a>

1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domain and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
2. In the left pane, click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/ad8821b9-d7a7-4915-9aec-255e4c5bed93.png)
  
3. Add the SIP SRV record for Lync federation.
    
    1. On the DNS records page for your domain, click **新增解析** (add a record). 
    
        ![Click "新增解析"](../media/438d0bda-f2ff-46b6-a5c0-ca89315908f0.png)
  
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **记录类型** (record type): **SRV**
    
        - **主机记录(RR)** (host name): **_sipfederationtls._tcp**
    
        - **解析线路** (network): Use the default value 
    
        - **记录值** (record value): **100 1 5061 sipfed.online.partner.lync.cn**
    
        - **TTL**: **10分钟** (10 minutes) 
    
    ![Add SRV record](../media/6e11ad2d-15af-4369-b4b3-d78692cbfe65.png)
  
    3. Click **保存** (save). 
    
4. Add the SIP SRV record for Lync web conferencing.
    
    1. On the DNS records page for your domain, click **新增解析** (add a record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **记录类型** (record type): **SRV**
    
        - **主机记录(RR)** (host name): **_sip._tls**
    
        - **解析线路** (network): Use the default value 
    
        - **记录值** (record value): **100 1 443 sipdir.online.partner.lync.cn**
    
        - **TTL**: **10分钟** (10 minutes) 
    
    3. Click **保存** (save). 
    


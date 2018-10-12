---
title: "Create DNS records at East.net for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_East'
- 'O365M_DOM_East'
- 'O365E_DOM_East'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: a428f6cf-e471-418a-a4e9-518bea7c2cd5
description: "Learn to setup your own DNS records at East.net for Office 365 operated by 21Vianet in China."
---

# Create DNS records at East.net for Office 365

If east.net is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-east-net.md#BKMK_verify_domain)
    
- [Add an MX record to route email](create-dns-records-at-east-net.md#BKMK_add_MX)
    
- [Add CNAME records](create-dns-records-at-east-net.md#BKMK_add_CNAME)
    
- [Add a TXT record to help prevent spam](create-dns-records-at-east-net.md#BKMK_add_TXT)
    
- [Add SRV records](create-dns-records-at-east-net.md#BKMK_add_SRV)
    
After you add these records at east.net, your domain will be set up to work with Office 365 services.
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
    ![Sign in to east.net](../media/62d3e9d5-1fdc-45b9-bc72-0bde89168377.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
    ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析" (domain name resolution)](../media/88907339-c195-41a0-9ac1-f903d2812af9.png)
  
4. In the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): Leave the box blank 
    
  - **类型** (type): **TXT**
    
  - **值** (value): Paste the **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Select "TXT"](../media/67d6d897-0696-4f3c-a5bf-596132dc676e.png)
  
5. Click **新增** (add). 
    
    ![Add TXT record](../media/a8c12de1-34ad-42c1-b6cd-f1285c9a5f43.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
## Add an MX record to route email
<a name="BKMK_add_MX"> </a>

1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
    ![Sign in to east.net](../media/62d3e9d5-1fdc-45b9-bc72-0bde89168377.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
    ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析" (domain name resolution)](../media/88907339-c195-41a0-9ac1-f903d2812af9.png)
  
4. In the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): Leave the box blank. 
    
  - **类型** (type): **MX**
    
  - **值** (value): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **优先级** (priority): **0**
    
    ![Select "MX"](../media/a0a8aa1d-153d-4808-9c4f-2605a5d9976d.png)
  
5. Click **新增** (add). 
    
    ![Add MX record](../media/678b9427-3c58-470c-bab3-bbcd90ce89c1.png)
  
6. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. In the **当前解析列表** (current DNS records) section, on the row of the obsolete record, click **删除** (remove). 
    
    2. In the confirmation dialog box, click **OK**.
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
        ![Sign in to east.net](../media/62d3e9d5-1fdc-45b9-bc72-0bde89168377.png)
  
    2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
        ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
    3. Click the **域名解析** (domain name resolution) tab. 
    
        The DNS records page for your domain opens.
    
        ![Click "域名解析" (domain name resolution)](../media/88907339-c195-41a0-9ac1-f903d2812af9.png)
  
    4. On the DNS records page for your domain, in the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **autodiscover**
    
        - **类型** (type): **CNAME**
    
        - **值** (value): **autodiscover.partner.outlook.cn**
    
        ![Select "CNAME"](../media/04500bbe-e06b-434e-85b7-c54685e1d42f.png)
  
    5. Click **新增** (add). 
    
    ![Add CNAME record](../media/ad57a360-b75a-42d1-b529-e1e17e3acee1.png)
  
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **lyncdiscover**
    
        - **类型** (type): **CNAME**
    
        - **值** (value): **webdir.online.partner.lync.cn**
    
    2. Click **新增** (add). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **sip**
    
        - **类型** (type): **CNAME**
    
        - **值** (value): **sipdir.online.partner.lync.cn**
    
    2. Click **新增** (add). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **msoid**
    
        - **类型** (type): **CNAME**
    
        - **值** (value): **clientconfig.partner.microsoftonline-p.net.cn**
    
    2. Click **新增** (add). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
    ![Sign in to east.net](../media/62d3e9d5-1fdc-45b9-bc72-0bde89168377.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
    ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析" (domain name resolution)](../media/88907339-c195-41a0-9ac1-f903d2812af9.png)
  
4. In the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): Leave the box blank. 
    
  - **类型** (type): **TXT**
    
  - **值** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Select "TXT"](../media/67d6d897-0696-4f3c-a5bf-596132dc676e.png)
  
5. Click **新增** (add). 
    
    ![Add TXT record](../media/a8c12de1-34ad-42c1-b6cd-f1285c9a5f43.png)
  
## Add SRV records
<a name="BKMK_add_SRV"> </a>

1. Add the SIP SRV record for Lync federation.
    
    1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
        ![Sign in to east.net](../media/62d3e9d5-1fdc-45b9-bc72-0bde89168377.png)
  
    2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
        ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
    3. Click the **域名解析** (domain name resolution) tab. 
    
        The DNS records page for your domain opens.
    
        ![Click "域名解析" (domain name resolution)](../media/88907339-c195-41a0-9ac1-f903d2812af9.png)
  
    4. On the DNS records page for your domain, in the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **_sipfederationtls._tcp**
    
        - **类型** (type): **SRV**
    
        - **值** (value): **1 5061 sipfed.online.partner.lync.cn**
    
        ![Select "SRV"](../media/74aa3363-0e1a-4b6b-b2e9-2a6605643526.png)
  
    5. Click **新增** (add). 
    
    ![Add SRV record](../media/3e52bc42-efff-4acd-80b3-f7815ae5cd2e.jpg)
  
2. Add the SIP SRV record for Lync web conferencing.
    
    1. On the DNS records page for your domain, in the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **_sip._tls**
    
        - **类型** (type): **SRV**
    
        - **值** (value): **1 443 sipdir.online.partner.lync.cn**
    
    2. Click **新增** (add). 
    


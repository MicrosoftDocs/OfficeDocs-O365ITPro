---
title: "Create DNS records at ENAME for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_ENAME'
- 'O365M_DOM_ENAME'
- 'O365E_DOM_ENAME'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 50193085-0f1d-4bf2-9c76-1f62b78b835e
description: "Learn to setup your own DNS records at ENAME Services for Office 365 operated by 21Vianet in China."
---

# Create DNS records at ENAME for Office 365

> [!CAUTION]
> The ENAME website doesn't support SRV records, which means that several Lync Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If despite the service limitations, you choose to manage your own Office 365 DNS records at ENAME, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-ename.md#BKMK_verify_domain)
    
- [Add an MX record to route email](create-dns-records-at-ename.md#BKMK_add_MX)
    
- [Add CNAME records](create-dns-records-at-ename.md#BKMK_add_CNAME)
    
- [Add a TXT record to help prevent spam](create-dns-records-at-ename.md#BKMK_add_TXT)
    
After you add these records at ENAME, your domain will be set up to work with Office 365 services, though not with the Lync Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [Add records at ENAME to set up your SharePoint Online Public Website](https://support.office.com/article/aaddc359-44c1-4252-8f34-8ba90bb85aaf), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at ENAME](https://www.ename.net/manage/domainlist) and sign in. 
    
    ![Sign in to ENAME](../media/6d6c0ca0-576f-4112-bf02-173caa62cba2.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/93ce0fff-1ab3-4d3f-8861-291fe16b85a3.png)
  
3. Click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析 "](../media/660a9979-53bb-43b9-a1e3-5fccffd1a6c5.png)
  
4. Click **添加记录** (add a record). 
    
    ![Click "添加记录"](../media/518c8698-c209-4237-8d20-a3a0cf1d7c68.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (record type): **TXT**
    
  - **记录值(IP/域名)** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*  . [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - ** 线路类型 ** (network): Use the default value. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/2f9119ef-46de-4ba5-adbc-1bec5fbe24ea.png)
  
6. Click **保存** (save). 
    
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

1. In your browser, go to [your domains list at ENAME](https://www.ename.net/manage/domainlist) and sign in. 
    
    ![Sign in to ENAME](../media/6d6c0ca0-576f-4112-bf02-173caa62cba2.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/93ce0fff-1ab3-4d3f-8861-291fe16b85a3.png)
  
3. Click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析 "](../media/660a9979-53bb-43b9-a1e3-5fccffd1a6c5.png)
  
4. Click **添加记录** (add a record). 
    
    ![Click "添加记录"](../media/518c8698-c209-4237-8d20-a3a0cf1d7c68.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (record type): **MX**
    
  - **记录值(IP/域名)** (value): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. 
  
[Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - ** 线路类型 ** (network): Use the default value. 
    
  - **MX优先级** (MX priority): **0**
    
  - **TTL**: **3600**
    
    ![Add MX record](../media/bfd9596b-8788-41be-8e31-671d7e9f1dc6.png)
  
6. Click **保存** (save). 
    
7. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
1. Find the obsolete record.
    
2. On the row of the obsolete record, click **删除** (remove). 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
1. In your browser, go to [your domains list at ENAME](https://www.ename.net/manage/domainlist) and sign in. 
    
    ![Sign in to ENAME](../media/6d6c0ca0-576f-4112-bf02-173caa62cba2.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/93ce0fff-1ab3-4d3f-8861-291fe16b85a3.png)
  
3. Click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析 "](../media/660a9979-53bb-43b9-a1e3-5fccffd1a6c5.png)
  
4. On the DNS records page for your domain, click **添加记录** (add a record). 
    
    ![Click "添加记录"](../media/518c8698-c209-4237-8d20-a3a0cf1d7c68.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): **autodiscover**
    
  - **记录类型** (record type): **CNAME**
    
  - **记录值(IP/域名)** (value): **autodiscover.partner.outlook.cn**
    
  - ** 线路类型 ** (network): Use the default value. 
    
  - **TTL**: **3600**
    
    ![Add CNAME record](../media/7b926a66-ea8b-4775-b929-0cbbab10d82f.png)
  
6. Click **保存** (save). 
    
2. Add the Lync Autodiscover CNAME record.
    
1. On the DNS records page for your domain, click **添加记录** (add a record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): **lyncdiscover**
    
  - **记录类型** (record type): **CNAME**
    
  - **记录值(IP/域名)** (value): **webdir.online.partner.lync.cn**
    
  - ** 线路类型 ** (network): Use the default value. 
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    
3. Add the Lync SIP CNAME record.
    
1. On the DNS records page for your domain, click **添加记录** (add a record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): **sip**
    
  - **记录类型** (record type): **CNAME**
    
  - **记录值(IP/域名)** (value): **sipdir.online.partner.lync.cn**
    
  - ** 线路类型 ** (network): Use the default value. 
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
1. On the DNS records page for your domain, click **添加记录** (add a record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): **msoid**
    
  - **记录类型** (record type): **CNAME**
    
  - **记录值(IP/域名)** (value): **clientconfig.partner.microsoftonline-p.net.cn**
    
  - ** 线路类型 ** (network): Use the default value. 
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [your domains list at ENAME](https://www.ename.net/manage/domainlist) and sign in. 
    
    ![Sign in to ENAME](../media/6d6c0ca0-576f-4112-bf02-173caa62cba2.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/93ce0fff-1ab3-4d3f-8861-291fe16b85a3.png)
  
3. Click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析 "](../media/660a9979-53bb-43b9-a1e3-5fccffd1a6c5.png)
  
4. Click **添加记录** (add a record). 
    
    ![Click "添加记录"](../media/518c8698-c209-4237-8d20-a3a0cf1d7c68.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (record type): **TXT**
    
  - **记录值(IP/域名)** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - ** 线路类型 ** (network): Use the default value. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/2f9119ef-46de-4ba5-adbc-1bec5fbe24ea.png)
  
6. Click **保存** (save). 
    


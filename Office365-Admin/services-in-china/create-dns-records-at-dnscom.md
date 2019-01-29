---
title: "Create DNS records at DNSCOM for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DNSCOM'
- 'O365M_DOM_DNSCOM'
- 'O365E_DOM_DNSCOM'
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
ms.assetid: e703bc41-3711-4578-9ea9-78123cd9b67c
description: "Learn to setup your own DNS records at DNSCOM for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at DNSCOM for Office 365

> [!CAUTION]
> The DNSCOM website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at DNSCOM, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
After you add these records at DNSCOM, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/a6aa103b-d6ca-4752-bd60-b0c002d640cb), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [DNSCOM domain management system](http://mgt.dns.com.cn/index.php) and sign in with your domain name and password. 
    
    ![Sign in to DNSCOM domain management system](../media/e1714e30-2f91-4987-b0bc-647145d854b4.png)
  
2. Click **MyDNS功能** (MyDNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "MyDNS功能"](../media/a407306f-4d10-429b-812a-5f31153c61a5.png)
  
3. In the **纯域名列表** (domain list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **类型** (type): **TXT**
    
  - **指向** (point to): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*  . [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Add TXT record](../media/39e6d11c-3a2b-4a01-bb84-bd00916523dd.png)
  
4. Click **保存** (save). 
    
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

1. In your browser, go to [DNSCOM domain management system](http://mgt.dns.com.cn/index.php) and sign in with your domain name and password. 
    
    ![Sign in to DNSCOM domain management system](../media/e1714e30-2f91-4987-b0bc-647145d854b4.png)
  
2. Click **MyDNS功能** (MyDNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "MyDNS功能"](../media/a407306f-4d10-429b-812a-5f31153c61a5.png)
  
3. In the **纯域名列表** (domain list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **类型** (type): **MX**
    
  - **顺序** (priority): **0**
    
  - **指向** (point to): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
    ![Add MX record](../media/254f349a-4711-43be-9c0f-9ab764f57b0d.png)
  
4. Click **保存** (save). 
    
5. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. Find the obsolete record.
    
    2. On the row of the obsolete record, click **删除** (remove). 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to [DNSCOM domain management system](http://mgt.dns.com.cn/index.php) and sign in with your domain name and password. 
    
        ![Sign in to DNSCOM domain management system](../media/e1714e30-2f91-4987-b0bc-647145d854b4.png)
  
    2. Click **MyDNS功能** (MyDNS settings). 
    
        The DNS records page for your domain opens.
    
        ![Click "MyDNS功能"](../media/a407306f-4d10-429b-812a-5f31153c61a5.png)
  
    3. On the DNS records page for your domain, in the **主机记录列表** (host record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **域名** (host name): **autodiscover**
    
        - **类型** (type): **CNAME**
    
        - **指向** (point to): **autodiscover.partner.outlook.cn**
    
    4. Click **保存** (save). 
    
    ![Add CNAME record](../media/12cefe54-e6c8-4769-962c-302ed89d3ec0.png)
  
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **主机记录列表** (host record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **域名** (host name): **lyncdiscover**
    
        - **类型** (type): **CNAME**
    
        - **指向** (point to): **webdir.online.partner.lync.cn**
    
    2. Click **保存** (save). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **主机记录列表** (host record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **域名** (host name): **sip**
    
        - **类型** (type): **CNAME**
    
        - **指向** (point to): **sipdir.online.partner.lync.cn**
    
    2. Click **保存** (save). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **主机记录列表** (host record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **域名** (host name): **msoid**
    
        - **类型** (type): **CNAME**
    
        - **指向** (point to): **clientconfig.partner.microsoftonline-p.net.cn**
    
    2. Click **保存** (save). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [DNSCOM domain management system](http://mgt.dns.com.cn/index.php) and sign in with your domain name and password. 
    
    ![Sign in to DNSCOM domain management system](../media/e1714e30-2f91-4987-b0bc-647145d854b4.png)
  
2. Click **MyDNS功能** (MyDNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "MyDNS功能"](../media/a407306f-4d10-429b-812a-5f31153c61a5.png)
  
3. In the **纯域名列表** (domain list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **类型** (type): **TXT**
    
  - **指向** (point to): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/39e6d11c-3a2b-4a01-bb84-bd00916523dd.png)
  
4. Click **保存** (save). 
    


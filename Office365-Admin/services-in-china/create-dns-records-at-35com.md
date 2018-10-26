---
title: "Create DNS records at 35COM for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_35COM'
- 'O365M_DOM_35COM'
- 'O365E_DOM_35COM'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: dfa8ce0b-9c06-4de8-b0f0-835920f25375
description: "Learn to setup your own DNS records at 35COM for Office 365 operated by 21Vianet in China."
---

# Create DNS records at 35COM for Office 365

> [!CAUTION]
> The 35COM website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at 35COM, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.

After you add these records at 35COM, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/a5d0e814-bc41-4eba-9990-90a91007ee0d), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [35COM domain management system](https://www.dns-diy.net/home.aspx) and sign in with your domain name and password. 
    
    ![Sign in to 35COM DNS-DIY system](../media/f40bf946-ee14-43fb-8714-278b89904ee2.png)
  
2. On the **DNS服务在线协议** (DNS service agreement) page, read the agreement and click **同意** (agree). 
    
    The DNS records page for your domain opens.
    
    ![Click "同意"](../media/d2e57676-77f8-4dff-9650-2532dbc83d47.png)
  
3. In the empty record, make sure that the fields are set to precisely the following values:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **类型** (type): **TXT**
    
  - **IP地址/主机名** (points to): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **优先级** (priority): Leave the box blank. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/ef04f942-9e42-4815-96d2-931b274aa557.png)
  
4. Click **新增** (add). 
    
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

1. In your browser, go to [35COM domain management system](https://www.dns-diy.net/home.aspx) and sign in with your domain name and password. 
    
    ![Sign in to 35COM DNS-DIY system](../media/f40bf946-ee14-43fb-8714-278b89904ee2.png)
  
2. On the **DNS服务在线协议** (DNS service agreement) page, read the agreement and click **同意** (agree). 
    
    The DNS records page for your domain opens.
    
    ![Click "同意"](../media/d2e57676-77f8-4dff-9650-2532dbc83d47.png)
  
3. In the empty record, make sure that the fields are set to precisely the following values:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **类型** (type): **MX**
    
  - **IP地址/主机名** (points to): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn. You must append a dot (.) to the value to make it work. 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **优先级** (priority): **0**
    
  - **TTL**: **3600**
    
    ![Add MX record](../media/ab833520-b82f-4aca-a7a6-f7afee9677e9.png)
  
4. Click **新增** (add). 
    
5. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. Find the obsolete record. 
    
    2. On the **删除** (remove) column of the obsolete record, click **X** button. 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to [35COM domain management system](https://www.dns-diy.net/home.aspx) and sign in with your domain name and password. 
    
        ![Sign in to 35COM DNS-DIY system](../media/f40bf946-ee14-43fb-8714-278b89904ee2.png)
  
    2. On the **DNS服务在线协议** (DNS service agreement) page, read the agreement and click **同意** (agree). 
    
        The DNS records page for your domain opens.
    
        ![Click "同意"](../media/d2e57676-77f8-4dff-9650-2532dbc83d47.png)
  
    3. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **autodiscover**
    
        - **类型** (type): **CNAME**
    
        - **IP地址/主机名** (points to): **autodiscover.partner.outlook.cn.**
    
        - **优先级** (priority): Leave the box blank. 
    
        - **TTL**: **3600**
    
        ![Add CNAME record](../media/2d040856-f5c1-490c-bc1e-500cbb951eaf.png)
  
    4. Click **新增** (add). 
    
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **lyncdiscover**
    
        - **类型** (type): **CNAME**
    
        - **IP地址/主机名** (points to): **webdir.online.partner.lync.cn.**
    
        - **优先级** (priority): Leave the box blank. 
    
        - **TTL**: **3600**
    
    2. Click **新增** (add). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **sip**
    
        - **类型** (type): **CNAME**
    
        - **IP地址/主机名** (points to): **sipdir.online.partner.lync.cn.**
    
        - **优先级** (priority): Leave the box blank. 
    
        - **TTL**: **3600**
    
    2. Click **新增** (add). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **msoid**
    
        - **类型** (type): **CNAME**
    
        - **IP地址/主机名** (points to): **clientconfig.partner.microsoftonline-p.net.cn.**
    
        - **优先级** (priority): Leave the box blank. 
    
        - **TTL**: **3600**
    
    2. Click **新增** (add). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [35COM domain management system](https://www.dns-diy.net/home.aspx) and sign in with your domain name and password. 
    
    ![Sign in to 35COM DNS-DIY system](../media/f40bf946-ee14-43fb-8714-278b89904ee2.png)
  
2. On the **DNS服务在线协议** (DNS service agreement) page, read the agreement and click **同意** (agree). 
    
    The DNS records page for your domain opens.
    
    ![Click "同意"](../media/d2e57676-77f8-4dff-9650-2532dbc83d47.png)
  
3. In the empty record, make sure that the fields are set to precisely the following values:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **类型** (type): **TXT**
    
  - **IP地址/主机名** (points to): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **优先级** (priority): Leave the box blank. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/ef04f942-9e42-4815-96d2-931b274aa557.png)
  
4. Click **新增** (add). 
    


---
title: "Create DNS records at CNDNS for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_CNDNS'
- 'O365M_DOM_CNDNS'
- 'O365E_DOM_CNDNS'
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
ms.assetid: ce8cce16-9d20-4b1b-aefd-86d4dceb6ed6
description: "Learn to setup your own DNS records at CNDNS for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at CNDNS for Office 365

> [!CAUTION]
> The CNDNS website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at CNDNS, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on. here's how to set them up. 
  
After you add these records at CNDNS, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/d80ffb87-aa51-495c-8133-454d7b75253b), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at CNDNS](https://www.cndns.com/) and sign in. 
    
    ![Sign in to CNDNS](../media/e9a982be-5751-49ca-a6e5-c227eedffc7e.png)
  
2. In the **操作** (actions) column for the domain that you want to update, click **解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "解析"](../media/4613ead0-8c68-44d6-8708-b87bb5a778f7.png)
  
3. In the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): **@**
    
  - **记录类型** (record type): **TXT记录** (TXT record) 
    
  - **记录值** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Add TXT record](../media/6b20a743-1d8b-463f-978a-d48f21846001.png)
  
4. Click **立即添加** (add). 
    
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

1. In your browser, go to [your domains list at CNDNS](https://www.cndns.com/) and sign in. 
    
    ![Sign in to CNDNS](../media/e9a982be-5751-49ca-a6e5-c227eedffc7e.png)
  
2. In the **操作** (actions) column for the domain that you want to update, click **解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "解析"](../media/4613ead0-8c68-44d6-8708-b87bb5a778f7.png)
  
3. In the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): **@**
    
  - **记录类型** (record type): **MX记录** (MX record) 
    
  - **优先级** (priority): **0**
    
  - **记录值** (value): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
    ![Add MX record](../media/8a49067d-a646-4414-b9c8-28ec269bd104.png)
  
4. Click **立即添加** (add). 
    
5. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. From the **域名解析记录列表** (DNS record list) section, find the row of the obsolete record. 
    
    2. In the **操作** (actions) column, click **删除** (remove). 
    
## Add CNAME records

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to [your domains list at CNDNS](https://www.cndns.com/) and sign in. 
    
        ![Sign in to CNDNS](../media/e9a982be-5751-49ca-a6e5-c227eedffc7e.png)
  
    2. In the **操作** (actions) column for the domain that you want to update, click **解析** (domain name resolution). 
    
        The DNS records page for your domain opens.
    
        ![Click "解析"](../media/4613ead0-8c68-44d6-8708-b87bb5a778f7.png)
  
    3. On the DNS records page for your domain, in the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **autodiscover**
    
        - **记录类型** (record type): **CNAME记录** (CNAME record) 
    
        - **记录值** (value): **autodiscover.partner.outlook.cn**
    
        ![Add CNAME record](../media/8a8cf00a-f8a5-47f3-bf4a-ad099929df43.png)
  
    4. Click **立即添加** (add). 
    
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **lyncdiscover**
    
        - **记录类型** (record type): **CNAME记录** (CNAME record) 
    
        - **记录值** (value): **webdir.online.partner.lync.cn**
    
    2. Click **立即添加** (add). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **sip**
    
        - **记录类型** (record type): **CNAME记录** (CNAME record) 
    
        - **记录值** (value): **sipdir.online.partner.lync.cn**
    
    2. Click **立即添加** (add). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **主机名** (host name): **msoid**
    
        - **记录类型** (record type): **CNAME记录** (CNAME record) 
    
        - **记录值** (value): **clientconfig.partner.microsoftonline-p.net.cn**
    
    2. Click **立即添加** (add). 
    
## Add a TXT record to help prevent spam

1. In your browser, go to [your domains list at CNDNS](https://www.cndns.com/) and sign in. 
    
    ![Sign in to CNDNS](../media/e9a982be-5751-49ca-a6e5-c227eedffc7e.png)
  
2. In the **操作** (actions) column for the domain that you want to update, click **解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "解析"](../media/4613ead0-8c68-44d6-8708-b87bb5a778f7.png)
  
3. In the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): **@**
    
  - **记录类型** (record type): **TXT记录** (TXT record) 
    
  - **记录值** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/6b20a743-1d8b-463f-978a-d48f21846001.png)
  
4. Click **立即添加** (add). 
    


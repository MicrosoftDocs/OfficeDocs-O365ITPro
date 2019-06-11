---
title: "Create DNS records at Xinnet for Office 365"
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
ms.assetid: 36ecc37f-fd4f-44d6-a013-7dba396e8ccc
description: "Learn to setup your own DNS records at Xinnet for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at Xinnet for Office 365

> [!CAUTION]
> The Xinnet website doesn't support SRV records, which means that several Lync Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at Xinnet, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on. here's how to set them up. 
    
After you add these records at Xinnet, your domain will be set up to work with Office 365 services, though not with the Lync Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/911fe8a5-0488-4457-a024-94473b90431f), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [Xinnet website](http://www.xinnet.com) and sign in. 
    
    ![Sign in to Xinnet](../media/c9d2c80e-0458-4131-88f3-9e1b094d0823.png)
  
2. In the upper-right corner, click **进入我的账户** (access my account). 
    
    ![Click "进入我的账户'](../media/4fbb122f-a08b-4c93-9bfa-f1d059201d6b.png)
  
3. In the left navigation pane, click **我的产品** (my products). 
    
    ![Click "域名管理"](../media/ffc1dfdd-f291-4645-9030-ef84d76edbef.png)
  
4. In the **常规管理** (general management) section, click **域名管理** (domain management). 
    
5. In the right pane, click the **我的域名** (my domains) tab. 
    
    ![Click "我的域名"](../media/b0bfbada-6e17-4857-b718-31a3fab89588.png)
  
6. Select the check box next to the domain that you want to update.
    
    ![Click "mydns解析设置"](../media/07417e01-a4a7-4f74-a444-0bc80b9fb72d.png)
  
7. Click **mydns解析设置** (DNS settings). 
    
    The DNS records page for your domain opens.
    
8. In the **文本记录 (TXT)** section, click ** 添加新的文本记录 ** (add a TXT record). 
    
    ![Click "添加新的文本记录"](../media/d859335c-ea0e-4a00-8217-2ed504d2cdaf.png)
  
9. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **文本记录 (TXT)**: Leave the box blank.
    
  - **文本内容** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **TTL**: Use the default value.
    
    ![Add TXT record](../media/fbbfa817-2a12-43c4-99b9-0e6ef76e9905.png)
  
10. Click **提交** (submit). 
    
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

1. In your browser, go to the [Xinnet website](http://www.xinnet.com) and sign in. 
    
    ![Sign in to Xinnet](../media/c9d2c80e-0458-4131-88f3-9e1b094d0823.png)
  
2. In the upper-right corner, click **进入我的账户** (access my account). 
    
    ![Click "进入我的账户'](../media/4fbb122f-a08b-4c93-9bfa-f1d059201d6b.png)
  
3. In the left navigation pane, click **我的产品** (my products). 
    
    ![Click "域名管理"](../media/ffc1dfdd-f291-4645-9030-ef84d76edbef.png)
  
4. In the **常规管理** (general management) section, click **域名管理** (domain management). 
    
5. In the right pane, click the **我的域名** (my domains) tab. 
    
    ![Click "我的域名"](../media/b0bfbada-6e17-4857-b718-31a3fab89588.png)
  
6. Select the check box next to the domain that you want to update.
    
    ![Click "mydns解析设置"](../media/07417e01-a4a7-4f74-a444-0bc80b9fb72d.png)
  
7. Click **mydns解析设置** (DNS settings). 
    
    The DNS records page for your domain opens.
    
8. In the **邮件交换记录 (MX)** section, click **添加新的邮件记录** (add an MX record). 
    
    ![Click "添加新的邮件记录"](../media/d6022586-c53a-4614-b20b-c211ce03cf6f.png)
  
9. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **邮件交换记录 (MX)**: Leave the box blank.
    
  - **目标主机** (target): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **优先级** (priority): **5**
    
  - **TTL**: Use the default value.
    
    ![Add MX record](../media/e773008e-2646-4172-9f83-c10795e31b0b.png)
  
10. Click **提交** (submit). 
    
11. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. On the row of the obsolete record, click **删除** (remove). 
    
    2. In the confirmation dialog box, click **OK**.
    
## Add the CNAME records required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to the [Xinnet website](http://www.xinnet.com) and sign in. 
    
        ![Sign in to Xinnet](../media/c9d2c80e-0458-4131-88f3-9e1b094d0823.png)
  
    2. In the upper-right corner, click **进入我的账户** (access my account). 
    
        ![Click "进入我的账户'](../media/4fbb122f-a08b-4c93-9bfa-f1d059201d6b.png)
  
    3. In the left navigation pane, click **我的产品** (my products). 
    
        ![Click "域名管理"](../media/ffc1dfdd-f291-4645-9030-ef84d76edbef.png)
  
    4. In the **常规管理** (general management) section, click **域名管理** (domain management). 
    
    5. In the right pane, click the **我的域名** (my domains) tab. 
    
        ![Click "我的域名"](../media/b0bfbada-6e17-4857-b718-31a3fab89588.png)
  
    6. Select the check box next to the domain that you want to update.
    
        ![Click "mydns解析设置"](../media/07417e01-a4a7-4f74-a444-0bc80b9fb72d.png)
  
    7. Click **mydns解析设置** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    8. On the DNS records page for your domain, in the **别名 (CNAME)** section, click **添加新的别名** (add a CNAME record). 
    
    ![Click "添加新的别名"](../media/6a448693-e7d1-478e-b8a8-3664456fed19.png)
  
    9. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **别名 (CNAME)**: **autodiscover**
    
        - **别名主机** (points to): **autodiscover.partner.outlook.cn**
    
        - **TTL**: Use the default value.
    
    ![Add CNAME record](../media/6b9fb7d6-5936-41e0-9603-5068cbf8c4ec.png)
  
    10. Click **提交** (submit). 
    
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **别名 (CNAME)** section, click **添加新的别名** (add a CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **别名 (CNAME)**: **lyncdiscover**
    
        - **别名主机** (points to): **webdir.online.partner.lync.cn**
    
        - **TTL**: Use the default value.
    
    3. Click **提交** (submit). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **别名 (CNAME)** section, click **添加新的别名** (add a CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **别名 (CNAME)**: **sip**
    
        - **别名主机** (points to): **sipdir.online.partner.lync.cn**
    
        - **TTL**: Use the default value.
    
    3. Click **提交** (submit). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **别名 (CNAME)** section, click **添加新的别名** (add a CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **别名 (CNAME)**: **msoid**
    
        - **别名主机** (points to): **clientconfig.partner.microsoftonline-p.net.cn**
    
        - **TTL**: Use the default value.
    
    3. Click **提交** (submit). 
    
## Add TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to the [Xinnet website](http://www.xinnet.com) and sign in. 
    
    ![Sign in to Xinnet](../media/c9d2c80e-0458-4131-88f3-9e1b094d0823.png)
  
2. In the upper-right corner, click **进入我的账户** (access my account). 
    
    ![Click "进入我的账户'](../media/4fbb122f-a08b-4c93-9bfa-f1d059201d6b.png)
  
3. In the left navigation pane, click **我的产品** (my products). 
    
    ![Click "域名管理"](../media/ffc1dfdd-f291-4645-9030-ef84d76edbef.png)
  
4. In the **常规管理** (general management) section, click **域名管理** (domain management). 
    
5. In the right pane, click the **我的域名** (my domains) tab. 
    
    ![Click "我的域名"](../media/b0bfbada-6e17-4857-b718-31a3fab89588.png)
  
6. Select the check box next to the domain that you want to update.
    
    ![Click "mydns解析设置"](../media/07417e01-a4a7-4f74-a444-0bc80b9fb72d.png)
  
7. Click **mydns解析设置** (DNS settings). 
    
    The DNS records page for your domain opens.
    
8. In the **文本记录 (TXT)** section, click ** 添加新的文本记录 ** (add a TXT record). 
    
    ![Click "添加新的文本记录"](../media/d859335c-ea0e-4a00-8217-2ed504d2cdaf.png)
  
9. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **文本记录 (TXT)**: Leave the box blank.
    
  - **文本内容** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **TTL**: Use the default value.
    
    ![Add TXT record](../media/fbbfa817-2a12-43c4-99b9-0e6ef76e9905.png)
  
10. Click **提交** (submit). 
    


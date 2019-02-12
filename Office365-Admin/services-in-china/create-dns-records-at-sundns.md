---
title: "Create DNS records at SUNDNS for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_SUNDNS'
- 'O365M_DOM_SUNDNS'
- 'O365E_DOM_SUNDNS'
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
ms.assetid: 0aad2dc1-e09a-4370-ac5a-b47b41d23f65
description: "Learn to setup your own DNS records at SUNDNS for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at SUNDNS for Office 365

> [!CAUTION]
> The SUNDNS website doesn't support SRV records, which means that several Lync Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, if you manage your DNS records at SUNDNS, there are significant [limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If despite the service limitations, you choose to manage your own Office 365 DNS records at SUNDNS, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
 
    
After you add these records at SUNDNS, your domain will be set up to work with Office 365 Service, though not with the Lync Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/b4f62e26-7cea-4dbb-a648-19cfc93680ee), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [SUNDNS website](http://www.sundns.com/login.php) and sign in. 
    
    ![Sign in to SUNDNS](../media/2e45a261-18c2-4244-817a-ca3eb9f8a369.png)
  
2. On the left navigation tree, under **我的业务** (my business), click **我的DNS** (my DNS). 
    
    ![Click "我的DNS"](../media/6ca2c8a9-6427-4f87-97d5-aadb2c217ee2.png)
  
3. In the right pane, in the **管理** (manage) column for the domain that you want to update, click **管理** (manage). 
    
    The DNS records page for your domain opens.
    
    ![Click "管理"](../media/bf345b18-d27f-40d9-bebc-f23559ec65ec.png)
  
4. In the **文本记录(TXT记录)** (TXT record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): Leave the box blank. 
    
  - **文本内容** (value): Paste the **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Add TXT record](../media/76d547b9-38a5-4eae-943a-e4fcf6f0f4b2.png)
  
5. Click **添加** (add). 
    
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

1. In your browser, go to the [SUNDNS website](http://www.sundns.com/login.php) and sign in. 
    
    ![Sign in to SUNDNS](../media/2e45a261-18c2-4244-817a-ca3eb9f8a369.png)
  
2. On the left navigation tree, under **我的业务** (my business), click **我的DNS** (my DNS). 
    
    ![Click "我的DNS"](../media/6ca2c8a9-6427-4f87-97d5-aadb2c217ee2.png)
  
3. In the right pane, in the **管理** (manage) column for the domain that you want to update, click **管理** (manage). 
    
    The DNS records page for your domain opens.
    
    ![Click "管理"](../media/bf345b18-d27f-40d9-bebc-f23559ec65ec.png)
  
4. In the **邮件交换记录解析(MX记录)** (MX record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
    - **邮件记录** (mail host): Leave the box blank. 
    
    - **服务器名** (value): Paste the **Points to address**value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn. You must append a dot (.) to the end of the value. 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
    - **优先级** (priority): **0**
    
    For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)
    
    ![Add MX record](../media/1b45983d-8a56-423c-8bcd-2b1e47d8becf.png)
  
5. Click **添加** (add). 
    
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. In your browser, go to the [SUNDNS website](http://www.sundns.com/login.php) and sign in. 
    
    ![Sign in to SUNDNS](../media/2e45a261-18c2-4244-817a-ca3eb9f8a369.png)
  
2. On the left navigation tree, under **我的业务** (my business), click **我的DNS** (my DNS). 
    
    ![Click "我的DNS"](../media/6ca2c8a9-6427-4f87-97d5-aadb2c217ee2.png)
  
3. In the right pane, in the **管理** (manage) column for the domain that you want to update, click **管理** (manage). 
    
    The DNS records page for your domain opens.
    
    ![Click "管理"](../media/bf345b18-d27f-40d9-bebc-f23559ec65ec.png)
  
4. Add the email (Exchange) Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **别名记录设置(CNAME记录)** (CNAME record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **别名** (alias): **autodiscover**
    
        - **对应主机名** (point to value): **autodiscover.partner.outlook.cn**
    
    ![Add CNAME record](../media/160d33e2-5ce8-4795-9712-691fbf50a0eb.png)
  
    2. Click **添加** (add). 
    
5. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **别名记录设置(CNAME记录)** (CNAME record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **别名** (alias): **lyncdiscover**
    
        - **对应主机名** (point to value): **webdir.online.partner.lync.cn**
    
    2. Click **添加** (add). 
    
6. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **别名记录设置(CNAME记录)** (CNAME record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **别名** (alias): **sip**
    
        - **对应主机名** (point to value): **sipdir.online.partner.lync.cn**
    
    2. Click **添加** (add). 
    
7. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **别名记录设置(CNAME记录)** (CNAME record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
        - **别名** (alias): **msoid**
    
        - **对应主机名** (point to value): **clientconfig.partner.microsoftonline-p.net.cn**
    
    2. Click **添加** (add). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to the [SUNDNS website](http://www.sundns.com/login.php) and sign in. 
    
    ![Sign in to SUNDNS](../media/2e45a261-18c2-4244-817a-ca3eb9f8a369.png)
  
2. On the left navigation tree, under **我的业务** (my business), click **我的DNS** (my DNS). 
    
    ![Click "我的DNS"](../media/6ca2c8a9-6427-4f87-97d5-aadb2c217ee2.png)
  
3. In the right pane, in the **管理** (manage) column for the domain that you want to update, click **管理** (manage). 
    
    The DNS records page for your domain opens.
    
    ![Click "管理"](../media/bf345b18-d27f-40d9-bebc-f23559ec65ec.png)
  
4. In the **文本记录(TXT记录)** (TXT record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
    - **主机名** (host name): Leave the box blank. 
    
    - **文本内容** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/76d547b9-38a5-4eae-943a-e4fcf6f0f4b2.png)
  
5. Click **添加** (add). 
    


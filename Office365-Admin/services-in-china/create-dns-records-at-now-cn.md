---
title: "Create DNS records at Now.cn for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Now'
- 'O365M_DOM_Now'
- 'O365E_DOM_Now'
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
ms.assetid: f169e878-8362-4e42-9cb5-f9b26049f468
description: "Learn to setup your own DNS records at Now.cn for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at Now.cn for Office 365

> [!CAUTION]
> The Now.cn website doesn't support SRV records. which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, if you manage your DNS records at Now.cn, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at Now.cn, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.

    
After you add these records at Now.cn, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/d436861d-e28d-4f81-a51f-b33799234b11), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at Now.cn](http://www.now.cn/user/login.php?1&amp;page=%2Fdomain-admin%2Fdomain_list.php) and sign in. 
    
    ![Sign in to Now.cn](../media/7525bdbc-9624-4eb5-be0a-87fa9e3fb9d2.png)
  
2. In the **功能管理** (management) column for the domain that you want to update, click **VDNS 解析** (VDNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "VDNS 解析"](../media/32ce15a4-2764-4d1e-af54-b653d5ae95b3.png)
  
3. In the **Type** drop-down list, select **TXT**.
    
    ![Select "TXT"](../media/262f0e29-3dfb-4749-bd3a-8cb4a831a43a.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **Prior**: Use the default value.
    
  - **\*.\*.\*.\***: Paste **Destination or Points to Address** value rom the table in Office 365, for example MS=ms  *XXXXXXX*  . [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
5. Click **Add Subdomain**.
    
6. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
    ![Add TXT record](../media/493bc4c7-c870-445e-9f6d-addb636448a7.png)
  
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

1. In your browser, go to [your domains list at Now.cn](http://www.now.cn/user/login.php?1&amp;page=%2Fdomain-admin%2Fdomain_list.php) and sign in. 
    
    ![Sign in to Now.cn](../media/7525bdbc-9624-4eb5-be0a-87fa9e3fb9d2.png)
  
2. In the **功能管理** (management) column for the domain that you want to update, click **VDNS 解析** (VDNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "VDNS 解析"](../media/32ce15a4-2764-4d1e-af54-b653d5ae95b3.png)
  
3. In the **Type** drop-down list, select **MX**.
    
    ![Select "MX"](../media/6b796c44-f6ce-4222-aab4-fd2163ff2729.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **sub domain**: Leave the box blank.
    
  - **Prior**: **0**
    
  - **\*.\*.\*.\***: Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
    ![Add MX record](../media/ab841ce7-041b-4cef-afd4-f4574e8168c8.png)
  
5. Click **Add Subdomain**.
    
6. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
7. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
  - On the row of the obsolete record, click **DELETE**.
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to [your domains list at Now.cn](http://www.now.cn/user/login.php?1&amp;page=%2Fdomain-admin%2Fdomain_list.php) and sign in. 
    
        ![Sign in to Now.cn](../media/7525bdbc-9624-4eb5-be0a-87fa9e3fb9d2.png)
  
    2. In the **功能管理** (management) column for the domain that you want to update, click **VDNS 解析** (VDNS management). 
    
        The DNS records page for your domain opens.
    
        ![Click "VDNS 解析"](../media/32ce15a4-2764-4d1e-af54-b653d5ae95b3.png)
  
    3. On the DNS records page for your domain, in the **Type** drop-down list, select **CNAME**.
    
    ![Select "CNAME"](../media/8901d098-1cbd-4427-8bde-10d7d1ec6332.png)
  
    4. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **sub domain**: **autodiscover**
    
        - **\*.\*.\*.\***: **autodiscover.partner.outlook.cn**
    
    5. Click **Add Subdomain**.
    
    6. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
    ![Add CNAME record](../media/08a5e988-19c0-47c5-8413-06543239287a.png)
  
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **Type** drop-down list, select **CNAME**.
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **sub domain**: **lyncdiscover**
    
        - **\*.\*.\*.\***: **webdir.online.partner.lync.cn**
    
    3. Click **Add Subdomain**.
    
    4. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **Type** drop-down list, select **CNAME**.
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **sub domain**: **sip**
    
        - **\*.\*.\*.\***: **sipdir.online.partner.lync.cn**
    
    3. Click **Add Subdomain**.
    
    4. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **Type** drop-down list, select **CNAME**.
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **sub domain**: **msoid**
    
        - **\*.\*.\*.\***: **clientconfig.partner.microsoftonline-p.net.cn**
    
    3. Click **Add Subdomain**.
    
    4. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [your domains list at Now.cn](http://www.now.cn/user/login.php?1&amp;page=%2Fdomain-admin%2Fdomain_list.php) and sign in. 
    
    ![Sign in to Now.cn](../media/7525bdbc-9624-4eb5-be0a-87fa9e3fb9d2.png)
  
2. In the **功能管理** (management) column for the domain that you want to update, click **VDNS 解析** (VDNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "VDNS 解析"](../media/32ce15a4-2764-4d1e-af54-b653d5ae95b3.png)
  
3. In the **Type** drop-down list, select **TXT**.
    
    ![Select "TXT"](../media/262f0e29-3dfb-4749-bd3a-8cb4a831a43a.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **Prior**: Use the default value.
    
  - **\*.\*.\*.\***: **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/493bc4c7-c870-445e-9f6d-addb636448a7.png)
  
5. Click **Add Subdomain**.
    
6. Click **Restart VDNS** for the changes to take effect across the Internet. 
    


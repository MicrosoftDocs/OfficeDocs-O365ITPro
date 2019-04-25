---
title: "Create DNS records at ZGSJ for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_ZGSJ'
- 'O365M_DOM_ZGSJ'
- 'O365E_DOM_ZGSJ'
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
ms.assetid: df5380a5-1b61-4650-8a9a-51e1d712869c
description: "Learn to setup your own DNS records at ZGSJ for Office 365 operated by 21Vianet in China."
monikerRange: 'o365-21vianet'
---

# Create DNS records at ZGSJ for Office 365

> [!CAUTION]
> The zgsj website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [service limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If despite the service limitations, you choose to manage your own Office 365 DNS records at zgsj, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
    
After you add these records at zgsj, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/949e3cd9-86c6-4cd5-b5d4-607bc0d6fffb), like www. *your_domain*.com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [zgsj website](http://www.zgsj.com) and sign in. 
    
    ![Sign in to zgsj](../media/25f81db6-5dd4-4895-817a-5ff33ddc394d.png)
  
2. In the left pane, in the **产品管理** (product management) section, click **域名管理** (domain management). 
    
    ![Click "域名管理"](../media/0934df0b-1dc5-4560-9d8e-ac18df6c55e2.png)
  
3. In the right pane, in the **控制面板** (control panel) column for the domain that you want to update, click **登录解析**(sign in).
    
    ![Click "登录解析"](../media/c184cca7-145d-4052-9922-a69387129813.png)
  
4. In the control panel for your domain, in the left pane, click **DNS解析管理** (DNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/fff3ce9f-1b40-4ae9-80e6-0208121226b2.png)
  
5. In the right pane, click **增加TXT** (add a TXT record). 
    
    ![Click "增加TXT"](../media/9ac6b204-a5d9-48ac-ba11-82c1dee9620a.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **智能DNS** (network): Use the default value. 
    
  - **主机名** (host name): Leave the box blank. 
    
  - **值** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Add TXT record](../media/94520f94-5625-48e7-816e-34873243a0cc.png)
  
7. Click **增加** (add). 
    
8. In the confirmation dialog box, click **OK**.
    
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

1. In your browser, go to the [zgsj website](http://www.zgsj.com) and sign in. 
    
    ![Sign in to zgsj](../media/25f81db6-5dd4-4895-817a-5ff33ddc394d.png)
  
2. In the left pane, in the **产品管理** (product management) section, click **域名管理** (domain management). 
    
    ![Click "域名管理"](../media/0934df0b-1dc5-4560-9d8e-ac18df6c55e2.png)
  
3. In the right pane, in the **控制面板** (control panel) column for the domain that you want to update, click **登录解析**(sign in).
    
    ![Click "登录解析"](../media/c184cca7-145d-4052-9922-a69387129813.png)
  
4. In the control panel for your domain, in the left pane, click **DNS解析管理** (DNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/fff3ce9f-1b40-4ae9-80e6-0208121226b2.png)
  
5. In the right pane, click **增加邮件** (add an MX record). 
    
    ![Click "增加邮件'](../media/528a95db-f3f1-4e32-ae42-743b999f7731.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **智能DNS** (network): Use the default value. 
    
  - **主机名** (host name): Leave the box blank. 
    
  - **优先级** (priority): **0**
    
  - **邮件主机** (mail host): Paste the **Points to address** from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn. This value must end with a period (.). 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
    ![Add MX record](../media/9223a381-fbbe-4326-88fd-af29e5cb5d67.png)
  
7. Click **增加** (add). 
    
8. In the confirmation dialog box, click **OK**.
    
9. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. On the row of the obsolete record, click the **删除** (remove) icon. 
    
    2. In the confirmation dialog box, click **OK**.
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to the [zgsj website](http://www.zgsj.com) and sign in. 
    
        ![Sign in to zgsj](../media/25f81db6-5dd4-4895-817a-5ff33ddc394d.png)
  
    2. In the left pane, in the **产品管理** (product management) section, click **域名管理** (domain management). 
    
        ![Click "域名管理"](../media/0934df0b-1dc5-4560-9d8e-ac18df6c55e2.png)
  
    3. In the right pane, in the **控制面板** (control panel) column for the domain that you want to update, click **登录解析**(sign in).
    
        ![Click "登录解析"](../media/c184cca7-145d-4052-9922-a69387129813.png)
  
    4. In the control panel for your domain, in the left pane, click **DNS解析管理** (DNS management). 
    
        The DNS records page for your domain opens.
    
        ![Click "DNS解析管理"](../media/fff3ce9f-1b40-4ae9-80e6-0208121226b2.png)
  
    5. On the DNS records page for your domain, in the right pane, click **增加别名** (add a CNAME record). 
    
        ![Click "增加别名"](../media/766b023c-0a7e-4e27-8bf4-d6952c12a7a1.png)
  
    6. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **智能DNS** (network): Use the default value. 
    
        - **主机名** (host name): **autodiscover**
    
        - **指向到** (points to): **autodiscover.partner.outlook.cn**
    
    ![Add CNAME record](../media/ebcb3e22-31a6-4b1c-a74f-a0cbb8f32683.png)
  
    7. Click **增加** (add). 
    
    8. In the confirmation dialog box, click **OK**.
    
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the right pane, click **增加别名** (add a CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **智能DNS** (network): Use the default value. 
    
        - **主机名** (host name): **lyncdiscover**
    
        - **指向到** (points to): **webdir.online.partner.lync.cn**
    
    3. Click **增加** (add). 
    
    4. In the confirmation dialog box, click **OK**.
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the right pane, click **增加别名** (add a CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **智能DNS** (network): Use the default value. 
    
        - **主机名** (host name): **sip**
    
        - **指向到** (points to): **sipdir.online.partner.lync.cn**
    
    3. Click **增加** (add). 
    
    4. In the confirmation dialog box, click **OK**.
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the right pane, click **增加别名** (add a CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **智能DNS** (network): Use the default value. 
    
        - **主机名** (host name): **msoid**
    
        - **指向到** (points to): **clientconfig.partner.microsoftonline-p.net.cn**
    
    3. Click **增加** (add). 
    
    4. In the confirmation dialog box, click **OK**.
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to the [zgsj website](http://www.zgsj.com) and sign in. 
    
    ![Sign in to zgsj](../media/25f81db6-5dd4-4895-817a-5ff33ddc394d.png)
  
2. In the left pane, in the **产品管理** (product management) section, click **域名管理** (domain management). 
    
    ![Click "域名管理"](../media/0934df0b-1dc5-4560-9d8e-ac18df6c55e2.png)
  
3. In the right pane, in the **控制面板** (control panel) column for the domain that you want to update, click **登录解析**(sign in).
    
    ![Click "登录解析"](../media/c184cca7-145d-4052-9922-a69387129813.png)
  
4. In the control panel for your domain, in the left pane, click **DNS解析管理** (DNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/fff3ce9f-1b40-4ae9-80e6-0208121226b2.png)
  
5. In the right pane, click **增加TXT** (add a TXT record). 
    
    ![Click "增加TXT"](../media/9ac6b204-a5d9-48ac-ba11-82c1dee9620a.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **智能DNS** (network): Use the default value. 
    
  - **主机名** (host name): Leave the box blank. 
    
  - **值** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/94520f94-5625-48e7-816e-34873243a0cc.png)
  
7. Click **增加** (add). 
    
8. In the confirmation dialog box, click **OK**.
    


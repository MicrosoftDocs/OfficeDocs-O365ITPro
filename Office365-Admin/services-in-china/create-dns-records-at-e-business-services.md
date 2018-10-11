---
title: "Create DNS records at E-business Services for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_EBus'
- 'O365M_DOM_EBus'
- 'O365E_DOM_EBus'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 02969edd-320f-48d8-9933-2770a71f4b89
description: "Learn to setup your own DNS records at E-business Services for Office 365 operated by 21Vianet in China."
---

# Create DNS records at E-business Services for Office 365

> [!CAUTION]
> The E-business Services website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [limitations](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If, despite the service limitations, you choose to manage your own Office 365 DNS records at E-business Services, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-e-business-services.md#BKMK_verify_domain)
    
- [Add an MX record to route email](create-dns-records-at-e-business-services.md#BKMK_add_MX)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-e-business-services.md#BKMK_add_CNAME)
    
- [Add a TXT record to help prevent spam](create-dns-records-at-e-business-services.md#BKMK_add_TXT)
    
After you add these records at E-business Services, your domain will be set up to work with Office 365 Service, though not with the Lync Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/26bc0b35-6fee-44b6-9b55-df974ae63ed0), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [E-business Services domain control panel](https://www.eb.com.cn/) and sign in with your domain name and password. 
    
    ![Sign in to domain control panel](../media/1095c6f1-a37f-40b7-bedb-674f3378cd57.png)
  
2. Click **DNS解析管理** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/2e7f43fc-12bc-48e8-80eb-3d6524ab3251.png)
  
3. In the **高级解析** (advanced DNS settings) section, click **文本记录(TXT记录)** (TXT record). 
    
    ![Click "文本记录(TXT记录)"](../media/5a473b8a-7b49-46d3-b8e6-b67b34364244.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **内容** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX* . [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Add TXT record](../media/2570ded3-e7e4-4456-b425-a31d859fbe14.png)
  
5. Click **增加** (add). 
    
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

1. In your browser, go to [E-business Services domain control panel](https://www.eb.com.cn/) and sign in with your domain name and password. 
    
    ![Sign in to domain control panel](../media/1095c6f1-a37f-40b7-bedb-674f3378cd57.png)
  
2. Click **DNS解析管理** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/2e7f43fc-12bc-48e8-80eb-3d6524ab3251.png)
  
3. In the **高级解析** (advanced DNS settings) section, click **邮件交换记录(MX记录)** (MX record). 
    
    ![Click "邮件交换记录(MX记录)"](../media/207c5845-ae2d-4b2e-865c-d36078bafa5e.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **对应MAIL主机名** (points to): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. [How do I find this?](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **优先级** (priority): **0**
    
    ![Add MX record](../media/60d236b6-061d-4488-a286-846eb1904653.png)
  
5. Click **增加** (add). 
    
6. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
    1. In the **高级解析** (advanced DNS settings) section, click **邮件交换记录(MX记录)** (MX record). 
    
    2. On the row of the obsolete record, click **删除** (remove). 
    
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
    1. In your browser, go to [E-business Services domain control panel](https://www.eb.com.cn/) and sign in with your domain name and password. 
    
        ![Sign in to domain control panel](../media/1095c6f1-a37f-40b7-bedb-674f3378cd57.png)
  
    2. Click **DNS解析管理** (DNS record management). 
    
        The DNS records page for your domain opens.
    
        ![Click "DNS解析管理"](../media/2e7f43fc-12bc-48e8-80eb-3d6524ab3251.png)
  
    3. On the DNS records page for your domain, in the **高级解析** (advanced DNS settings) section, click **别名记录(CNAME)** (CNAME record). 
    
        ![Click "别名记录(CNAME)"](../media/d53fd235-073d-47fd-a17c-1babc7b1d5bc.png)
  
    4. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **autodiscover**
    
        - **对应主机** (points to): **autodiscover.partner.outlook.cn**
    
        ![Add CNAME record](../media/88bc84f7-7b26-4348-8deb-167b8a91c533.png)
  
    5. Click **增加** (add). 
    
2. Add the Lync Autodiscover CNAME record.
    
    1. On the DNS records page for your domain, in the **高级解析** (advanced DNS settings) section, click **别名记录(CNAME)** (CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **lyncdiscover**
    
        - **对应主机** (points to): **webdir.online.partner.lync.cn**
    
    3. Click **增加** (add). 
    
3. Add the Lync SIP CNAME record.
    
    1. On the DNS records page for your domain, in the **高级解析** (advanced DNS settings) section, click **别名记录(CNAME)** (CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **sip**
    
        - **对应主机** (points to): **sipdir.online.partner.lync.cn**
    
    3. Click **增加** (add). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
    1. On the DNS records page for your domain, in the **高级解析** (advanced DNS settings) section, click **别名记录(CNAME)** (CNAME record). 
    
    2. Make sure that the fields are set to precisely the following values for the empty record:
    
        - **主机名** (host name): **msoid**
    
        - **对应主机** (points to): **clientconfig.partner.microsoftonline-p.net.cn**
    
    3. Click **增加** (add). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [E-business Services domain control panel](https://www.eb.com.cn/) and sign in with your domain name and password. 
    
    ![Sign in to domain control panel](../media/1095c6f1-a37f-40b7-bedb-674f3378cd57.png)
  
2. Click **DNS解析管理** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/2e7f43fc-12bc-48e8-80eb-3d6524ab3251.png)
  
3. In the **高级解析** (advanced DNS settings) section, click **文本记录(TXT记录)** (TXT record). 
    
    ![Click "文本记录(TXT记录)"](../media/5a473b8a-7b49-46d3-b8e6-b67b34364244.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
      - **主机名** (host name): Leave the box blank. 
    
      - **内容** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/2570ded3-e7e4-4456-b425-a31d859fbe14.png)
  
5. Click **增加** (add). 
    


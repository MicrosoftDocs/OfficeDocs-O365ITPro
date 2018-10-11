---
title: "Create DNS records at DNSPod for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DNSPod'
- 'O365M_DOM_DNSPod'
- 'O365E_DOM_DNSPod'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 1ee3e051-20fc-4258-936c-3a45f654f703
description: "Learn to setup your own DNS records at DNSPod for Office 365 operated by 21Vianet in China."
---

# Create DNS records at DNSPod for Office 365

If DNSPod is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-dnspod.md#BKMK_verify_domain)
    
- [Add MX record](create-dns-records-at-dnspod.md#BKMK_add_MX)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-dnspod.md#BKMK_add_CNAME)
    
- [Add a TXT record to help prevent spam](create-dns-records-at-dnspod.md#BKMK_add_TXT)
    
- [Add SRV records](create-dns-records-at-dnspod.md#BKMK_add_SRV)
    
After you add these records at DNSPod, your domain will be set up to work with Office 365 services.
  
If you have a SharePoint Online Public Website, you can [Add records at DNSPod to set up your SharePoint Online Public Website](https://support.office.com/article/6ead13cd-3e47-44ca-a7fa-a60436cc597b), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. Click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **@**
    
  - ** 记录类型 ** (record type): **TXT**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*  . [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/c9a54892-c7f9-400b-b49a-631854077365.png)
  
5. Click **保存** (save). 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
## Add MX record
<a name="BKMK_add_MX"> </a>

1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. Click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **@**
    
  - ** 记录类型 ** (record type): **MX**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. 
  
[Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **MX优先级** (MX priority): **1**
    
  - **TTL**: **3600**
    
    ![Add MX record](../media/8b87ce1c-e3f0-4ab9-bdb4-8f9c86104521.png)
  
5. Click **保存** (save). 
    
6. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
1. On the row of the obsolete record, click **删除** (remove). 
    
2. In the confirmation dialog box, click **确定** (OK). 
    
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. Add the email (Exchange) Autodiscover CNAME record.
    
1. On the DNS records page for your domain, click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **autodiscover**
    
  - ** 记录类型 ** (record type): **CNAME**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **autodiscover.partner.outlook.cn**
    
  - **TTL**: **3600**
    
    ![Add CNAME record](../media/22c6d668-d4f8-47de-9e0c-9c2076551d5c.png)
  
3. Click **保存** (save). 
    
4. Add the Lync Autodiscover CNAME record.
    
1. On the DNS records page for your domain, click **添加记录** (add a DNS record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **lyncdiscover**
    
  - ** 记录类型 ** (record type): **CNAME**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **webdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    
5. Add the Lync SIP CNAME record.
    
1. On the DNS records page for your domain, click **添加记录** (add a DNS record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **sip**
    
  - ** 记录类型 ** (record type): **CNAME**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **sipdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
1. On the DNS records page for your domain, click **添加记录** (add a DNS record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **msoid**
    
  - ** 记录类型 ** (record type): **CNAME**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **clientconfig.partner.microsoftonline-p.net.cn**
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. Click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **@**
    
  - ** 记录类型 ** (record type): **TXT**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/c9a54892-c7f9-400b-b49a-631854077365.png)
  
5. Click **保存** (save). 
    
## Add SRV records
<a name="BKMK_add_SRV"> </a>

1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. Add the SIP SRV record for Lync federation.
    
1. On the DNS records page for your domain, click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **_sipfederationtls._tcp**
    
  - ** 记录类型 ** (record type): **CNAME**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **100 1 5061 sipfed.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
    ![Add SRV record](../media/51ea67b3-0978-4016-8f84-c5bfae17eb0e.png)
  
3. Click **保存** (save). 
    
4. Add the SIP SRV record for Lync web conferencing.
    
1. On the DNS records page for your domain, click **添加记录** (add a DNS record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **_sip._tls**
    
  - ** 记录类型 ** (record type): **CNAME**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): **100 1 443 sipdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
3. Click **保存** (save). 
    


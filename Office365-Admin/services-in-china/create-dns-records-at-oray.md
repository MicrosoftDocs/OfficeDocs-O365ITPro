---
title: "Create DNS records at Oray for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Oray'
- 'O365M_DOM_Oray'
- 'O365E_DOM_Oray'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: bc8e0427-72ea-4d98-9f13-3ea98edc5972
description: "Learn to setup your own DNS records at Oray for Office 365 operated by 21Vianet in China."
---

# Create DNS records at Oray for Office 365

If Oray is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-oray.md#BKMK_verify_domain)
    
- [Add MX record](create-dns-records-at-oray.md#BKMK_add_MX)
    
- [Add CNAME records](create-dns-records-at-oray.md#BKMK_add_CNAME)
    
- [Add a TXT record to help with spam prevention](create-dns-records-at-oray.md#BKMK_add_TXT)
    
- [Add SRV records](create-dns-records-at-oray.md#BKMK_add_SRV)
    
After you add these records at Oray, your domain will be set up to work with Office 365 services.
  
If you have a SharePoint Online Public Website, you can [Add records at Oray to set up your SharePoint Online Public Website](https://support.office.com/article/5815d187-c312-49b4-8d8b-f37bd90a68aa), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at Oray](https://console.oray.com/domain/root) and sign in. 
    
    ![Sign in to Oray](../media/b55798c7-e143-454f-a3d3-7fd8733cba46.png)
  
2. In the right pane, in the **解析设置** (DNS record management) column for the domain that you want to update, click **DNS解析设置** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析设置"](../media/90257c23-ac07-4fab-83e7-7ae96693f667.png)
  
3. In the **域名解析设置** (DNS record management) list, click the **@** subdomain name. 
    
    ![Click "@'](../media/4deba23f-034c-42dc-8cae-29009e6229d9.png)
  
4. Click the **TXT记录** (TXT record) tab. 
    
    ![Click "TXT记录"](../media/85379c31-da07-4dc5-ac4e-0e6cb9a99957.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **说明** (value): Paste **Destination or Points to Address** value from the table in Office 365, for example MS=ms  *XXXXXXX*  . [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/5681f501-bccd-4b3d-8e5b-55272b01b833.png)
  
6. Click **增加** (add). 
    
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

1. In your browser, go to [your domains list at Oray](https://console.oray.com/domain/root) and sign in. 
    
    ![Sign in to Oray](../media/b55798c7-e143-454f-a3d3-7fd8733cba46.png)
  
2. In the right pane, in the **解析设置** (DNS record management) column for the domain that you want to update, click **DNS解析设置** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析设置"](../media/90257c23-ac07-4fab-83e7-7ae96693f667.png)
  
3. In the **域名解析设置** (DNS record management) list, click the **@** subdomain name. 
    
    ![Click "@'](../media/4deba23f-034c-42dc-8cae-29009e6229d9.png)
  
4. Click the **MX记录** (MX record) tab. 
    
    ![Click "MX记录"](../media/e350e329-78d0-427b-8b22-8fd510e53ccd.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **邮件服务器** (mail server): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. 
  
[Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **优先级** (priority): **0**
    
  - **TTL**: **3600**
    
    ![Add MX record](../media/1f231529-b209-4602-b817-bce4713d72dc.png)
  
6. Click **增加** (add). 
    
7. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
1. Click the **MX记录** (MX record) tab. 
    
2. On the row of the obsolete record, click **删除** (remove). 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
1. In your browser, go to [your domains list at Oray](https://console.oray.com/domain/root) and sign in. 
    
    ![Sign in to Oray](../media/b55798c7-e143-454f-a3d3-7fd8733cba46.png)
  
2. In the right pane, in the **解析设置** (DNS record management) column for the domain that you want to update, click **DNS解析设置** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析设置"](../media/90257c23-ac07-4fab-83e7-7ae96693f667.png)
  
3. On the DNS records page for your domain, in the **无需带域名根** (subdomain name) box, type **autodiscover**, and then click **增加子域名** (add subdomain). 
    
4. Click the newly added subdomain name **autodiscover**.
    
    ![Add subdomain name](../media/c810c388-131a-4019-bac5-db9730d92d92.png)
  
5. Click the **CNAME** tab. 
    
    ![Click "CNAME"](../media/438c1a64-b28d-46f4-a1d5-46d7e7a33eed.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **CName (别名)**: **autodiscover.partner.outlook.cn**
    
  - **TTL**: **3600**
    
    ![Add CNAME record](../media/9e09e3b3-104c-4a1a-b6f2-c72edfe8cdb8.png)
  
7. Click **保存** (save). 
    
2. Add the Lync Autodiscover CNAME record.
    
1. On the DNS records page for your domain, in the **无需带域名根** (subdomain name) box, type **lyncdiscover**, and then click **增加子域名** (add subdomain). 
    
2. Click the newly added subdomain name **lyncdiscover**.
    
3. Click the **CNAME** tab. 
    
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **CName (别名)**: **webdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
5. Click **保存** (save). 
    
3. Add the Lync SIP CNAME record.
    
1. On the DNS records page for your domain, in the **无需带域名根** (subdomain name) box, type **sip**, and then click **增加子域名** (add subdomain). 
    
2. Click the newly added subdomain name **sip**.
    
3. Click the **CNAME** tab. 
    
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **CName (别名)**: **sipdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
5. Click **保存** (save). 
    
4. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
1. On the DNS records page for your domain, in the **无需带域名根** (subdomain name) box, type **msoid**, and then click **增加子域名** (add subdomain). 
    
2. Click the newly added subdomain name **msoid**.
    
3. Click the **CNAME** tab. 
    
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **CName (别名)**: **clientconfig.partner.microsoftonline-p.net.cn**
    
  - **TTL**: **3600**
    
5. Click **保存** (save). 
    
## Add a TXT record to help with spam prevention
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [your domains list at Oray](https://console.oray.com/domain/root) and sign in. 
    
    ![Sign in to Oray](../media/b55798c7-e143-454f-a3d3-7fd8733cba46.png)
  
2. In the right pane, in the **解析设置** (DNS record management) column for the domain that you want to update, click **DNS解析设置** (DNS record management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析设置"](../media/90257c23-ac07-4fab-83e7-7ae96693f667.png)
  
3. In the **域名解析设置** (DNS record management) list, click the **@** subdomain name. 
    
    ![Click "@'](../media/4deba23f-034c-42dc-8cae-29009e6229d9.png)
  
4. Click the **TXT记录** (TXT record) tab. 
    
    ![Click "TXT记录"](../media/85379c31-da07-4dc5-ac4e-0e6cb9a99957.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **说明** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **TTL**: **3600**
    
6. Click **增加** (add). 
    
    ![Add TXT record](../media/5681f501-bccd-4b3d-8e5b-55272b01b833.png)
  
## Add SRV records
<a name="BKMK_add_SRV"> </a>

> [!NOTE]
> Currently you can't add the SRV records for Office 365 due to the Oray website's restrictions on subdomain character types. To add the SRV records, contact the Oray support team at 800@oray.com and ask them to create the SRV records for you according to the following information. 
  
1. Add the SIP SRV record for Lync federation.
    
1. On the DNS records page for your domain, in the **无需带域名根** (subdomain name) box, type **_sipfederationtls._tcp**, and then click **增加子域名** (add subdomain). 
    
    ![Add subdomain name](../media/c810c388-131a-4019-bac5-db9730d92d92.png)
  
2. Click the newly added subdomain name **_sipfederationtls._tcp**.
    
    ![Click "SRV记录"](../media/3368ba28-e99c-4c8f-a335-4658ed52b86b.png)
  
3. Click the **SRV记录** (SRV record) tab. 
    
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): **sipfed.online.partner.lync.cn**
    
  - **优先** (priority): **100**
    
  - **权重** (weight): **1**
    
  - **端口** (port)): **5061**
    
  - **TTL**: **3600**
    
    ![Add SRV record](../media/28719253-7f0e-4837-ab04-f27f41e6b157.png)
  
5. Click **增加** (add). 
    
2. Add the SIP SRV record for Lync web conferencing.
    
1. On the DNS records page for your domain, in the **无需带域名根** (subdomain name) box, type **_sip._tls**, and then click **增加子域名** (add subdomain). 
    
2. Click the newly added subdomain name **_sip._tls**.
    
3. Click the **SRV记录** (SRV record) tab. 
    
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): **sipdir.online.partner.lync.cn**
    
  - **优先** (priority): **100**
    
  - **权重** (weight): **1**
    
  - **端口** (port)): **443**
    
  - **TTL**: **3600**
    
5. Click **增加** (add). 
    


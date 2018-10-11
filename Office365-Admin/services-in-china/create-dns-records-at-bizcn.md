---
title: "Create DNS records at BIZCN for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_BIZCN'
- 'O365M_DOM_BIZCN'
- 'O365E_DOM_BIZCN'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: fcc15118-0d19-4517-a315-ffabc9a0290a
description: "Learn to setup your own DNS records at BIZCN for Office 365 operated by 21Vianet in China."
---

# Create DNS records at BIZCN for Office 365

If BIZCN is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-bizcn.md#BKMK_verify_domain)
    
- [Add an MX record to route email](create-dns-records-at-bizcn.md#BKMK_add_MX)
    
- [Add CNAME records](create-dns-records-at-bizcn.md#BKMK_add_CNAME)
    
- [Add a TXT record to help prevent spam](create-dns-records-at-bizcn.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-bizcn.md#BKMK_add_SRV)
    
After you add these records at BIZCN, your domain will be set up to work with Office 365 services.
  
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain for the website URL address](https://support.office.com/article/b3d443c9-f520-4e72-9e37-2ced53ae1a58), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Click **增加TXT记录** (add a TXT record). 
    
    ![Click "增加邮件"](../media/4ff4d29d-db86-48de-af17-43c306c56a86.png)
  
7. In the boxes for the new record, type or copy and paste the following values:
    
  - **主机名** (host name): **@**
    
  - **字符串记录** (value): Paste the **Destination or Points to Address** from the table in Office 365, for example MS=ms  *XXXXXXX*  . [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
    ![Add MX record](../media/664358f5-edd8-4113-b4ca-e45b32f6cf95.png)
  
8. Click **增加** (add). 
    
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

Add an MX record so email for your domain will come to Office 365.
  
1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Click **增加邮件** (add an MX record). 
    
7. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): **@**
    
  - **优先级** (priority): **0**
    
    For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)
    
  - **对应MAIL主机名** (points to): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. 
  
[Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **TTL**: Use the default value.
    
8. Click **增加** (add). 
    
If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
  
1. On the DNS records page for your domain, find the obsolete record.
    
2. In the **删除** (remove) column for the record, click the **删除** (remove) button. 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

Add the CNAME records that are required for Office 365. If additional CNAME records are listed in Office 365, add those following the same general steps shown here. .
  
1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Add the email (Exchange) Autodiscover CNAME record.
    
1. On the DNS records page for your domain, click **增加别名** (add a CNAME record). 
    
    ![Click "增加别名"](../media/b122a9e7-f6b2-4123-b91f-242dd80fdd30.png)
  
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **别名** (alias): **autodiscover**
    
  - **对应主机名** (points to): **autodiscover.partner.outlook.cn**
    
7. ![Add CNAME record](../media/a11316b1-f56d-4412-bb68-7fb7271bd8a5.png)
  
8. Click **增加** (add). 
    
9. Add the Lync Autodiscover CNAME record.
    
1. On the DNS records page for your domain, click **增加别名** (add a CNAME record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **别名** (alias): **lyncdiscover**
    
  - **对应主机名** (points to): **webdir.online.partner.lync.cn**
    
3. Click **增加** (add). 
    
10. Add the Lync SIP CNAME record.
    
1. On the DNS records page for your domain, click **增加别名** (add a CNAME record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **别名** (alias): **sip**
    
  - **对应主机名** (points to): **sipdir.online.partner.lync.cn**
    
3. Click **增加** (add). 
    
11. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
1. On the DNS records page for your domain, click **增加别名** (add a CNAME record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **别名** (alias): **msoid**
    
  - **对应主机名** (points to): **clientconfig.partner.microsoftonline-p.net.cn**
    
3. Click **增加** (add). 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Click **增加TXT记录** (add a TXT record). 
    
    ![Click "增加TXT记录"](../media/2d797e07-dff8-46ee-b63d-48680c18e18b.png)
  
7. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): **@**
    
  - **字符串记录** (value): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
    ![Add TXT record](../media/5999218d-4d02-41ea-b0df-ab5f7059f0e3.png)
  
8. Click **增加** (add). 
    
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Add the SIP SRV record for Lync federation.
    
1. On the DNS records page for your domain, click **增加SRV记录** (add a CNAME record). 
    
    ![Select "增加SRV记录"](../media/df86cf80-0362-4fb2-ad6d-5a16e1d44974.png)
  
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **服务** (service): **sipfederationtls**
    
  - **协议** (protocol): **TCP**
    
  - **优先级** (priority): **99**
    
  - **权重** (weight): **1**
    
  - **端口** (port): **5061**
    
  - **对应的主机名** (target): **sipfed.online.partner.lync.cn**
    
    ![Add SRV record](../media/2486f17e-8ffb-45bb-9804-2a6d85d861f7.png)
  
3. Click **增加** (add). 
    
7. Add the SIP SRV record for Lync web conferencing.
    
1. On the DNS records page for your domain, click **增加SRV记录** (add a CNAME record). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **服务** (service): **sip**
    
  - **协议** (protocol): **TLS**
    
  - **优先级** (priority): **99**
    
  - **权重** (weight): **1**
    
  - **端口** (port): **443**
    
  - **对应的主机名** (target): **sipdir.online.partner.lync.cn**
    
3. Click **增加** (add). 
    


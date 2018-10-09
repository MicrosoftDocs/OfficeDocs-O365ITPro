---
title: "Create DNS records at IDC1 for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_IDC'
- 'O365M_DOM_IDC'
- 'O365E_DOM_IDC'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: f4e5581e-9ae2-488a-9c2e-911028c4a177
description: "Learn to setup your own DNS records at IDC1 Services for Office 365 operated by 21Vianet in China."
---

# Create DNS records at IDC1 for Office 365

> [!CAUTION]
> The IDC1 website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 operated by 21Vianet plan you use, there are significant [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77), and you may want to switch to a different DNS hosting provider. 
  
If despite the service limitations, you choose to manage your own Office 365 DNS records at IDC1, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-idc1.md#BKMK_verify_domain)
    
- [Add an MX record to route email](create-dns-records-at-idc1.md#BKMK_add_MX)
    
- [Add CNAME records](create-dns-records-at-idc1.md#BKMK_add_CNAME)
    
- [Add a TXT record to help prevent spam](create-dns-records-at-idc1.md#BKMK_add_TXT)
    
After you add these records at IDC1, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App features mentioned above.
  
If you have a SharePoint Online Public Website, you can [Add records at IDC1 to set up your SharePoint Online Public Website](https://support.office.com/article/5fe093d7-7511-4af5-895a-b7aac802fc51), like www. *your_domain*  .com. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. 
  
## Add a TXT record for verification
<a name="BKMK_verify_domain"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [IDC1 DNS management system](http://edns.72dns.com/SuperDns/Login.aspx).
    
    ![Sign in to DNS management system](../media/8562d0bc-dde7-4fdb-b4dc-78f57fa159b8.png)
  
2. In the **域名** (domain name) box, type the name of the domain that you want to update. 
    
3. In the **管理密码** (administration password) box, type the administration password for your domain name. 
    
4. Click **登录** (sign in). 
    
    The DNS records page for your domain opens.
    
5. On the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **TXT 记录** (TXT record). 
    
    ![Add TXT record](../media/342ff242-c2c7-4d60-8421-5387e0b8d7a8.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): Leave the box blank. 
    
  - **域名** (points to domain): Paste **Destination or Points to Address** value **字符串记录** (value): Paste the **Destination or Points to Address** from the table in Office 365, for example MS=ms  *XXXXXXX*  . [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
    
  - **TTL**: **3600**
    
7. Click **增加** (add). 
    
8. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify button](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
## Add an MX record to route email
<a name="BKMK_add_MX"> </a>

1. In your browser, go to [IDC1 DNS management system](http://edns.72dns.com/SuperDns/Login.aspx).
    
    ![Sign in to DNS management system](../media/8562d0bc-dde7-4fdb-b4dc-78f57fa159b8.png)
  
2. In the **域名** (domain name) box, type the name of the domain that you want to update. 
    
3. In the **管理密码** (administration password) box, type the administration password for your domain name. 
    
4. Click **登录** (sign in). 
    
    The DNS records page for your domain opens.
    
5. On the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **MX 记录 (邮箱)** (MX record). 
    
    ![Add MX record](../media/45ae32cf-3865-4d72-869f-b30889f2f662.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): Leave the box blank. 
    
  - **邮箱服务器** (mailbox server): Paste the **Points to address** value from Office 365:  *\<domain-key\>*  .mail.protection.partner.outlook.cn 
    
    > [!NOTE]
    > Get your  *\<domain-key\>*  from your Office 365 portal account. 
  
[Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e)
  
  - **TTL**: **3600**
    
  - **优先级** (priority): **0**
    
7. Click **增加** (add). 
    
8. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
9. If you have any MX records for this domain that send email to someplace other than Office 365, remove them:
    
1. Click the **子域名列表** (subdomain list) tab. 
    
2. On the row of the obsolete record, click **删除** (remove). 
    
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

1. Add the email (Exchange) Autodiscover CNAME record.
    
1. In your browser, go to [IDC1 DNS management system](http://edns.72dns.com/SuperDns/Login.aspx).
    
    ![Sign in to DNS management system](../media/8562d0bc-dde7-4fdb-b4dc-78f57fa159b8.png)
  
2. In the **域名** (domain name) box, type the name of the domain that you want to update. 
    
3. In the **管理密码** (administration password) box, type the administration password for your domain name. 
    
4. Click **登录** (sign in). 
    
    The DNS records page for your domain opens.
    
5. On the DNS records page for your domain, on the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **CNAME/别名** (CNAME/alias). 
    
    ![Add CNAME record](../media/e9acdea8-7dc5-4032-b7be-f185506f8d06.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): **autodiscover**
    
  - **域名** (points to domain): **autodiscover.partner.outlook.cn**
    
  - **TTL**: **3600**
    
7. Click **增加** (add). 
    
8. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
2. Add the Lync Autodiscover CNAME record.
    
1. On the DNS records page for your domain, on the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **CNAME/别名** (CNAME/alias). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): **lyncdiscover**
    
  - **域名** (points to domain): **webdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
3. Click **增加** (add). 
    
4. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
5. Add the Lync SIP CNAME record.
    
1. On the DNS records page for your domain, on the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **CNAME/别名** (CNAME/alias). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): **sip**
    
  - **域名** (points to domain): **sipdir.online.partner.lync.cn**
    
  - **TTL**: **3600**
    
3. Click **增加** (add). 
    
4. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
3. Add the Office 365 MSOID CNAME record. This is an additional record that is required for Office 365.
    
1. On the DNS records page for your domain, on the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **CNAME/别名** (CNAME/alias). 
    
2. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): **msoid**
    
  - **域名** (points to domain): **clientconfig.partner.microsoftonline-p.net.cn**
    
  - **TTL**: **3600**
    
3. Click **增加** (add). 
    
4. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
## Add a TXT record to help prevent spam
<a name="BKMK_add_TXT"> </a>

1. In your browser, go to [IDC1 DNS management system](http://edns.72dns.com/SuperDns/Login.aspx).
    
    ![Sign in to DNS management system](../media/8562d0bc-dde7-4fdb-b4dc-78f57fa159b8.png)
  
2. In the **域名** (domain name) box, type the name of the domain that you want to update. 
    
3. In the **管理密码** (administration password) box, type the administration password for your domain name. 
    
4. Click **登录** (sign in). 
    
    The DNS records page for your domain opens.
    
5. On the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **TXT 记录** (TXT record). 
    
    ![Add TXT record](../media/342ff242-c2c7-4d60-8421-5387e0b8d7a8.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): Leave the box blank. 
    
  - **域名** (points to domain): **v=spf1 include:spf.protection.partner.outlook.cn -all**
    
  - **TTL**: **3600**
    
7. Click **增加** (add). 
    
8. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    


---
title: "Create DNS records at Net4.in for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 4/23/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Net4'
- 'O365M_DOM_Net4'
- 'O365E_DOM_Net4'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 42d002c2-cf25-42bc-ad14-7122abd4575b

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Net4.in for Office 365."
---

# Create DNS records at Net4.in for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Net4.in is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-net4-in.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-net4-in.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-net4-in.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-net4-in.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-net4-in.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-net4-in.md#BKMK_add_SRV)
    
After you add these records at Net4.in, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx ). You'll be prompted to log in.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **DNS** tab. 
    
    ![Choose the DNS tab](../media/a02534d9-8307-47fc-a368-a939007adf37.png)
  
5. In the boxes for the new record in the **DNS Records:  *domain_name* ** section, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    (Net4.in supplies the **Host** value automatically.) 
    
|**TTL**|**Type**|**Host**|**Data**|
|:-----|:-----|:-----|:-----|
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |TXT  <br/> |(This value is supplied automatically by server.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Enter DNS values](../media/38bf58d2-7371-452d-a3d2-ca43857eddd2.png)
  
6. Choose **Create**.
    
    ![Choose Create](../media/3574bcd0-ee5a-445a-b980-878f207bc3e3.png)
  
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify button](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx ). You'll be prompted to log in.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **DNS** tab. 
    
    ![Choose the DNS tab](../media/a02534d9-8307-47fc-a368-a939007adf37.png)
  
5. In the boxes for the new record in the **DNS Records:  *domain_name* ** section, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**TTL**|**Type**|**Data**|**Priority**|
|:-----|:-----|:-----|:-----|
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |MX  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![Enter the DNS values](../media/445bbaaa-200d-42af-9efe-1d50a12f1cb5.png)
  
6. Choose **Create**.
    
    ![Choose Create](../media/47e99d2f-8bd6-49b7-b8d7-84d1046f5344.png)
  
7. If there are any other MX records listed, delete each one by selecting the checkbox for that record.
    
    ![Select the check box to delete](../media/b2994aa7-2229-49b6-854e-3a060257b55f.png)
  
8. Choose **Multiple Delete**.
    
    ![Choose Multiple Delete](../media/df9b835d-095d-495d-86b9-2e1a5cfb84b2.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx ). You'll be prompted to log in.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **DNS** tab. 
    
    ![Choose the DNS tab](../media/a02534d9-8307-47fc-a368-a939007adf37.png)
  
5. Create the first of the six CNAME records.
    
    In the boxes for the new record in the **DNS Records :  *domain_name* ** section, type or copy and paste the values from the first row of the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**TTL**|**Type**|**Host**|**Data**|
|:-----|:-----|:-----|:-----|
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![Create the CNAME records](../media/488400a4-2057-4f99-af18-e28687c2547c.png)
  
6. Choose **Create**.
    
    ![Choose Create](../media/60380fa4-ae96-4913-a823-ae0676dd8ce4.png)
  
7. Create the other five CNAME records by using the same process and the values from the remaining five rows of the table.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx ). You'll be prompted to log in.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **DNS** tab. 
    
    ![Choose the DNS tab](../media/a02534d9-8307-47fc-a368-a939007adf37.png)
  
5. In the boxes for the new record in the **DNS Records:  *domain_name* ** section, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**TTL**|**Type**|**Host**|**Data**|
|:-----|:-----|:-----|:-----|
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |TXT  <br/> |(This value is supplied automatically by the server.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Enter the DNS values](../media/e3f2a35e-de0a-4720-936e-ccdf060be8e6.png)
  
6. Choose **Create**.
    
    ![Choose Create](../media/1ec2432f-7e43-4ef9-973a-a639e1d08669.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx ). You'll be prompted to log in.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **DNS** tab. 
    
    ![Choose the DNS tab](../media/a02534d9-8307-47fc-a368-a939007adf37.png)
  
5. Create the first of the two SRV records.
    
    In the boxes for the new record in the **DNS Records:  *domain_name* ** section, type or copy and paste the values from the first row of the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**TTL**|**Type**|**Host**|**Data**|
|:-----|:-----|:-----|:-----|
|3600(Once this value is set, it is automatically applied to all of the DNS records in the domain.)|SRV|sip._tls. **This value MUST end with a period (.)**(Add this value before the  *domain_name*  shown in the **Host** field. For example, _sip._tls.contoso.com.) |100 443 sipdir.online.lync.com 1> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
|3600(Once this value is set, it is automatically applied to all of the DNS records in the domain.)|SRV|_sipfederationtls._tcp. **This value MUST end with a period (.)**(Add this value before the  *domain_name*  shown in the **Host** field. For example, _sipfederationtls._tcp.contoso.com.) |100 5061 sipfed.online.lync.com 1> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Create SRV records](../media/c29cd6f1-e765-41eb-b3b0-b5969aeb5f63.png)
  
6. Choose **Create**.
    
    ![Choose Create](../media/a13e2e9e-2b71-4955-a5d3-ee23776347d4.png)
  
7. To add the other SRV record, choose **SRV** again, create a record using the values from the second row in the table, and then again choose **Create** to complete the record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Still need help?
<a name="BKMK_NeedHelp"> </a>

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


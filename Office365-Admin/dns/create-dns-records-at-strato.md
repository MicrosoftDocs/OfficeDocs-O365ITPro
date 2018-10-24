---
title: "Create DNS records at Strato for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8f31403f-92eb-4126-8145-dff92db5f3cb
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Strato for Office 365."
---

# Create DNS records at Strato for Office 365

[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If Strato.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. 
  
- [Add a TXT record for verification](#add-a-txt-record-for-verification)
    
- [Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Add the CNAME records that are required for Office 365](#add-the-cname-records-that-are-required-for-office-365)
    
- [Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
After you add these records at Strato.com, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](../setup/domains-faq.md).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="bkmk_txt"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select **Domains**.
    
    ![Strato_domains](../media/ae990bf2-6f98-4dd6-9aef-f65d2888091a.png)
  
3. Select **Domain management**.
    
    ![strato_domainManagement](../media/eced1360-f207-4b5e-bd61-848a70dc44a9.png)
  
4. On the **Domain management** page, next to the domain you want to manage, select **manage**.
    
    ![strato_manage](../media/2d9bd3ae-e4bc-459b-8539-206768b60a9b.png)
  
5. Under **Settings (domain)**, expand **DNS Settings**.
    
    ![strato_DNSsettings](../media/fb83450b-f638-4cd6-a844-5eab442424ae.png)
  
6. Next to **TXT records, including SPF and DKIM settings**, select **manage**
    
    ![strato_TXT_manage](../media/e0277f36-af91-45b9-8242-fcebbb5502c7.png)
  
7. In the boxes for the new record, type or copy and paste the following values.
    
    |**Prefix**|**Type**|**Value**|
    |:-----|:-----|:-----|
    |(leave blank)  <br/> |TXT  <br/> |MS=msXXXXXXX  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.   [How do I find this?](../get-help-with-domains/information-for-dns-records.md)  |
   
8. Select **Accept settings**.
    
    ![Strato_TXT_values_accept](../media/72828ff3-9a67-4de4-97fb-41b9eb43d909.png)
  
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="bkmk_mx"> </a>

1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select **Domains**.
    
    ![Strato_domains](../media/ae990bf2-6f98-4dd6-9aef-f65d2888091a.png)
  
3. Select **Domain management**.
    
    ![strato_domainManagement](../media/eced1360-f207-4b5e-bd61-848a70dc44a9.png)
  
4. On the **Domain management** page, next to the domain you want to manage, select **manage**.
    
    ![strato_manage](../media/2d9bd3ae-e4bc-459b-8539-206768b60a9b.png)
  
5. Under **Settings (domain)**, expand **DNS Settings**.
    
    ![strato_DNSsettings](../media/fb83450b-f638-4cd6-a844-5eab442424ae.png)
  
6. Next to **MX record**, choose **manage**
    
    ![Strato_MX_manage](../media/1fa1ffa4-fa98-4967-89ed-2896b689c2c4.png)
  
7. Next to **Primary mail server**, choose **Personal mail server**. In the **Address 1** box for the primary mail server, type or copy and paste the value from the following table. 
    
    > [!NOTE]
    > You must include a period at the end of the **Address 1** value. 
  
    |**Type**|**Priority**|**Address 1 (Points to address or value)**|
    |:-----|:-----|:-----|
    |MX  <br/> |high                    For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |\<domain-key\>.mail.protection.outlook.com.  <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 portal account.   [How do I find this?](../get-help-with-domains/information-for-dns-records.md)   |
   
    ![Strato_MX_manage](../media/4bae897e-95ca-43d3-b729-f216e32bbc93.png)
  
8. Select **Accept settings** to save the record. 
    
## Add the CNAME records that are required for Office 365
<a name="bkmk_cname"> </a>

You'll create the required CNAME records by creating the six subdomains first, and then updating each subdomain with its correct CNAME value. 
  
1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select **Domains**.
    
    ![Strato_domains](../media/ae990bf2-6f98-4dd6-9aef-f65d2888091a.png)
  
3. Select **Domain management**.
    
    ![strato_domainManagement](../media/eced1360-f207-4b5e-bd61-848a70dc44a9.png)
  
4. On the **Domain management** page, next to the domain you want to manage, select **manage**.
    
    ![strato_manage](../media/2d9bd3ae-e4bc-459b-8539-206768b60a9b.png)
  
5. In this step, you'll create the six subdomains listed in the **Subdomain (Host name)** table below. Later in, step 7, you'll update each subdomain with its correct CNAME value. 
    
6. Under **Settings (domain)**, expand **Create sub-domain**.
    
    ![Strato_subdomain_Expand](../media/2f0397d4-7ee6-44c0-afc5-1df60399a96f.png)
  
7. In the **Name of the sub-domain** box, type the first subdomain name from the **Subdomain (Host name)** table below. Then select **Create sub-domain**.
    
    ![Strato_subdomain_Create](../media/b7c659d0-a5e5-4ad7-88ec-d83dc3318004.png)
  
8. Repeat this step for each subdomain in the following table.
    
    |**Subdomain (Host name)**|
    |:-----|
    |autodiscover  <br/> |
    |sip  <br/> |
    |lyncdiscover  <br/> |
    |msoid  <br/> |
    |enterpriseregistration  <br/> |
    |enterpriseenrollment  <br/> |
   
9. Select **To the overview**.
    
    ![Strato_ToOverview](../media/4f0dc974-fa74-4d9b-9b5a-0f133e0acdd3.png)
  
10. Now you'll update each subdomain with its CNAME value. 
    
11. Select the **+** icon next to your domain to expand the subdomain list. 
    
    ![Strato_expand_domain](../media/5d036677-a92b-4297-bfdc-77f8c5363b73.png)
  
12. Next to a subdomain, select **manage**.
    
    ![Strato_subdomain_manage](../media/f97b4f9a-cea0-4537-8439-e3151a0dc980.png)
  
13. Expand **DNS management**.
    
    ![Strato_subdomain_Expand_DNS](../media/7cc4f400-00be-44d6-b56a-2d5611c9bf51.png)
  
14. Next to **CNAME record**, select **manage**.
    
    ![Strato_subdomain_CNAME_manage](../media/d323dba7-bdbb-445e-8eb9-40b452808b05.png)
  
15. Select **Change CNAME entry**, and then enter the corresponding CNAME value from the table below. You must include a period at the end of the value. 
  
    |**Subdomain (Host name)**|**Type**|**Value (Points to address or value)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> |
    |msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> |
   
    ![Strato_subdomain_CNAME_values](../media/84b4bada-92dd-4de1-b2de-4bff05b16017.png)
  
16. Select the **I am aware…** checkbox, and then select **Accept settings**.
    
    ![Strato_subdomain_CNAME_values](../media/55d9a738-396f-4575-bd8e-7ba5e03206ac.png)
  
17. Select **To the overview**
    
    ![Strato_CNAME_values_ToOverview](../media/760448c2-44b3-4906-9304-32c35c85d7c1.png)
  
18. Select **To the overview** again. 
    
    ![Strato_CNAME_values_ToOverviewAgain](../media/a02c7269-2cb3-4c83-9a73-40f6fbdd8cc0.png)
  
19. Select the **+** icon next to your domain to expand the subdomain list, and then repeat this entire step for each subdomain in the list. 
    
## Add a TXT record for SPF to help prevent email spam
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select **Domains**.
    
    ![Strato_domains](../media/ae990bf2-6f98-4dd6-9aef-f65d2888091a.png)
  
3. Select **Domain management**.
    
    ![strato_domainManagement](../media/eced1360-f207-4b5e-bd61-848a70dc44a9.png)
  
4. On the **Domain management** page, next to the domain you want to manage, select **manage**.
    
    ![strato_manage](../media/2d9bd3ae-e4bc-459b-8539-206768b60a9b.png)
  
5. Under **Settings (domain)**, expand **DNS Settings**.
    
    ![strato_DNSsettings](../media/fb83450b-f638-4cd6-a844-5eab442424ae.png)
  
6. Next to **TXT records, including SPF and DKIM settings**, choose **manage**.
    
    ![strato_TXT_manage](../media/e01f9724-d26d-4253-a263-c4c9544c3962.png)
  
7. In the boxes for the TXT record, type or copy and paste the values from the following table.
    
    > [!NOTE]
    > If records already exist, select the **+** button to add a new TXT record. 
  
    |**Prefix**|**Type**|**Value**|
    |:-----|:-----|:-----|
    |(leave blank)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Strato_TXT SPF_values](../media/efdbfd3e-c568-40a0-b997-c5216fa8d891.png)
  
8. Select **Accept settings** to save the record. 
    
    ![Strato_TXT SPF_values_Accept](../media/bf6e1050-215a-4542-935d-d2201cf3dc6d.png)
  
## Add the two SRV records that are required for Office 365
<a name="bkmk_srv"> </a>

1. To get started, go to your domains page in Strato.com by using [this link](https://www.strato.com/apps/CustomerService). You'll be prompted to log in.
    
    ![strato_login](../media/5d7e87b3-f1ae-4be9-bede-3260258d2205.png)
  
2. Select **Domains**.
    
    ![Strato_domains](../media/ae990bf2-6f98-4dd6-9aef-f65d2888091a.png)
  
3. Select **Domain management**.
    
    ![strato_domainManagement](../media/eced1360-f207-4b5e-bd61-848a70dc44a9.png)
  
4. On the **Domain management** page, next to the domain you want to manage, select **manage**.
    
    ![strato_manage](../media/2d9bd3ae-e4bc-459b-8539-206768b60a9b.png)
  
5. Under **Settings (domain)**, expand **DNS Settings**.
    
    ![strato_DNSsettings](../media/fb83450b-f638-4cd6-a844-5eab442424ae.png)
  
6. Next to **SRV record**, choose **manage**.
    
    ![Strato_SRV_manage](../media/a6842088-34b5-4333-95ab-e591a4ddf891.png)
  
7. Next to **SRV record**, select **Enabled**, and then in the boxes for the new record, type or copy and paste the values from the following table.
    
    |**Service**|**Protocol**|**Record type**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |sip  <br/> |tls  <br/> |SRV (Service)  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |
    |sipfederationtls  <br/> |tcp﻿  <br/> |SRV (Service)  <br/> |100  <br/> |1 <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |
   
    ![Strato_SRV_values](../media/bf5bca69-2fc4-4c46-8bac-14ec5dd6e5a3.png)
  
8. Select the **+** icon to add a new line for the second SRV record. Type or copy and paste the values from the table above for the second record. 
    
9. Select **Accept settings** to save the records. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  


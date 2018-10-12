---
title: "Create DNS records at Blacknight for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8362dc56-976b-41ee-bb00-4736ee2d8f91

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Blacknight for Office 365."
---

# Create DNS records at Blacknight for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Blacknight is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. Follow the steps below. (Need more help? [Still need help?](create-dns-records-at-1-1-internet.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-blacknight.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-blacknight.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-blacknight.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-blacknight.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-blacknight.md#BKMK_add_SRV)
    
After you add these records at Blacknight, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
    ![Blacknight-BP-Configure-1-3](../media/9a028259-5525-48e2-a071-8948de207fee.png)
  
4. Choose the **DNS** tab. 
    
    ![Blacknight-BP-Configure-1-4-1](../media/fe9bfd97-11aa-49b5-9bfa-e9d9a52ee98c.png)
  
5. Then choose **DNS Records**.
    
    ![Blacknight-BP-Configure-1-4-2](../media/efba13d7-d305-4b76-98cf-fe736304cea1.png)
  
6. Choose **Add New DNS Record**.
    
    ![Blacknight-BP-Configure-1-5](../media/9b843ca3-a1b5-411f-aecb-2d21fead5cb1.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** value from the drop-down list.) 
    
|**DNS Record Type**|**Domain**|**Data**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![Blacknight-BP-Verify-1-1](../media/b6c3c40b-d2ed-4efe-95ad-1213d57aae94.png)
  
8. Choose **Finish**.
    
    ![Blacknight-BP-Verify-1-2](../media/0cd9134d-bbfa-41a3-913a-d0a223ec6ae4.png)
  
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
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
    ![Blacknight-BP-Configure-1-3](../media/9a028259-5525-48e2-a071-8948de207fee.png)
  
4. Choose the **DNS** tab. 
    
    ![Blacknight-BP-Configure-1-4-1](../media/fe9bfd97-11aa-49b5-9bfa-e9d9a52ee98c.png)
  
5. Then choose **DNS Records**.
    
    ![Blacknight-BP-Configure-1-4-2](../media/efba13d7-d305-4b76-98cf-fe736304cea1.png)
  
6. Choose **Add New DNS Record**.
    
    ![Blacknight-BP-Configure-1-5](../media/9b843ca3-a1b5-411f-aecb-2d21fead5cb1.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** and **Preference** values from the drop-down lists.) 
    
|**DNS Record Type**|**Mail domain**|**Preference**|**Mail exchanger**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|MX  <br/> |(Leave this field empty.)  <br/> |Very high (10)  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![Blacknight-BP-Configure-2-1](../media/39b85283-78a7-4361-82da-31af7023c6e1.png)
  
8. Choose **Finish**.
    
    ![Blacknight-BP-Configure-2-2](../media/fdafa143-d5e1-469f-8a15-5e3cb03d385d.png)
  
9. If there are any other MX records, delete them by selecting all of them.
    
    ![Blacknight-BP-Configure-2-3-1](../media/c914bb34-40ae-431c-8d59-69929603228d.png)
  
10. Then choose **Delete**.
    
    ![Blacknight-BP-Configure-2-3-2](../media/e94afd22-d706-49f5-b8c9-dee4af443fdd.png)
  
11. If you deleted any MX records in the preceding step, choose **OK** in the confirmation dialog box. 
    
    ![Blacknight-BP-Configure-2-4](../media/50863027-1de2-4050-81f8-d5d69437d369.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
    ![Blacknight-BP-Configure-1-3](../media/9a028259-5525-48e2-a071-8948de207fee.png)
  
4. Choose the **DNS** tab. 
    
    ![Blacknight-BP-Configure-1-4-1](../media/fe9bfd97-11aa-49b5-9bfa-e9d9a52ee98c.png)
  
5. Then choose **DNS Records**.
    
    ![Blacknight-BP-Configure-1-4-2](../media/efba13d7-d305-4b76-98cf-fe736304cea1.png)
  
6. Choose **Add New DNS Record**.
    
    ![Blacknight-BP-Configure-1-5](../media/9b843ca3-a1b5-411f-aecb-2d21fead5cb1.png)
  
7. Add the first of the CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** from the drop-down list.) 
    
|**DNS Record Type**|**Domain**|**Canonical name**|**TTL**|
|:-----|:-----|:-----|:-----|
|CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
|CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
|CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
|CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
|CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
|CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![Blacknight-BP-Configure-3-1](../media/8029a021-0ac8-4d79-87e6-74dd125d998b.png)
  
8. Choose **Finish**.
    
    ![Blacknight-BP-Configure-3-2](../media/b0cdc4b8-f8e7-4d59-a89a-5bcc3a492fab.png)
  
9. To add each of the other five CNAME records, choose **Add New DNS Record** again, create a record using the values from the next row in the table, and then again choose **Finish** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
    ![Blacknight-BP-Configure-1-3](../media/9a028259-5525-48e2-a071-8948de207fee.png)
  
4. Choose the **DNS** tab. 
    
    ![Blacknight-BP-Configure-1-4-1](../media/fe9bfd97-11aa-49b5-9bfa-e9d9a52ee98c.png)
  
5. Then choose **DNS Records**.
    
    ![Blacknight-BP-Configure-1-4-2](../media/efba13d7-d305-4b76-98cf-fe736304cea1.png)
  
6. Choose **Add New DNS Record**.
    
    ![Blacknight-BP-Configure-1-5](../media/9b843ca3-a1b5-411f-aecb-2d21fead5cb1.png)
  
7. In the boxes for the new record, type or copy and paste the value from the following table.
    
|**DNS Record Type**|**Domain**|**Data**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![Blacknight-BP-Configure-4-1](../media/90d8eb39-3191-4fe1-8bf0-e73b77250ed4.png)
  
8. Choose **Finish**.
    
    ![Blacknight-BP-Configure-4-2](../media/0847b75d-5d1f-40af-ab71-a31eec14bfb1.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
    ![Blacknight-BP-Configure-1-3](../media/9a028259-5525-48e2-a071-8948de207fee.png)
  
4. Choose the **DNS** tab. 
    
    ![Blacknight-BP-Configure-1-4-1](../media/fe9bfd97-11aa-49b5-9bfa-e9d9a52ee98c.png)
  
5. Then choose **DNS Records**.
    
    ![Blacknight-BP-Configure-1-4-2](../media/efba13d7-d305-4b76-98cf-fe736304cea1.png)
  
6. Choose **Add New DNS Record**.
    
    ![Blacknight-BP-Configure-1-5](../media/9b843ca3-a1b5-411f-aecb-2d21fead5cb1.png)
  
7. Add the first of the two SRV records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Choose the **DNS Record Type**, **Protocol**, and **Preference** values from the drop-down lists. The **Protocol** list is the unlabeled drop-down list to the right of the **Service** box. The **Port** field is the unlabeled box to the right of the first **Server Host** field.) 
    
|**DNS Record Type**|**Service**|**Protocol**|**Preference**|**Weight**|**Data**|**Port**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SRV  <br/> |sip  <br/> |tls  <br/> |Custom (100)  <br/> |1  <br/> |sipdir.online.lync.com  <br/> |443  <br/> |Select **Custom** and enter the value **3600**.  <br/> |
|SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |Custom (100)  <br/> |1  <br/> |sipfed.online.lync.com  <br/> |5061  <br/> |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![Blacknight-BP-Configure-5-1](../media/5f12d96a-bf5a-4e15-8958-7d107c745abd.png)
  
8. Choose **Finish**.
    
    ![Blacknight-BP-Configure-5-2](../media/6fea8115-d1f1-4d48-8a95-69dbf91b118f.png)
  
9. To add the other SRV record, choose **Add New DNS Record** again, create a record using the values from the second row in the table, and then again choose **Finish** to complete the record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

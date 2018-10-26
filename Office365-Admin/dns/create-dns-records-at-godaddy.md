---
title: "Create DNS records at GoDaddy for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_GD'
- 'O365M_DOM_GD'
- 'O365M_AddDNSRecords_GoDaddySteps'
- 'O365E_DOM_GD'
- 'O365E_AddDNSRecords_GoDaddySteps'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at GoDaddy for Office 365."
---

# Create DNS records at GoDaddy for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Follow the steps below or [watch the video (start at 0:43)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-GoDaddy-for-Office-365-7d56924e-77ab-4ac6-b6f2-ca0e1a72249d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at GoDaddy by using [this link](https://dcc.godaddy.com). You'll be prompted to log in.
    
    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)
  
2. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![GoDaddy-BP-Configure-1-2](../media/97f68c12-b4c7-45eb-872e-17dbe288db21.png)
  
3. Choose **DNS Zone File**.
    
    ![GoDaddy-BP-Configure-1-3](../media/4823c977-3662-4057-b661-c6e393c25855.png)
  
4. Choose ** Add Record **.
    
    ![GoDaddy-BP-Configure-1-4](../media/ab66fdc2-e16a-43ab-924e-3365ac037fe0.png)
  
5. Choose **TXT (Text)** from the drop-down list. 
    
    ![GoDaddy-BP-Verify-1-0](../media/33e9173a-e046-41a2-98b7-bae8e0d5a081.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **TTL** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |Record type  <br/> |Host  <br/> |TXT Value  <br/> |TTL  <br/> |
    |TXT (Text)  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1 hour  <br/> |
   
   ![GoDaddy-BP-Verify-1-1](../media/fad2470b-c347-4682-bc92-5f4fc60d92e1.png)
  
7. Choose **Finish**.
    
    ![GoDaddy-BP-Verify-1-2](../media/f0f82379-07d7-4fdb-81cb-37660e968659.png)
  
8. Choose **Save Changes**.
    
    ![GoDaddy-BP-Verify-1-3](../media/5d6d058e-3506-4dab-a7fc-0dd98cf368bb.png)
  
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

Follow the steps below or [watch the video (start at 3:36)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-GoDaddy-for-Office-365-7d56924e-77ab-4ac6-b6f2-ca0e1a72249d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at GoDaddy by using [this link](https://dcc.godaddy.com). You'll be prompted to log in.
    
    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)
  
2. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![GoDaddy-BP-Configure-1-2](../media/97f68c12-b4c7-45eb-872e-17dbe288db21.png)
  
3. Choose **DNS Zone File**.
    
    ![GoDaddy-BP-Configure-1-3](../media/4823c977-3662-4057-b661-c6e393c25855.png)
  
4. Choose **Add Record**.
    
    ![GoDaddy-BP-Configure-1-4](../media/ab66fdc2-e16a-43ab-924e-3365ac037fe0.png)
  
5. Choose **MX (Mail Exchanger)** from the drop-down list. 
    
    ![GoDaddy-BP-Configure-2-0](../media/2621bf89-69be-42bd-a047-55b2e9b17891.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **TTL** value from the drop-down list.) 
    
    |**Record type**|**Host**|**Points to**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1 hour  <br/> |
   
   ![GoDaddy-BP-Configure-2-1](../media/c0d17b39-0315-48ce-99c5-541bdc52e10a.png)
  
7. Choose **Finish**.
    
    ![GoDaddy-BP-Configure-2-2](../media/312a0051-18ee-4853-873a-ba1502474b64.png)
  
8. Choose **Save Changes**.
    
    ![GoDaddy-BP-Configure-2-3](../media/3f928450-6104-415f-8299-160df006574b.png)
  
9. If there are any other MX records, delete them all in the **MX (Mail Exchanger)** section of the **Domain Details** page. (Select each record and then, in the **Actions** column, choose the trash-can **Delete** icon.) 
    
    ![GoDaddy-BP-Configure-2-4](../media/f15cf114-6a99-4231-a754-4fa33b816336.png)
  
10. Choose **Save Changes**.
    
    ![GoDaddy-BP-Configure-2-5](../media/e8aacc46-7dcb-4c94-9250-41ce21f6c71f.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

Follow the steps below or [watch the video (start at 4:27)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-GoDaddy-for-Office-365-7d56924e-77ab-4ac6-b6f2-ca0e1a72249d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at GoDaddy by using [this link](https://dcc.godaddy.com). You'll be prompted to log in.
    
    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)
  
2. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![GoDaddy-BP-Configure-1-2](../media/97f68c12-b4c7-45eb-872e-17dbe288db21.png)
  
3. Choose **DNS Zone File**.
    
    ![GoDaddy-BP-Configure-1-3](../media/4823c977-3662-4057-b661-c6e393c25855.png)
  
4. Choose **Add Record**.
    
    ![GoDaddy-BP-Configure-1-4](../media/ab66fdc2-e16a-43ab-924e-3365ac037fe0.png)
  
5. Choose **CNAME (Alias)** from the drop-down list. 
    
    ![GoDaddy-BP-Configure-3-0](../media/251d0bcc-4964-4afe-a139-d83dd83a32c7.png)
  
6. Create the first CNAME record.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **TTL** value from the drop-down list.) 
    
    |**Record type**|**Host**|**Points to**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hour  <br/> |
   
   ![GoDaddy-BP-Configure-3-1](../media/bdb9a8da-ecc2-48f5-b0f2-1252aeed07a1.png)
  
7. Choose **Add Another**.
    
    (You will not choose **Finish** until you have added all of the CNAME records that you need.) 
    
    ![GoDaddy-BP-Configure-3-2](../media/f4ef2eef-beda-4706-897f-62349d296b73.png)
  
8. Create the other five CNAME records.
    
    For each record, type of copy and paste the values from the next row of the table above into the boxes for that record. After creating the second and third records, choose **Add Another**.
    
    Repeat these steps until you have created all six of the CNAME records.
    
9. When you have added the final CNAME record, choose **Finish**.
    
    ![GoDaddy-BP-Configure-3-3](../media/43248c08-52bb-4dc2-9116-e4b9379496d3.png)
  
10. Choose **Save Changes**.
    
    ![GoDaddy-BP-Configure-3-4](../media/7a36d24c-e8d1-4fc6-9696-9307a62587fc.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
Follow the steps below or [watch the video (start at 5:15)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-GoDaddy-for-Office-365-7d56924e-77ab-4ac6-b6f2-ca0e1a72249d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at GoDaddy by using [this link](https://dcc.godaddy.com). You'll be prompted to log in.
    
    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)
  
2. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![GoDaddy-BP-Configure-1-2](../media/97f68c12-b4c7-45eb-872e-17dbe288db21.png)
  
3. Choose **DNS Zone File**.
    
    ![GoDaddy-BP-Configure-1-3](../media/4823c977-3662-4057-b661-c6e393c25855.png)
  
4. Choose **Add Record**.
    
    ![GoDaddy-BP-Configure-1-4](../media/ab66fdc2-e16a-43ab-924e-3365ac037fe0.png)
  
5. Choose **TXT (Text)** from the drop-down list. 
    
    ![GoDaddy-BP-Configure-4-0](../media/232f6402-df5b-4c85-be44-493b0412b365.png)
  
6. In the boxes for the new record, type or copy and paste the following values.
    
    (Select the **TTL** value from the drop-down lists.) 
    
    |**Record type**|**Host**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |1 hour  <br/> |
   
    ![GoDaddy-BP-Configure-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)
  
7. Choose **Finish**.
    
    ![GoDaddy-BP-Configure-4-2](../media/4b2d5048-e95c-4a6c-aad3-a70949e2511f.png)
  
8. Choose **Save Changes**.
    
    ![GoDaddy-BP-Configure-4-3](../media/475f05e1-f15c-4544-b5ce-339d15d55cee.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

Follow the steps below or [watch the video (start at 5:59)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-GoDaddy-for-Office-365-7d56924e-77ab-4ac6-b6f2-ca0e1a72249d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at GoDaddy by using [this link](https://dcc.godaddy.com). You'll be prompted to log in.
    
    ![GoDaddy-BP-Configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)
  
2. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![GoDaddy-BP-Configure-1-2](../media/97f68c12-b4c7-45eb-872e-17dbe288db21.png)
  
3. Choose **DNS Zone File**.
    
    ![GoDaddy-BP-Configure-1-3](../media/4823c977-3662-4057-b661-c6e393c25855.png)
  
4. Choose **Add Record**.
    
    ![GoDaddy-BP-Configure-1-4](../media/ab66fdc2-e16a-43ab-924e-3365ac037fe0.png)
  
5. Choose **SRV (Service)** from the drop-down list. 
    
    ![GoDaddy-BP-Configure-5-0](../media/d7d940f1-8041-440c-b25f-c4d3149aa561.png)
  
6. Create the first SRV record.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Record type** and **TTL** values from the drop-down lists.) 
    
    |**Record type**|**Name**|**Target**|**Protocol**|**Service**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hour  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hour  <br/> |
   
    ![GoDaddy-BP-Configure-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)
  
7. Choose **Add Another**.
    
    (You will not choose **Finish** until you have added the other SRV record.) 
    
    ![GoDaddy-BP-Configure-5-2](../media/2a0b85db-b4ff-4d57-b5e3-dafc41157290.png)
  
8. Create the other SRV record.
    
    Type or copy and paste the values from the second row of the table above into the boxes for the second record.
    
9. Choose **Finish**.
    
    ![GoDaddy-BP-Configure-5-3](../media/60a56df3-9efa-45e5-a274-94453d8fff86.png)
  
10. Choose **Save Changes**.
    
    ![GoDaddy-BP-Configure-5-4](../media/feaf0204-4228-4dc0-93e2-3f80aaabcec3.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  


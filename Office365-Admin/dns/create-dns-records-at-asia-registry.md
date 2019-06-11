---
title: "Create DNS records at Asia Registry for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
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
ms.assetid: 525fd8a3-e33c-4abb-8c3b-786f06484894
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Asia Registry for Office 365."
---

# Create DNS records at Asia Registry for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Asia Registry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at Asia Registry, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **My Domains** page, in the row for the domain you're changing, choose the domain name. 
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-3](../media/820b6d1a-7fed-48f4-8015-c177693a1f0e.png)
  
4. On the **Domain Info** page, choose **DNS SETTINGS**.
    
    ![AsiaRegistry-BP-Configure-1-4](../media/39b750e4-4ed7-47ca-9a8a-b1b8a9fe77eb.png)
  
5. Select **Use Asia Registry Name Servers**.
    
    ![AsiaRegistry-BP-Configure-1-5](../media/8a05d58d-f5ea-4fb3-aaa4-f4b332c4c6e7.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
    ![AsiaRegistry-BP-Configure-1-6](../media/2074b068-196e-447e-aa0a-99478451545c.png)
  
7. In the **ZONE RECORDS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Host**|**Type**|**Content**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/>**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![AsiaRegistry-BP-Verify-1-1](../media/a9e44f32-8a50-4b58-ad97-b87bb618bd77.png)
  
8. Choose **ADD** to save the record, which also automatically adds a new empty row. 
    
    ![AsiaRegistry-BP-Verify-1-2](../media/886175ad-1b81-4822-93a7-88379945ca2e.png)
  
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **My Domains** page, in the row for the domain you're changing, choose the domain name. 
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-3](../media/820b6d1a-7fed-48f4-8015-c177693a1f0e.png)
  
4. On the **Domain Info** page, choose **DNS SETTINGS**.
    
    ![AsiaRegistry-BP-Configure-1-4](../media/39b750e4-4ed7-47ca-9a8a-b1b8a9fe77eb.png)
  
5. Select **Use Asia Registry Name Servers**.
    
    ![AsiaRegistry-BP-Configure-1-5](../media/8a05d58d-f5ea-4fb3-aaa4-f4b332c4c6e7.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
    ![AsiaRegistry-BP-Configure-1-6](../media/2074b068-196e-447e-aa0a-99478451545c.png)
  
7. In the **ZONE RECORDS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Host**|**Type**|**Content**|**Priority**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![AsiaRegistry-BP-Configure-2-1](../media/8c56db68-da62-4ad6-b025-5fa50d1d4583.png)
  
8. Choose **ADD** to save the record, which also automatically adds a new empty row. 
    
    ![AsiaRegistry-BP-Configure-2-2](../media/5992edb4-eb37-4e12-b18c-0959894ee9df.png)
  
9. If there are any other MX records in the **MX Records** section, delete one of them by choosing the **Delete (X)** icon for that record. 
    
    ![AsiaRegistry-BP-Configure-2-3](../media/8306ef7a-b7e7-475d-9b4a-f347f00903df.png)
  
10. Choose **CONFIRM** to confirm your deletion. 
    
    ![AsiaRegistry-BP-Configure-2-4](../media/c066c8fe-47f3-4e97-bdf8-e6fdbb104592.png)
  
11. Use the same steps to delete all other MX records, except for the one that you created earlier in this procedure.
    
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **My Domains** page, in the row for the domain you're changing, choose the domain name. 
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-3](../media/820b6d1a-7fed-48f4-8015-c177693a1f0e.png)
  
4. On the **Domain Info** page, choose **DNS SETTINGS**.
    
    ![AsiaRegistry-BP-Configure-1-4](../media/39b750e4-4ed7-47ca-9a8a-b1b8a9fe77eb.png)
  
5. Select **Use Asia Registry Name Servers**.
    
    ![AsiaRegistry-BP-Configure-1-5](../media/8a05d58d-f5ea-4fb3-aaa4-f4b332c4c6e7.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
    ![AsiaRegistry-BP-Configure-1-6](../media/2074b068-196e-447e-aa0a-99478451545c.png)
  
7. Add the first of the six CNAME records.
    
    In the **ZONE RECORDS** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Host**|**Type**|**Content**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![AsiaRegistry-BP-Configure-3-1](../media/4e054b56-0582-4e54-95a5-92678c068655.png)
  
8. Choose **ADD** to save the record, which also automatically adds a new empty row. 
    
    ![AsiaRegistry-BP-Configure-3-2](../media/5e934f3e-57b7-437c-a63b-d9d5f364118e.png)
  
9. Add each of the other five CNAME records.
    
    In the **ZONE RECORDS** section, create a record using the values from the next row in the table, and then again choose **ADD** to complete that record and add an empty row. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **My Domains** page, in the row for the domain you're changing, choose the domain name. 
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-3](../media/820b6d1a-7fed-48f4-8015-c177693a1f0e.png)
  
4. On the **Domain Info** page, choose **DNS SETTINGS**.
    
    ![AsiaRegistry-BP-Configure-1-4](../media/39b750e4-4ed7-47ca-9a8a-b1b8a9fe77eb.png)
  
5. Select **Use Asia Registry Name Servers**.
    
    ![AsiaRegistry-BP-Configure-1-5](../media/8a05d58d-f5ea-4fb3-aaa4-f4b332c4c6e7.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
    ![AsiaRegistry-BP-Configure-1-6](../media/2074b068-196e-447e-aa0a-99478451545c.png)
  
7. In the **ZONE RECORDS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Host**|**Type**|**Content**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![AsiaRegistry-BP-Configure-4-1](../media/f8be1015-29b5-41df-81ed-fb0a93108540.png)
  
8. Choose **ADD** to save the record, which also automatically adds a new empty row. 
    
    ![AsiaRegistry-BP-Configure-4-2](../media/b4d5b7ba-ce4f-438c-a77d-3521c3d4f81c.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **My Domains** page, in the row for the domain you're changing, choose the domain name. 
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-3](../media/820b6d1a-7fed-48f4-8015-c177693a1f0e.png)
  
4. On the **Domain Info** page, choose **DNS SETTINGS**.
    
    ![AsiaRegistry-BP-Configure-1-4](../media/39b750e4-4ed7-47ca-9a8a-b1b8a9fe77eb.png)
  
5. Select **Use Asia Registry Name Servers**.
    
    ![AsiaRegistry-BP-Configure-1-5](../media/8a05d58d-f5ea-4fb3-aaa4-f4b332c4c6e7.png)
  
6. Choose ** EDIT ZONE RECORDS (Advanced) **
    
    ![AsiaRegistry-BP-Configure-1-6](../media/2074b068-196e-447e-aa0a-99478451545c.png)
  
7. Add the first SRV record.
    
    In the **ZONE RECORDS** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Host**|**Type**|**Content**|**Priority**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |100|
    |_sipfederationtls._tcp|SRV|1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |100|
   
    ![AsiaRegistry-BP-Configure-5-1](../media/f5ba412d-380c-460a-806e-3a7d93205995.png)
  
8. Choose **ADD** to save the record, which also automatically adds a new empty row. 
    
    ![AsiaRegistry-BP-Configure-5-2](../media/8e0588f2-49b1-4207-a9cd-832d5cadbc3b.png)
  
9. Add the other SRV record.
    
    Still in the **ZONE RECORDS** section, create a record using the values from the other row in the table, and then again choose **ADD** to complete that record and add another empty row. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

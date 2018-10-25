---
title: "Create DNS records at Cloudflare for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
ms.custom:
- Adm_O365
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Cloudflare for Office 365."
---

# Create DNS records at Cloudflare for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> You must perform this procedure at the domain registrar where you purchased and registered your domain. 
  
When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process. 
  
The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services. To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.
  
To change your domain's name servers at your domain registrar's website yourself, follow these steps.
  
1. Find the area on the domain registrar's website where you can edit the nameservers for your domain.
    
2. Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.
    
|||
|:-----|:-----|
|First nameserver  <br/> |Use the nameserver value provided by Cloudflare.  <br/> |
|Second nameserver  <br/> |Use the nameserver value provided by Cloudflare.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. If there are any other name servers listed, you should delete them. 
  
3. Save your changes.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.
    
    ![Cloudflare-BP-Configure-1-1](../media/e1ab6ca7-c36d-42ce-9e0a-5e1b0c0b234c.png)
  
2. On the **Overview** page, in the **Select Website** area, choose the domain that you want to update. 
    
    ![Cloudflare-BP-Configure-1-2](../media/7ecd4e8d-cbeb-4af2-81e9-51801ae169b5.png)
  
3. On the **Overview** page for your domain, choose **DNS**.
    
    ![Cloudflare-BP-Configure-1-3](../media/19fdc829-44af-4280-af56-bda36a4b2c26.png)
  
4. In the **DNS Records** area, in the boxes for the new record, choose the values from the following table. 
    
    (Select the **Type** and **TTL** values from the drop-down lists.) 
    
|**Type**|**Name**|**Automatic TTL**|
|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |30 minutes  <br/> |
   
    ![Cloudflare-BP-Verify-1-1](../media/d88562c8-a146-4d3c-954c-6f5d8871afc2.png)
  
5. Choose **Click to configure**.
    
    ![Cloudflare-BP-Verify-1-2](../media/bbe39fcc-1a31-438c-b28e-486eee1222b5.png)
  
6. On the **Add Record: TXT content** page, in the box for the new record, type or copy and paste the value from the following table. 
    
|**Content**|
|:-----|
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![Cloudflare-BP-Verify-1-3](../media/8594832d-1e81-492d-9fb3-26ffe019a8e9.png)
  
7. Choose **Save**.
    
    ![Cloudflare-BP-Verify-1-4](../media/a2f53281-bc36-42a9-8153-aa7cd3829578.png)
  
8. Choose **Add Record**.
    
    ![Cloudflare-BP-Verify-1-5](../media/31ad8d5a-bc61-4ef7-a6ef-c910d18cd412.png)
  
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

1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.
    
    ![Cloudflare-BP-Configure-1-1](../media/e1ab6ca7-c36d-42ce-9e0a-5e1b0c0b234c.png)
  
2. On the **Overview** page, in the **Select Website** area, choose the domain that you want to update. 
    
    ![Cloudflare-BP-Configure-1-2](../media/7ecd4e8d-cbeb-4af2-81e9-51801ae169b5.png)
  
3. On the **Overview** page for your domain, choose **DNS**.
    
    ![Cloudflare-BP-Configure-1-3](../media/19fdc829-44af-4280-af56-bda36a4b2c26.png)
  
4. In the **DNS Records** area, in the boxes for the new record, choose the values from the following table. 
    
    (Select the **Type** and **TTL** values from the drop-down lists.) 
    
|**Type**|**Name**|**Automatic TTL**|
|:-----|:-----|:-----|
|MX  <br/> |@  <br/> |30 minutes  <br/> |
   
   ![Cloudflare-BP-Configure-2-1](../media/20d0a593-d50d-4d5e-b7e0-8ec31a27edc6.png)
  
5. Choose **Click to configure**.
    
    ![Cloudflare-BP-Configure-2-2](../media/e7eafd95-ea8e-4cea-804a-49559ee436a3.png)
  
6. On the **Add Record: MX content** page, in the boxes for the new record, type or copy and paste the values from the following table. 
    
|**Server**|**Priority**|
|:-----|:-----|
| *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Cloudflare-BP-Configure-2-3](../media/7b111d3a-2058-4694-a0a7-325c7a407838.png)
  
7. Choose **Save**. 
    
    ![Cloudflare-BP-Configure-2-4](../media/8687fa2d-94e8-4d8c-905c-85492bbe2a35.png)
  
8. Choose **Add Record**.
    
    ![Cloudflare-BP-Configure-2-5](../media/604faee8-bfe6-4f9e-aff5-ce432259ec6f.png)
  
9. If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon. 
    
    ![Cloudflare-BP-Configure-2-6](../media/4744d759-e92c-4e19-844d-a11dd5f37a31.png)
  
10. In the **Confirm** dialog box, choose **OK** to confirm your changes. 
    
    ![Cloudflare-BP-Configure-2-7](../media/73c3c04b-7fe1-4dd9-95c0-7a57c624f093.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.
    
    ![Cloudflare-BP-Configure-1-1](../media/e1ab6ca7-c36d-42ce-9e0a-5e1b0c0b234c.png)
  
2. On the **Overview** page, in the **Select Website** area, choose the domain that you want to update. 
    
    ![Cloudflare-BP-Configure-1-2](../media/7ecd4e8d-cbeb-4af2-81e9-51801ae169b5.png)
  
3. On the **Overview** page for your domain, choose **DNS**.
    
    ![Cloudflare-BP-Configure-1-3](../media/19fdc829-44af-4280-af56-bda36a4b2c26.png)
  
4. Add the first of the six CNAME records.
    
    In the **DNS Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    (Select the **Type** and **TTL** values from the drop-down lists.) 
    
|**Type**|**Name**|**Domain name**|**Automatic TTL**|
|:-----|:-----|:-----|:-----|
|CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |
|CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutes  <br/> |
|CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutes  <br/> |
|CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutes  <br/> |
|CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutes  <br/> |
|CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |30 minutes  <br/> |
   
   ![Cloudflare-BP-Configure-3-1](../media/02d0ee6e-5eb6-4a41-80b0-d9f75bd6c7a9.png)
  
5. Choose the **DNS Traffic** icon to bypass the Cloudflare servers. 
    
    ![Cloudflare-BP-Configure-3-1-2](../media/903aca96-a3b4-4c70-b205-8694b5dbd0ab.png)
  
6. Choose **Add Record**.
    
    ![Cloudflare-BP-Configure-3-2](../media/5fcdbb38-b101-434d-8e22-2c3a2c979c3e.png)
  
7. Add each of the other five CNAME records.
    
    In the **DNS Records** section, in the empty row, create a record by using the values from the next row in the table, and then again choose **Add Record** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.
    
    ![Cloudflare-BP-Configure-1-1](../media/e1ab6ca7-c36d-42ce-9e0a-5e1b0c0b234c.png)
  
2. On the **Overview** page, in the **Select Website** area, choose the domain that you want to update. 
    
    ![Cloudflare-BP-Configure-1-2](../media/7ecd4e8d-cbeb-4af2-81e9-51801ae169b5.png)
  
3. On the **Overview** page for your domain, choose **DNS**.
    
    ![Cloudflare-BP-Configure-1-3](../media/19fdc829-44af-4280-af56-bda36a4b2c26.png)
  
4. In the **DNS Records** area, in the boxes for the new record, choose the values from the following table. 
    
    (Select the **Type** and **TTL** values from the drop-down lists.) 
    
|**Type**|**Name**|**Automatic TTL**|
|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |30 minutes  <br/> |
   
    ![Cloudflare-BP-Configure-4-1](../media/e7b07179-48f7-4ff0-b4a0-300c560bdd98.png)
  
5. Choose **Click to configure**.
    
    ![Cloudflare-BP-Configure-4-2](../media/e213f7d2-c922-45de-8dc8-b4146d5c28a1.png)
  
6. On the **Add Record: TXT content** page, in the box for the new record, type or copy and paste the value from the following table. 
    
|**Content**|
|:-----|
|v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![Cloudflare-BP-Configure-4-3](../media/27d199f6-95a6-4bf7-b42c-79f10158b413.png)
  
7. Choose **Save Changes**.
    
    ![Cloudflare-BP-Configure-4-4](../media/fc7c62d2-b37d-4660-ad79-d27be67d9ed9.png)
  
8. Choose **Add Record**.
    
    ![Cloudflare-BP-Configure-4-5](../media/9d4564b5-176f-455b-9c78-837c56214aa1.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.
    
    ![Cloudflare-BP-Configure-1-1](../media/e1ab6ca7-c36d-42ce-9e0a-5e1b0c0b234c.png)
  
2. On the **Overview** page, in the **Select Website** area, choose the domain that you want to update. 
    
    ![Cloudflare-BP-Configure-1-2](../media/7ecd4e8d-cbeb-4af2-81e9-51801ae169b5.png)
  
3. On the **Overview** page for your domain, choose **DNS**.
    
    ![Cloudflare-BP-Configure-1-3](../media/19fdc829-44af-4280-af56-bda36a4b2c26.png)
  
4. Add the first of the two SRV records.
    
    In the DNS Records area, in the boxes for the new records, choose the values from the first row in the following table.
    
|**Type**|**TTL**|
|:-----|:-----|
|SRV  <br/> |30 minutes  <br/> |
   
   ![Cloudflare-BP-Configure-5-1](../media/c4b62e94-9abe-49f1-b047-1dbb31873515.png)
  
5. Choose the first **Click to configure** box. 
    
    ![Cloudflare-BP-Configure-5-2](../media/5c6971d4-7492-4190-b435-68b24081cc15.png)
  
6. On the **Add Record: SRV name** page, in the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
|**Service name**|**Protocol**|**Name**|
|:-----|:-----|:-----|
|_sip  <br/> |TLS  <br/> |Use your  *domain_name*  , for example, contoso.com  <br/> |
|_sipfederationtls  <br/> |TCP  <br/> |Use your  *domain_name*  , for example, contoso.com  <br/> |
   
   ![Cloudflare-BP-Configure-5-3](../media/0373fb6a-c73f-444f-b52d-f8f645708630.png)
  
7. Choose **Save**.
    
    ![Cloudflare-BP-Configure-5-4](../media/99f3d243-509e-464f-bb53-d0d56be09699.png)
  
8. On the **Add Record: SRV content** page, in the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
|**Priority**|**Weight**|**Port**|**Target**|
|:-----|:-----|:-----|:-----|
|100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
|100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
   ![Cloudflare-BP-Configure-5-5](../media/40e7b3bf-6eca-4b3f-b719-27b9c6baecc6.png)
  
9. Choose **Save**.
    
    ![Cloudflare-BP-Configure-5-6](../media/18001ce6-75f5-4da0-991a-8c8c0c6ec389.png)
  
10. Choose **Add Record**.
    
    ![Cloudflare-BP-Configure-5-7](../media/3c11f19f-0c52-4cb9-882d-97e4039ebc10.png)
  
11. Add the other SRV record.
    
    In the ** DNS Records ** section, in the empty row, create the next record by copying and pasting the **Service name**, **Protocol**, and **Name** values from the second row of the table to the first screen, copying and pasting the **Priority**, **Weight**, **Port**, and **Target** values from the second row of the table to the next screen, and then again choosing **Add Record** to complete that record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

---
title: "Create DNS records at Aabaco Small Business for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Aabaco'
- 'O365M_DOM_Aabaco'
- 'O365E_DOM_Aabaco'
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
ms.assetid: 53d1daba-6a4f-4814-8a68-8ad3d031463e
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Aabaco Small Business for Office 365."
---

# Create DNS records at Aabaco Small Business for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Aabaco Small Business is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at Aabaco Small Business, your domain will be set up to work with Office 365 services.
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
> [!IMPORTANT]
> Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
   To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
1. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
2. On the **Domain Control Panel** page, in the **TXT Records** section, choose **Add**.
    
3. On the **Add TXT Record** page, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Hostname:**|**Text:**|
    |:-----|:-----|
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** You must use the admin center to get this value.[Get help with Office 365 domains](../get-help-with-domains/get-help-with-domains.md)   <br/>     |
   
    ![Type or paste the DSN values on the Add TXT Record page](../media/ae8386df-6cec-4bbe-a280-9d3fc170d972.png)
  
4. Choose **Add**.
    
    ![Click Add](../media/3fa1c496-a07d-46c2-babd-027aa8c276ac.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
1. To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
2. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
3. On the **Domain Control Panel** page, in the **MX Records** section, choose **Add**.
    
    ![Click Add](../media/fd87d347-9584-4555-a168-b2274325fc7b.png)
  
4. On the **Add MX Record** page, in the boxes for the new record, type or copy and paste the following values. 
    
    (Select the **Select priority** value from the drop-down list.) 
    
    |**Mail Server**|**Select priority**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your \< *domain-key*  \> from your Office 365 portal account. [How do I find this?](../get-help-with-domains/get-help-with-domains.md)      |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Aabaco-BP-Configure-2-2](../media/c45cda65-86e0-4ed0-a589-a698cf655599.png)
  
5. Choose **Add**.
    
    ![Aabaco-BP-Configure-2-3](../media/90f28f5b-aa2c-4c45-a097-3eb0d361b8d2.png)
  
6. Delete any other MX records that are listed by selecting the **Delete** (trash) control in the **Action** column. 
    
    ![Aabaco-BP-Configure-2-4](../media/a0c04902-b3de-4f44-ad4e-f48d7aaf2e55.png)
  
7. Choose **Delete**.
    
    ![Aabaco-BP-Configure-2-5](../media/8c518390-208a-495c-826e-8c038c5f3e47.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
1. To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
2. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
3. On the **Domain Control Panel** page, in the **A and CNAME Records** section, choose **Add**.
    
    ![Aabaco-BP-Configure-3-1](../media/d3b6e22e-7844-4e21-8dde-a8cd2dc1ae70.png)
  
4. On the **A or CNAME Record** page, add the first of the six CNAME records. 
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    > [!IMPORTANT]
    > You do not need to specify the record type in this case, because Aabaco Small Business will automatically recognize the type as CNAME by the values entered in the **Source** and **Destination** fields. 
  
    |**Source**|**Destination**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
   ![Aabaco-BP-Configure-3-2](../media/db4ff2a7-02b6-494c-bb30-a06a757b05a5.png)
  
5. Choose **Add**.
    
    ![Aabaco-BP-Configure-3-3](../media/587c40d4-ab72-4f5c-b48b-d0b9462cde8f.png)
  
6. Add each of the other five CNAME records.
    
    On the **Domain Control Panel** page, choose **Add** again, create a record using the values from the next row in the table, and then again choose **Add** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [details and sample SPF records](https://docs.microsoft.com/en-us/office365/enterprise/external-domain-name-system-records). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
1. To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
2. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
3. On the **Domain Control Panel** page, in the **TXT Records** section, choose **Add**.
    
    ![Aabaco-BP-Configure-4-1](../media/f1e476d2-aad3-4d51-b8b2-9e59f54875ef.png)
  
4. On the **Add TXT Record** page, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Hostname:**|**Text:**|
    |:-----|:-----|
    |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Aabaco-BP-Configure-4-2](../media/62b89a12-fb10-4b79-b629-8282c56b78bb.png)
  
5. Choose **Add**.
    
    ![Aabaco-BP-Configure-4-3](../media/2d62e4f7-730c-4cda-9221-21754c5a5e35.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
1. To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
2. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
3. On the **Domain Control Panel** page, in the **SRV Records** section, choose **Add**.
    
    (You may need to scroll down.)
    
    ![Aabaco-BP-Configure-5-1](../media/42842369-b4b2-4dec-a9f0-e07fbdcad052.png)
  
4. Add the first of the two SRV records.
    
    In the **Add SRV Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Hostname**|**Destination**|**Priority**|**Weight**|**Port**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|sipdir.online.lync.com. **Note:**  We recommend copying and pasting this entry, so that all of the spacing stays correct.           |100|1|443|
    |_sipfederationtls._tcp|sipfed.online.lync.com. **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |100|1|5061|
   
    ![Aabaco-BP-Configure-5-2](../media/65bb157b-0cfd-4c94-8ad5-1ca287eaed1d.png)
  
5. Choose **Add**.
    
    ![Aabaco-BP-Configure-5-3](../media/fc029899-4dee-4326-abf5-64cd6f0197af.png)
  
6. To add the other SRV record:
    
    In the **Add SRV Record** section, choose **Add**, create a record by using the values from the second row in the table, and then again choose **Add** to complete that record. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).   

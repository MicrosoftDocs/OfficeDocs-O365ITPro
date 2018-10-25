---
title: "Create DNS records at Europe Registry for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_ER'
- 'O365M_DOM_ER'
- 'O365E_DOM_ER'
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
ms.assetid: a225208c-0910-4704-9ae3-17624b9045c8
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at EuropeRegistry for Office 365."
---

# Create DNS records at Europe Registry for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Europe Registry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at Europe Registry, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Europe Registry by using [this link](https://europeregistry.secure-admin.com/domain/default/admin). You'll be prompted to log in first.
    
2. On the Dashboard page, choose **MY DOMAINS**.
    
3. In the **My Domains** section, choose the name of the domain that you want to edit. 
    
4. Choose **DNS SETTINGS**.
    
5. Select **Use Europe Registry Name Servers**.
    
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
||||
|:-----|:-----|:-----|
|**Host** <br/> |**Type** <br/> |**Content** <br/> |
|@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
8. Choose **ADD**.
    
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at Europe Registry by using [this link](https://europeregistry.secure-admin.com/domain/default/admin). You'll be prompted to log in first.
    
2. On the **Dashboard** page, choose ** MY DOMAINS **.
    
3. In the **My Domains** section, choose the name of the domain that you want to edit. 
    
4. Choose **DNS SETTINGS**.
    
5. Select **Use Europe Registry Name Servers**.
    
    ![Select Use Europe Registry Name Servers.](../media/c0428617-dfd7-4045-824b-7f8c9baa32c4.png)
  
6. Choose ** EDIT ZONE RECORDS (Advanced) **.
    
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host**|**Type**|**Content**|**Priority**|
|:-----|:-----|:-----|:-----|
|@  <br/> |MX  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> > [!NOTE]> Get your \< *domain-key*  \> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          **This value MUST end with a period (.)** <br/> |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![EuropeRegistry-BP-Configure-2-1](../media/49ac2f57-5d96-4e04-8000-747d47a5a61e.png)
  
8. Choose **ADD**.
    
    ![EuropeRegistry-BP-Configure-2-2](../media/27e52953-563a-47e6-8008-0bb4ff9dcd24.png)
  
9. If there are any other existing MX records, point at each of those records until an **X** appears beside the record, and then choose the **X** to delete that record. 
    
    Continue until all of the MX records are deleted except the one that you created earlier in this procedure.
    
    ![EuropeRegistry-BP-Configure-2-3](../media/f8d4f335-32c0-4e10-8a70-6b3a79f3a464.png)
  
10. Choose **CONFIRM**.
    
    ![EuropeRegistry-BP-Configure-2-4](../media/a33668a9-0e56-4dd7-b532-d1014b270932.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Europe Registry by using [this link](https://europeregistry.secure-admin.com/domain/default/admin). You'll be prompted to log in first.
    
2. On the **Dashboard** page, choose ** MY DOMAINS **.
    
3. In the **My Domains** section, choose the name of the domain that you want to edit. 
    
4. Choose **DNS SETTINGS**.
    
5. Select **Use Europe Registry Name Servers**.
    
    ![Select Use Europe Registry Name Servers.](../media/c0428617-dfd7-4045-824b-7f8c9baa32c4.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
7. Create the first of the six CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host**|**Type**|**Content**|
|:-----|:-----|:-----|
|autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
|sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
   ![EuropeRegistry-BP-Configure-3-1](../media/cdfb4e42-27d7-4626-afc7-62337da9e78d.png)
  
8. Choose **ADD**.
    
    ![EuropeRegistry-BP-Configure-3-2](../media/a6c3960b-16c7-49a2-869e-cda87c1f0858.png)
  
9. Use the same procedure to add each of the other five CNAME records, typing or copying and pasting the values from the remaining rows in the table above, and then choosing **ADD** when you have completed each record. 
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at Europe Registry by using [this link](https://europeregistry.secure-admin.com/domain/default/admin). You'll be prompted to log in first.
    
2. On the **Dashboard** page, choose ** MY DOMAINS **.
    
3. In the **My Domains** section, choose the name of the domain that you want to edit. 
    
4. Choose **DNS SETTINGS**.
    
5. Select **Use Europe Registry Name Servers**.
    
    ![Select Use Europe Registry Name Servers.](../media/c0428617-dfd7-4045-824b-7f8c9baa32c4.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host**|**Type**|**Content**|
|:-----|:-----|:-----|
|@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![EuropeRegistry-BP-Configure-4-1](../media/b024abfc-1232-4261-ad15-e1775d7eab50.png)
  
8. Choose **ADD**.
    
    ![EuropeRegistry-BP-Configure-4-2](../media/1efdc19a-492c-4ed8-bf08-f5136ac1304f.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Europe Registry by using [this link](https://europeregistry.secure-admin.com/domain/default/admin). You'll be prompted to log in first.
    
2. On the **Dashboard** page, choose ** MY DOMAINS **.
    
3. In the **My Domains** section, choose the name of the domain that you want to edit. 
    
4. Choose **DNS SETTINGS**.
    
5. Select **Use Europe Registry Name Servers**.
    
    ![Select Use Europe Registry Name Servers.](../media/c0428617-dfd7-4045-824b-7f8c9baa32c4.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
7. Create the first of the two SRV records:
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host**|**Type**|**Content**|**Priority**|
|:-----|:-----|:-----|:-----|
|_sip._tls|SRV|1 443 sipdir.online.lync.com.> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           **This value MUST end with a period (.)**|100|
|_sipfederationtls._tcp|SRV|1 5061 sipfed.online.lync.com.> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           **This value MUST end with a period (.)**|100|
   
   ![EuropeRegistry-BP-Configure-5-1](../media/e53e3791-008d-4ee8-aeff-742f36597373.png)
  
8. Choose **ADD**.
    
    ![EuropeRegistry-BP-Configure-5-2](../media/e54bc4c6-9ce1-4fa7-a158-68805fb345d2.png)
  
9. Use the same procedure to add the other SRV record, typing or copying and pasting the values from the second row in the table above, and then choosing **ADD** when you have completed the record. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

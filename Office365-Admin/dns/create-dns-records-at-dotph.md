---
title: "Create DNS records at dotPH for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_dotPH'
- 'O365M_DOM_dotPH'
- 'O365E_DOM_dotPH'
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
ms.assetid: 67dbe1d7-25a1-4505-9605-24537688e93e
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at dotPH for Office 365."
---

# Create DNS records at dotPH for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
> [!CAUTION]
> The dotPH website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at dotPH, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider. 
  
If you choose to manage your own Office 365 DNS records at dotPH despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.
  
    
After you add these records at dotPH, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at dotPH by using [this link](https://www.dot.ph/domain_manager). You'll be prompted to log in first.
    
    ![DotPH-BP-Configure-1-1](../media/c8fd1371-76bc-43b6-9a29-70f3c89fff4c.png)
  
2. On the **Registered Domains** page, in the **Domain** section, choose the name of the domain you are updating. 
    
    ![DotPH-BP-Configure-1-2](../media/6519b55b-4db9-4f22-b7dc-ee1cc00d6971.png)
  
3. In the **DNS Entries** area, choose **Add DNS Entries**.
    
    (You may need to scroll down.)
    
    ![DotPH-BP-Configure-1-3](../media/673d0260-5604-4435-be7f-5a47b655fd18.png)
  
4. In the boxes for the new record, type or copy and paste the following values.
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Domain**|**Type**|**Content**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |
   
   ![DotPH-BP-Verify-1-1](../media/bdfa16fe-ac27-4954-939e-86b68787ce14.png)
  
5. Choose **Add**.
    
    ![DotPH-BP-Verify-1-2](../media/251d74a3-7b1d-4de3-9401-bbae724f2782.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365

1. To get started, go to your domains page at dotPH by using [this link](https://www.dot.ph/domain_manager). You'll be prompted to log in first.
    
    ![DotPH-BP-Configure-1-1](../media/c8fd1371-76bc-43b6-9a29-70f3c89fff4c.png)
  
2. On the **Registered Domains** page, in the **Domain** section, choose the name of the domain you are updating. 
    
    ![DotPH-BP-Configure-1-2](../media/6519b55b-4db9-4f22-b7dc-ee1cc00d6971.png)
  
3. In the **DNS Entries** area, choose **Add DNS Entries**.
    
    (You may need to scroll down.)
    
    ![DotPH-BP-Configure-1-3](../media/673d0260-5604-4435-be7f-5a47b655fd18.png)
  
4. In the boxes for the new record, type or copy and paste the following values.
    
    (Select the **Type** value from the drop-down lists.) 
    
    |**Domain**|**Type**|**Weight**|**Content**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |MX  <br/> |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **NOTE:** Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)        <br/> |
   
   ![DotPH-BP-Configure-2-1](../media/a032d938-e69c-4039-a62e-8f0f159c458d.png)
  
5. Choose **Add**.
    
    ![DotPH-BP-Configure-2-2](../media/36517f66-a3f5-4200-9aeb-20a18320fd88.png)
  
6. If there are any other MX records listed in the **DNS Entries** section, delete them: 
    
    Begin by choosing the **trash can** icon for one of the other MX records. 
    
    ![DotPH-BP-Configure-2-3](../media/805cf25b-47a8-4cf5-bbb3-be897414e612.png)
  
7. In the confirmation dialog box, choose **OK** to confirm the deletion of that record. 
    
    ![DotPH-BP-Configure-2-4](../media/70049fa8-b3fe-429c-a7ec-2910e022febc.png)
  
8. Use the same two steps to delete any other MX records, until only the one that you created earlier in this procedure remains.
    
## Add the six CNAME records that are required for Office 365

1. To get started, go to your domains page at dotPH by using [this link](https://www.dot.ph/domain_manager). You'll be prompted to log in first.
    
    ![DotPH-BP-Configure-1-1](../media/c8fd1371-76bc-43b6-9a29-70f3c89fff4c.png)
  
2. On the **Registered Domains** page, in the **Domain** section, choose the name of the domain you are updating. 
    
    ![DotPH-BP-Configure-1-2](../media/6519b55b-4db9-4f22-b7dc-ee1cc00d6971.png)
  
3. In the **DNS Entries** area, choose **Add DNS Entries**.
    
    (You may need to scroll down.)
    
    ![DotPH-BP-Configure-1-3](../media/673d0260-5604-4435-be7f-5a47b655fd18.png)
  
4. Add the first of the six CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type** value from the drop-down list.) 
        
    |**Domain**|**Type**|**Content**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
      
    ![DotPH-BP-Configure-3-1](../media/47b85426-89d5-4793-8ae1-17e5b8e4e5ed.png)
  
5. Choose **Add**.
    
    ![DotPH-BP-Configure-3-2](../media/3101e34d-6a2e-4e7a-ab0f-7120d342f612.png)
  
6. Add the other five CNAME records.
    
    On the **Registered Domains** page, choose **Add DNS Entries** again, create a record using the values from the next row in the table, and then again choose **Add** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. To get started, go to your domains page at dotPH by using [this link](https://www.dot.ph/domain_manager). You'll be prompted to log in first.
    
    ![DotPH-BP-Configure-1-1](../media/c8fd1371-76bc-43b6-9a29-70f3c89fff4c.png)
  
2. On the **Registered Domains** page, in the **Domain** section, choose the name of the domain you are updating. 
    
    ![DotPH-BP-Configure-1-2](../media/6519b55b-4db9-4f22-b7dc-ee1cc00d6971.png)
  
3. In the **DNS Entries** area, choose **Add DNS Entries**.
    
    (You may need to scroll down.)
    
    ![DotPH-BP-Configure-1-3](../media/673d0260-5604-4435-be7f-5a47b655fd18.png)
  
4. In the boxes for the new record, type or copy and paste the following values.
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Domain**|**Type**|**Content**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **NOTE:** We recommend copying and pasting this entry, so that all of the spacing stays correct. <br/>           |
   
    ![DotPH-BP-Configure-4-1](../media/90075dd0-9e1d-4f9e-9b10-a5f3327dbeac.png)
  
5. Choose **Add**.
    
    ![DotPH-BP-Configure-4-2](../media/43c1b524-3457-49ac-9632-a439a40fbc55.png)
  
## Add the two SRV records that are required for Office 365

> [!CAUTION]
> The dotPH website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at dotPH, there are [Significant service limitations](../setup/domains-faq.md), and you might want to switch to a different DNS hosting provider. 
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

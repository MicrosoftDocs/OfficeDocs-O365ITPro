---
title: "Create DNS records at Melbourne IT for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_MIT'
- 'O365M_DOM_MIT'
- 'O365E_DOM_MIT'
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
ms.assetid: 52f7a42f-e49c-42ca-910f-9448625f30a0
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Melbourne IT for Office 365."
---

# Create DNS records at Melbourne IT for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Melbourne IT is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
    
After you add these records at Melbourne IT, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Follow the steps below or [watch the video (start at :51)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-Melbourne-IT-for-Office-365-255a7d5e-92b0-47bc-8ab8-51dad28414c2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![MelbourneIT-BP-Configure-1-3](../media/ca52e15f-beda-439f-a9ed-76c103b429cb.png)
  
4. In the **DNS** section, on the **DNS Status** row, choose **Manage Power DNS**.
    
    ![MelbourneIT-BP-Configure-1-4](../media/76dfbf8f-cc9d-4f14-a3aa-37972269e682.png)
  
5. Scroll down to the **TXT Records** section and, in the boxes for the new record, type or copy and paste the following values. 
    
    |**HOSTNAME**|**TXT VALUE**|
    |:-----|:-----|
    |Use your domain name.  <br/> Example: contoso.com.  <br/> **This value MUST end with a period (.)** <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MelbourneIT-BP-Verify-1-1](../media/9ac3a867-51ff-4e86-872e-d7813dea24cd.png)
  
6. Choose the **Add** button indicated in the following illustration. 
    
    ![MelbourneIT-BP-Verify-1-2](../media/d5a8e480-b2e2-44d4-89be-d65544122e97.png)
  
7. Choose **Edit** for the record that you have just created. 
    
    ![MelbourneIT-BP-Verify-1-3](../media/5260b33e-d169-49d0-b5dc-fe3ab9a387f3.png)
  
8. Select **3600** for the **TTL (SEC)** value. 
    
    ![MelbourneIT-BP-Verify-1-4](../media/a8a01807-4388-481f-a967-cb688953b7b4.png)
  
9. Choose **Update**.
    
    ![MelbourneIT-BP-Verify-1-5](../media/9d925e8f-ba87-41fd-927e-47010e064987.png)
  
10. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
<a name="BKMK_add_MX"> </a>

Follow the steps below or [watch the video (start at 4:03)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-Melbourne-IT-for-Office-365-255a7d5e-92b0-47bc-8ab8-51dad28414c2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![MelbourneIT-BP-Configure-1-3](../media/ca52e15f-beda-439f-a9ed-76c103b429cb.png)
  
4. In the **DNS** section, on the **DNS Status** row, choose **Manage Power DNS**.
    
    ![MelbourneIT-BP-Configure-1-4](../media/76dfbf8f-cc9d-4f14-a3aa-37972269e682.png)
  
5. Scroll down to the **MX Records** section. In the boxes for the new record, type or paste the following values. 
    
    |**HOSTNAME**|**ADDRESS**|**PRIORITY**|
    |:-----|:-----|:-----|
    |Use your domain name.  <br/> Example: contoso.com.  <br/> **This value MUST end with a period (.)** <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 account.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![MelbourneIT-BP-Configure-2-1](../media/84dfe64d-1998-4b3b-be86-fe55eea5ea7a.png)
  
6. Choose the **Add** button indicated in the following illustration. 
    
    ![MelbourneIT-BP-Configure-2-2](../media/0fff58e2-b409-450f-b60b-236ae146cf77.png)
  
7. Choose **Edit** for the record that you have just created. 
    
    ![MelbourneIT-BP-Configure-2-3](../media/e96729cd-36bc-45ff-b4db-5b72415be5ba.png)
  
8. Select **3600** for the **TTL (SEC)** value. 
    
    ![MelbourneIT-BP-Configure-2-4](../media/69a25d77-d35f-4b18-acc0-81f3a61f1995.png)
  
9. Choose **Update**.
    
    ![MelbourneIT-BP-Configure-2-5](../media/3c7b73b4-713b-4623-9367-35196e05ef81.png)
  
10. If there are any other existing MX records, delete each of them by choosing **Delete** in the row for that record. 
    
    ![MelbourneIT-BP-Configure-2-6](../media/1a10d94f-c9e6-4286-a86b-ff8dafd97db4.png)
  
11. Choose **OK** to confirm the deletion. 
    
    ![MelbourneIT-BP-Configure-2-7](../media/83485de0-e49c-4316-ae32-0fe386e4e14a.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

Follow the steps below or [watch the video (start at 4:57)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-Melbourne-IT-for-Office-365-255a7d5e-92b0-47bc-8ab8-51dad28414c2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![MelbourneIT-BP-Configure-1-3](../media/ca52e15f-beda-439f-a9ed-76c103b429cb.png)
  
4. In the **DNS** section, on the **DNS Status** row, choose **Manage Power DNS**.
    
    ![MelbourneIT-BP-Configure-1-4](../media/76dfbf8f-cc9d-4f14-a3aa-37972269e682.png)
  
5. Scroll down to the **A, CNAME, AAAA Records** section and create the first of the four required CNAME records. 
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Choose the **TYPE** value from the drop-down list.) 
    
    |**HOSTNAME**|**POINTS TO**|**TYPE**|
    |:-----|:-----|:-----|
    |autodiscover. ***domain_name***.  <br/> The "autodiscover" value must be added to the beginning of your domain name as a single string, and separated by a period.          For example:          autodiscover.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |CNAME  <br/> |
    |sip. ***domain_name***.  <br/> The "sip" value must be added to the beginning of your domain name as a single string, and separated by a period.          For example:          sip.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |CNAME  <br/> |
    |lyncdiscover. ***domain_name***.  <br/> The "lyncdiscover" value must be added to the beginning of your domain name as a single string, and separated by a period.          For example:          lyncdiscover.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |CNAME  <br/> |
    |msoid. ***domain_name***.  <br/> The "msoid" value must be added to the beginning of your domain name as a single string, and separated by a period.          For example:          msoid.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |CNAME  <br/> |
    |enterpriseregistration. ***domain_name***.  <br/> The "enterpriseregistration" value must be added to the beginning of your domain name as a single string, and separated by a period.          For example:          enterpriseregistration.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |CNAME  <br/> |
    |The "enterpriseenrollment" value must be added to the beginning of your domain name as a single string, and separated by a period.          For example:          enterpriseenrollment.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |CNAME  <br/> |
       
    ![MelbourneIT-BP-Configure-3-1](../media/c87425a2-bbe2-4fda-b628-e30d9f8d31ea.png)
  
6. Choose the **Add** button indicated in the following illustration to add the first record. 
    
    ![MelbourneIT-BP-Configure-3-2](../media/fba01fda-c2a8-490f-8f80-a65a83bb7a34.png)
  
7. Choose **Edit** for the record that you have just created. 
    
    ![MelbourneIT-BP-Configure-3-3](../media/b216219d-3020-48b5-95a2-e13cfc239cc2.png)
  
8. Select **3600** for the **TTL (SEC)** value. 
    
    ![MelbourneIT-BP-Configure-3-4](../media/b9ed06cc-a7ab-41d6-a499-44669b66c956.png)
  
9. Choose **Update**.
    
    ![MelbourneIT-BP-Configure-3-5](../media/b42dba30-ddf4-40f9-b139-1fe1c7ab5f4e.png)
  
10. Create the second CNAME record by using the same procedure.
    
    In the boxes for the second record, type or copy and paste the values from the second row of the table above, choose **Add** to add the record, choose **Edit** for the new record, set its **TTL (SEC)** value to **3600**, and then choose **Update**.
    
    Use the same process to add the remaining CNAME records, using the values from the third, fourth, fifth, and sixth rows of the table.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
Follow the steps below or [watch the video (start at 6:01)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-Melbourne-IT-for-Office-365-255a7d5e-92b0-47bc-8ab8-51dad28414c2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![MelbourneIT-BP-Configure-1-3](../media/ca52e15f-beda-439f-a9ed-76c103b429cb.png)
  
4. In the **DNS** section, on the **DNS Status** row, choose **Manage Power DNS**.
    
    ![MelbourneIT-BP-Configure-1-4](../media/76dfbf8f-cc9d-4f14-a3aa-37972269e682.png)
  
5. Scroll down to the **TXT Records** section. In the boxes for the new record, type or copy and paste the following values. 
    
    |**HOSTNAME**|**TXT VALUE**|
    |:-----|:-----|
    |Use your domain name.  <br/> Example: contoso.com.  <br/> **This value MUST end with a period (.)** <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![MelbourneIT-BP-Configure-4-1](../media/29fe8d56-cbbf-43a6-bf17-39407c7a2edc.png)
  
6. Choose the **Add** button indicated in the following illustration. 
    
    ![MelbourneIT-BP-Configure-4-2](../media/d4d9eee9-0ad4-489f-8cef-9a5488906ee3.png)
  
7. Choose **Edit** for the record that you have just created. 
    
    ![MelbourneIT-BP-Configure-4-3](../media/c7e19357-517f-460c-8548-e85c520b36bd.png)
  
8. Select **3600** for the **TTL (SEC)** value. 
    
    ![MelbourneIT-BP-Configure-4-4](../media/0619a9c5-4a40-480f-af38-24a9c6b1a4ad.png)
  
9. Choose **Update**.
    
    ![MelbourneIT-BP-Configure-4-5](../media/c3c680f5-0b2d-4930-9baf-f5f9c937147d.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

Follow the steps below or [watch the video (start at 6:47)](https://support.office.com/en-us/article/Video-Create-DNS-records-at-Melbourne-IT-for-Office-365-255a7d5e-92b0-47bc-8ab8-51dad28414c2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![MelbourneIT-BP-Configure-1-3](../media/ca52e15f-beda-439f-a9ed-76c103b429cb.png)
  
4. In the **DNS** section, on the **DNS Status** row, choose **Manage Power DNS**.
    
    ![MelbourneIT-BP-Configure-1-4](../media/76dfbf8f-cc9d-4f14-a3aa-37972269e682.png)
  
5. Scroll down to the **SRV Records** section and create the first of the two SRV records. 
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    |**Name**|**Priority**|**Port**|**Weight**|**Service**|**Protocol**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |Use your domain name.  <br/> Example: contoso.com.  <br/> **This value MUST end with a period (.)** <br/> |100  <br/> |443  <br/> |1  <br/> |_sip  <br/> |_tls  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |Use your domain name.  <br/> Example: contoso.com.  <br/> **This value MUST end with a period (.)** <br/> |100  <br/> |5061  <br/> |1  <br/> |_sipfederationtls  <br/> |_tcp  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![MelbourneIT-BP-Configure-5-1](../media/222807cb-55d9-4848-805d-eee7740b45fe.png)
  
6. Choose the **Add** button indicated in the following illustration to add the first record. 
    
    ![MelbourneIT-BP-Configure-5-2](../media/4d112a7b-68bd-4bc5-b199-83413c6611f0.png)
  
7. Choose **Edit** for the record that you have just created. 
    
    ![MelbourneIT-BP-Configure-5-3](../media/20d5923b-c6e0-46c8-b3d0-1a3b75edf5b5.png)
  
8. Select **3600** for the **TTL (SEC)** value. 
    
    ![MelbourneIT-BP-Configure-5-4](../media/20813ab0-b175-43bd-b240-672831638f9d.png)
  
9. Choose **Update**.
    
    ![MelbourneIT-BP-Configure-5-5](../media/36f2dd52-ae21-4cb7-9c70-a2ec5a8e80d3.png)
  
10. Create the second SRV record by using the same procedure.
    
    In the boxes for the second record, type or copy and paste the values from the second row of the table above, choose **Add** to add the record, choose **Edit** for the new record, set its **TTL (SEC)** value to **3600**, and then choose **Update**.
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 

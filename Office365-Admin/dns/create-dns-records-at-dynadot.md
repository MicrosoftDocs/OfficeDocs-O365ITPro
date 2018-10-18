---
title: "Create DNS records at Dynadot for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Dyna'
- 'O365M_DOM_Dyna'
- 'O365E_DOM_Dyna'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4d199a41-730f-4aac-bfd5-104727a4ab03
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Dynadot for Office 365."
---

# Create DNS records at Dynadot for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Dynadot is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-dynadot.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-dynadot.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-dynadot.md#BKMK_add_MX)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-dynadot.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-dynadot.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-dynadot.md#BKMK_add_SRV)
    
After you add these records at Dynadot, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose the **DNS** tab. 
    
    ![Dynadot-BP-Configure-1-4](../media/9f251ffa-569e-402c-ab97-1d5b24d88514.png)
  
4. In the **Domain Record (required)** section, find the boxes for the new record, and then type or copy and paste the values from the following table. 
    
    (Choose the **Record Type** value from the drop-down list.) 
    
|**Record Type**|**IP Address or Target Host**|
|:-----|:-----|
|TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![Dynadot-BP-Verify-1-1](../media/7be98776-f41d-4317-b93a-afccf72d6590.png)
  
5. Choose **Save DNS**.
    
    (You may have to scroll down.)
    
    ![Dynadot-BP-Verify-1-2](../media/13510279-3652-491d-be26-a3d527eeff2e.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose the **DNS** tab. 
    
    ![Dynadot-BP-Configure-1-4](../media/9f251ffa-569e-402c-ab97-1d5b24d88514.png)
  
4. In the **MX Records (optional)** section, find the boxes for the new record, and then type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
|**Mail Host**|**Distance**|
|:-----|:-----|
| *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Dynadot-BP-Configure-2-1](../media/d83422ba-8d89-43af-b503-e00854a22105.png)
  
5. If there are any other MX records, delete each one by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![Dynadot-BP-Configure-2-2](../media/64884b23-7e90-4e85-bdfd-cf65f0127150.png)
  
6. Choose **Save DNS**.
    
    ![Dynadot- BP-Configure-2-3](../media/fed6f374-9154-41ec-869c-50d874ad7dca.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose the **DNS** tab. 
    
    ![Dynadot-BP-Configure-1-4](../media/9f251ffa-569e-402c-ab97-1d5b24d88514.png)
  
4. In the **Subdomain Records (optional)** section, find the boxes for the four new records, and then type or copy and paste the values from the following table. 
    
    (Choose the **Record Type** value from the drop-down list.) 
    
|**Subdomain**|**Record Type**|**IP Address or Target Host**|
|:-----|:-----|:-----|
|autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
|sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
|lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
|msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
   ![Dynadot-BP-Configure-3-1](../media/e59bbaf7-ecab-4a12-893f-6f4a218f6dea.png)
  
5. When you have added the last CNAME record, choose **Save DNS**.
    
    (You may have to scroll down.)
    
    ![Dynadot-BP-Configure-3-2](../media/44dd2a14-8a9c-4570-ac22-cc1f598d4dd0.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose the **DNS** tab. 
    
    ![Dynadot-BP-Configure-1-4](../media/9f251ffa-569e-402c-ab97-1d5b24d88514.png)
  
4. In the **Domain Record (required)** section, find the boxes for the new record, and then type or copy and paste the values from the following table. 
    
    (Choose the **Record Type** value from the drop-down list.) 
    
|**Record Type**|**IP Address or Target Host**|
|:-----|:-----|
|TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![Dynadot-BP-Configure-4-1](../media/0e20d369-6dad-45b5-aa9f-3ba72ee7b3d8.png)
  
5. Choose **Save DNS**.
    
    (You may have to scroll down.)
    
    ![Dynadot-BP-Configure-4-2](../media/53cf2ab9-89e5-49e8-ba1f-20b9be94e176.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose the **DNS** tab. 
    
    ![Dynadot-BP-Configure-1-4](../media/9f251ffa-569e-402c-ab97-1d5b24d88514.png)
  
4. In the **Subdomain Records (optional)** section, find the boxes for the two new records, and then type or copy and paste the values from the following table. 
    
    (Choose the **Record Type** value from the drop-down list.) 
    
|**Subdomain**|**Record Type**|**IP Address or Target Host**|
|:-----|:-----|:-----|
|_sip._tls|SRV|100 1 443 sipdir.online.lync.com> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
|_sipfederationtls._tcp|SRV|100 1 5061 sipfed.online.lync.com> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![Dynadot-BP-Configure-5-1](../media/2d721f42-eafc-4bb7-b377-d18c84b36057.png)
  
5. Choose **Save DNS**.
    
    (You may have to scroll down.)
    
    ![Dynadot-BP-Configure-5-2](../media/fab75af5-65b2-4fae-94d5-9bdb9e76467d.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

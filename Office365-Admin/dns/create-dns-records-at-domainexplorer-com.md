---
title: "Create DNS records at DomainExplorer.com for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DE'
- 'O365M_DOM_DE'
- 'O365E_DOM_DE'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a45405b8-2c00-44a9-b29c-0c28d80bb4ef
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at DomainExplorer.com for Office 365."
---

# Create DNS records at DomainExplorer.com for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If DomainExplorer.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-domainexplorer-com.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-domainexplorer-com.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-domainexplorer-com.md#BKMK_add_MX)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-domainexplorer-com.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-domainexplorer-com.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-domainexplorer-com.md#BKMK_add_SRV)
    
After you add these records at DomainExplorer.com, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **Host Records** section, choose **Edit**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-1-3](../media/5a13170c-9b86-412e-9f74-63dbb5251ea7.png)
  
4. In the **Standard Host Names** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host Name**|**Type**|**Address**|
|:-----|:-----|:-----|
|@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![DomainExplorer-BP-Verify-1-2](../media/df68adf3-72ef-4823-bb35-5dc325365459.png)
  
5. Choose **Save Changes**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Verify-1-3](../media/2ec16974-c660-4a46-89a4-b4ba590cd9ee.png)
  
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

1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **MX Records** section, choose **Try It Now**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-2-1](../media/d77db3c1-f243-4f87-924e-9637a86aa81e.png)
  
4. In the **MX Record Settings** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
|**Host Name**|**Address**|**Pref**|
|:-----|:-----|:-----|
|@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![DomainExplorer-BP-Configure-2-2](../media/84d188e6-8762-44c8-ab7a-55b8b2a0510c.png)
  
5. Choose **Save Changes**.
    
    ![DomainExplorer-BP-Configure-2-3](../media/026d164f-014b-4bc3-b12b-2c9de7c4f2f2.png)
  
6. If there are any other existing MX records, delete them all by choosing **delete** for each record. 
    
    ![DomainExplorer-BP-Configure-2-4](../media/173d8fa4-414b-45af-86c2-d10e20b11d50.png)
  
7. If you have deleted any records, choose **Save Changes** again. 
    
    ![DomainExplorer-BP-Configure-2-3](../media/026d164f-014b-4bc3-b12b-2c9de7c4f2f2.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **Host Records** section, choose **Edit**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-1-3](../media/5a13170c-9b86-412e-9f74-63dbb5251ea7.png)
  
4. In the **Custom Host Names** section, in the boxes for the new records, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host Name**|**Type**|**Address**|
|:-----|:-----|:-----|
|autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
|sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
   ![DomainExplorer-BP-Configure-3-1](../media/0e0bf1ef-e5a5-42b4-802d-58ade75cf388.png)
  
5. Choose **Save Changes** to add rows, and then type or copy and paste the remaining values in the boxes for the new records. 
    
    ![DomainExplorer-BP-Configure-3-2](../media/25c0f3c1-80fa-4b30-9561-5f4eb184d8a2.png)
  
6. When you have added the last CNAME record, choose **Save Changes**.
    
    ![DomainExplorer-BP-Configure-3-3](../media/cf89bc55-8da8-4615-b21c-dfa8cf649c54.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **Host Records** section, choose **Edit**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-4-1](../media/2dec04a4-20b0-4864-9782-3fe92da1e815.png)
  
4. In the **Standard Host Names** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host Name**|**Type**|**Address**|
|:-----|:-----|:-----|
|@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![DomainExplorer-BP-Configure-4-1](../media/2dec04a4-20b0-4864-9782-3fe92da1e815.png)
  
5. Choose **Save Changes**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-4-2](../media/cc114d57-484d-4d26-815c-eeccb1d6b5f3.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **SRV Records** section, choose **Try It Now**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-5-1](../media/151a3a2a-8a02-44c8-bb8a-b89e4bf962f7.png)
  
4. In the boxes for the two new records, type or copy and paste the values from the following table.
    
|**Service**|**Protocol**|**Priority**|**Weight**|**Port**|**Target**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
|_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
   ![DomainExplorer-BP-Configure-5-2](../media/ba7c9374-01b1-4a1f-b234-f0ded3641185.png)
  
5. Choose **Save Changes**.
    
    ![DomainExplorer-BP-Configure-5-3](../media/443d8ca2-86ce-4f1b-8ea8-f33339c0de9b.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 


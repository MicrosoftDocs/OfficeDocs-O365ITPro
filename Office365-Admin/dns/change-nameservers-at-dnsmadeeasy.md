---
title: "Change nameservers to set up Office 365 with DNSMadeEasy"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DNSMadeEasy1'
- 'O365M_DOM_DNSMadeEasy1'
- 'O365E_DOM_DNSMadeEasy1'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4e015047-2520-4b31-988c-68c560373c8d
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at DNSMadeEasy."
---

# Change nameservers to set up Office 365 with DNSMadeEasy

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
With the exception of the first one, the procedures in this article must be performed at the domain registrar where you purchased your domain. This is because DNSMadeEasy is  *not*  a domain registrar, and you must manage nameservers at your domain registrar's site. 
  
Use the procedures in this article to add and set up your domain in Office 365 so that your services like email and Skype for Business Online will use your own domain name. To do this, you'll verify your domain, and then change your domain's name servers to Office 365 so that the correct DNS records can be set up for you.
  
Follow these procedures if at least one of the following three statements describes your situation:
  
- You have your own domain and want to set it up to work with Office 365.
    
- You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](create-dns-records-at-dnsmadeeasy.md).)
    
- Your domain is hosted at a DNS hosting provider or domain registrar that is not listed in the article [How to buy a domain name](../get-help-with-domains/buy-a-domain-name.md).
    
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-dnsmadeeasy.md#BKMK_NeedHelp).)
  
- [Delete your DNSMadeEasy domain](change-nameservers-at-dnsmadeeasy.md#BKMK_delete)
    
- [Add a TXT or MX record for verification](change-nameservers-at-dnsmadeeasy.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-dnsmadeeasy.md#BKMK_nameservers)
    
## Delete your DNSMadeEasy domain
<a name="BKMK_delete"> </a>

When you signed up for DNSMadeEasy, you added a domain by using the **Add Domains** process. 
  
The domain that you added was purchased from a separate domain registrar; DNSMadeEasy does not offer domain registration services. To verify and redelegate your domain to Office 365, you first need to remove that domain from your DNSMadeEasy **Domains** list. 
  
After you remove your domain from DNSMadeEasy, you will perform additional steps at the domain registrar where you purchased your domain.
  
1. To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to log in first.
    
2. On the **Management Console** page, in the **Recently Updated Domains** area, choose the domain that you want to update. 
    
    On the **Management Console** page, in the **Recently Updated Domains** area, choose the domain that you want to update. 
    
    ![DNSMadeEasy-BP-Configure-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. Choose **Delete Domain**.
    
    ![DNSMadeEasy-BP-Redelegate-1-1](../media/c26402a7-d229-45d0-a954-52dacbc82ccf.png)
  
4. In the text box in the confirmation dialog box, type the following word:
    
    **DELETE**
    
    > [!IMPORTANT]
    > The word must be typed in capital letters  *only*  , as shown. 
  
    ![DNSMadeEasy-BP-Redelegate-1-2](../media/c11868dd-337b-4cc4-814d-be7b81d774f8.png)
  
5. Still in the confirmation dialog box, choose **Submit**.
    
    ![DNSMadeEasy-BP-Redelegate-1-3](../media/1945eaba-65e3-4699-8c08-73f9950b3ee0.png)
  
## Add a TXT or MX record for verification
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> You must perform this procedure at the domain registrar where you purchased and registered your domain. 
  
You will create only one record in this procedure, either a TXT record or an MX record. TXT is the preferred record type, but some DNS hosting providers don't support that type, in which case you can create an MX record instead.
  
Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
 **Find the area on your DNS hosting provider's website where you can create a new record**
  
1. Sign in to your DNS hosting provider's website.
    
2. Choose your domain.
    
3. Find the page where you can edit DNS records for your domain.
    
 **Create the record**
  
1. If you create a **TXT** record, use these values: 
    
|**Record Type**|**Alias or Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |(Type or copy and paste either **@** or your  *domain_name*  .)  <br/> |MS=ms *XXXXXXXX*  <br/> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/> |Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.  <br/> |
   
2. If you create an **MX** record, use these values: 
    
|**Record Type**|**Alias or Host Name**|**Value**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|MX  <br/> |(Type or copy and paste either **@** or your  *domain_name*  .)  <br/> |MS=ms *XXXXXXXX*  <br/> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/> |For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.  <br/> |
   
3. Save the record.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

> [!IMPORTANT]
> You must perform this procedure at the domain registrar where you purchased and registered your domain. 
  
When you get to the last step of the domains setup wizard in Office 365, you have one task remaining: to set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary name servers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you.
  
You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.
  
To change your domain's name servers at your domain registrar's website yourself, follow these steps.
  
1. Find the area on the domain registrar's website where you can edit the nameservers for your domain.
    
2. Either create four nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values:
    
|||
|:-----|:-----|
|**First nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth nameserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
3. Save your changes.
    
> [!CAUTION]
>  When you change your domain's NS records to point to the Office 365 nameservers, all of the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise, this change could result in service downtime, such as lack of email access, or your current website being inaccessible. For example, here are some additional steps that might be required for email and website hosting: >  Move all email addresses that use your domain to Office 365  *before*  you change your NS records. >  Want to add a domain that's currently used with a website address, like www.fourthcoffee.com? You can take steps while you add the domain to keep its website hosted where the site is hosted now, so that people can still get to the website after you change the domain's NS records to point to Office 365. 
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

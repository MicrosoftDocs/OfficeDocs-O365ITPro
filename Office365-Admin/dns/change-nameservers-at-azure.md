---
title: "Change nameservers to set up Office 365 with Azure"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f136a1e5-d97f-4e26-b4c5-31cdbd5407df
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Azure."
---

# Change nameservers to set up Office 365 with Azure

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
The procedures in this article must be performed at the domain registrar where you purchased your domain. This is because Azure is not a domain registrar, and you must manage nameservers at your domain registrar's site.
  
Use the procedures in this article to add and set up your domain in Office 365 so that your services like email and Skype for Business Online will use your own domain name. To do this, you'll verify your domain, and then change your domain's name servers to Office 365 so that the correct DNS records can be set up for you.
  
Follow these instructions if at least one of the following three statements describes your situation.
  
- You have your own domain and want to set it up to work with Office 365.
    
- You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](create-dns-records-for-azure-dns-zones.md).
    
- Your domain is hosted at a DNS hosting provider or domain registrar that is not listed in the article [How to buy a domain name](../get-help-with-domains/buy-a-domain-name.md).
    
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-azure.md#BKMK_NeedHelp).)
  
- [Return your domain to your registrar's default nameservers](change-nameservers-at-azure.md#BKMK_Default)
    
- [Add a TXT or MX record for verification](change-nameservers-at-azure.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-azure.md#BKMK_nameservers)
    
## Return your domain to your registrar's default nameservers
<a name="BKMK_Default"> </a>

The domain that you added to Azure was purchased from a separate domain registrar; Azure does not offer domain registration services. To verify and redelegate your domain to Office 365, you first need to return your domain to your Domain Registrar's default nameservers.
  
After you return your domain to your registrar's default nameservers, you will perform additional steps at your domain registrar.
  
1. To get started, go to your domains page at your domain registrar. You'll be prompted to log in first.
    
2. Find the area on the domain registrar's website where you can edit the nameservers for your domain.
    
3. Choose the default nameserver option, and then save your changes.
    
    > [!NOTE]
    > Many domain registrars require you to select a custom nameserver option before you added the Azure nameserver records. The options for returning to the default nameservers vary; often there is option to explicitly choose the domain registrar's default nameservers instead. Alternatively, you may have to type or copy and paste the domain registrar's nameserver values into the nameserver boxes and then save those changes. 
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
## Add a TXT or MX record for verification
<a name="BKMK_verify"> </a>

> [!NOTE]
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
  
1. If you create a **TXT** record, use the values in the following table. 
    
|**Record Type**|**Alias or Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |(Type or copy and paste either ** @ ** or your  * **domain_name*** .)  <br/> |MS=ms *XXXXXXXX*  <br/> |Set this value to **1 hour** or to the equivalent in minutes **(60)**, sections **(3600)**, and so on.  <br/> |
   
2. If you create an **MX** record, use the values in the following table. 
    
|**Record Type**|**Alias or Host Name**|**Value**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|MX  <br/> |(Type or copy and paste either ** @ ** or your  * **domain_name*** .)  <br/> |MS=ms *XXXXXXXX*  <br/> |For **Priority**,,to avoid conflicts with the MX record used for mail flow, use a lower priority for any existing MX records.  <br/> |Set this value to **1 hour** or to the equivalent in minutes **(60)**, sections **(3600)**, and so on.  <br/> |
   
3. Save the record.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify button](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. Find the area on the domain registrar's website where you can edit the nameservers for your domain.
    
2. Either create two nameserver records by using the values in the following table, or edit the existing nameserver records to match the values in the following table.
    
|||
|:-----|:-----|
|**First nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. If there are any other name servers listed, you can either delete them or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**. 
  
3. Save your changes.
    
> [!IMPORTANT]
> When you change your domain's NS records to point to the Office 365 nameservers, all of the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise, this change could result in service downtime, such as lack of email access, or your current website being inaccessible. 
  
For example, here are some additional steps that might be required for email and website hosting.
  
- Move all email addresses that use your domain to Office 365 before you change your NS records. Learn more: Why should I add users to Office 365 while I'm adding my domain?
    
- Want to add a domain that's currently used with a website address, like www.fourthcoffee.com? You can take steps while you add the domain to keep its website hosted where the site is hosted now, so that people can still get to the website after you change the domain's NS records to point to Office 365.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

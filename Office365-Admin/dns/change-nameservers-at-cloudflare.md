---
title: "Change nameservers to set up Office 365 with Cloudflare"
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
ms.assetid: fb8b07ce-6d9d-4616-96f0-20b093911531

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Cloudflare."
---

# Change nameservers to set up Office 365 with Cloudflare

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
With the exception of the first one, the procedures in this article must be performed at the domain registrar where you purchased your domain. This is because Cloudflare is not a domain registrar, and you must manage nameservers at your domain registrar's site.
  
Use the procedures in this article to add and set up your domain in Office 365 so that your services like email and Skype for Business Online will use your own domain name. To do this, you'll verify your domain, and then change your domain's name servers to Office 365 so that the correct DNS records can be set up for you.
  
Follow these procedures if at least one of the following three statements describes your situation:
  
- You have your own domain and want to set it up to work with Office 365.
    
- You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](create-dns-records-at-cloudflare.md).
    
    Your domain is hosted at a DNS hosting provider or domain registrar that is not listed in the article [How to buy a domain name](../get-help-with-domains/buy-a-domain-name.md).
    
Here's what you need to do. (Need more help? [Get support](https://support.office.com/article/fb8b07ce-6d9d-4616-96f0-20b093911531e.aspx#BKMK_NeedHelp).)
  
- [Delete your Cloudflare domain](fb8b07ce-6d9d-4616-96f0-20b093911531.md#BKMK_delete)
    
- [Add a TXT or MX record for verification](fb8b07ce-6d9d-4616-96f0-20b093911531.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](fb8b07ce-6d9d-4616-96f0-20b093911531.md#BKMK_nameservers)
    
## Delete your Cloudflare domain
<a name="BKMK_delete"> </a>

When you signed up for Cloudflare, you added a domain by using the **Add Domains** process. 
  
The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services. To verify and redelegate your domain to Office 365, you first need to remove that domain from your Cloudflare **Website** list. 
  
After you remove your domain from Cloudflare, you will perform additional steps at the domain registrar where you purchased your domain.
  
1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.
    
    ![Cloudflare-BP-Configure-1-1](../media/e1ab6ca7-c36d-42ce-9e0a-5e1b0c0b234c.png)
  
2. On the **Overview** page, in the **Select Website** area, choose the domain that you want to update. 
    
    ![Cloudflare-BP-Configure-1-2](../media/7ecd4e8d-cbeb-4af2-81e9-51801ae169b5.png)
  
3. Choose **Overview**.
    
    ![Cloudflare-BP-Redelegate-1-1-1](../media/32604478-ae7b-460c-8999-e26d4aede787.png)
  
4. In the **Status: Active** section, choose **Advanced**.
    
    ![Cloudflare-BP-Redelegate-1-1-2](../media/6c559aaf-ec96-4610-b0c6-da4e46fbfe2e.png)
  
5. In the **Delete Website** section, choose **Delete**.
    
    ![Cloudflare-BP-Redelegate-1-2](../media/b00c296c-893c-4f4b-9ccc-c19e3529710c.png)
  
6. On the **Delete Website** dialog box, choose **Delete**.
    
    ![Cloudflare-BP-Redelegate-1-3](../media/f58ea101-100c-43c7-b9f7-0c3c2272b960.png)
  
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
  
1. If you create a **TXT** record, use the values in the following table. 
    
|**Record Type**|**Alias or Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |(Type or copy and paste either ** @ ** or your ** *domain_name* **.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Set this value to **1 hour** or to the equivalent in minutes ( **60**), sections ( **3600**), and so on.  <br/> |
   
2. If you create an **MX** record, use the values in the following table. 
    
|**Record Type**|**Alias or Host Name**|**Value**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|MX|(Type or copy and paste either ** @ ** or your ** *domain_name* **.) |MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority for any existing MX records.|Set this value to **1 hour** or to the equivalent in minutes ( **60**), sections ( **3600**), and so on.|
   
3. Save the record.
    
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
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

> [!IMPORTANT]
> You must perform this procedure at the domain registrar where you purchased and registered your domain. 
  
When you get to the last step of the domains setup wizard in Office 365, you have one task remaining: To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary name servers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you.
  
You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.
  
To change your domain's name servers at your domain registrar's website yourself, follow these steps.
  
1. Find the area on the domain registrar's website where you can edit the nameservers for your domain.
    
2. Either create nameserver records by using the values in the following table, or edit the existing nameserver records to match the values in the following table.
    
|||
|:-----|:-----|
|**First nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth nameserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
3. Save your changes.
    
> [!IMPORTANT]
> When you change your domain's NS records to point to the Office 365 nameservers, all of the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise, this change could result in service downtime, such as lack of email access, or your current website being inaccessible. 
  
For example, here are some additional steps that might be required for email and website hosting:
  
- Move all email addresses that use your domain to Office 365 before you change your NS records. Learn more: [Why should I add users to Office 365 while I'm adding my domain?](https://support.office.com/article/60253758-518f-4bd8-8ad9-c69de9ea535a.aspx)
    
- Want to add a domain that's currently used with a website address, like www.fourthcoffee.com? You can take steps while you add the domain to keep its website hosted where the site is hosted now, so that people can still get to the website after you change the domain's NS records to point to Office 365.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

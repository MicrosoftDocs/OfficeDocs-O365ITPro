---
title: "Change nameservers to set up Office 365 with Domain Monster"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fc46b19e-c84d-4941-bcc6-6a3ac95fb5d5
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Domain Monster."
---

# Change nameservers to set up Office 365 with Domain Monster

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Domain Monster](create-dns-records-at-domain-monster.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-domain-monster.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-domain-monster.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-domain-monster.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Manage DNS**.
    
    ![DomainMonster-BP-Configure-1-3](../media/1b9ed73e-1930-4075-a214-000ba0a5d18a.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record type** value from the drop-down list.) 
    
|**Record type**|**Hostname**|**Comment**|
|:-----|:-----|:-----|
|TXT  <br/> |(Leave this field blank.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![DomainMonster-BP-Verify-1-1](../media/32e7e4ef-f51b-44ed-b5ad-a1508a95e82b.png)
  
5. Choose **Add record**.
    
    ![DomainMonster-BP-Verify-1-2](../media/c959f008-0644-43f2-b50a-5cbdac289392.png)
  
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
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Name Servers &amp; Glue Records**.
    
    ![DomainMonster-BP-Redelegate-1-1](../media/ee3bbf05-c1db-463f-9f3c-ea5813aa856f.png)
  
4. Select **Use 3rd Party Name Servers**.
    
    (You may have to scroll down.)
    
    ![DomainMonster-BP-Redelegate-1-2](../media/d11bb75a-e6f7-4b9e-b482-1df368347f2d.png)
  
5. Still in the **Use 3rd Party Name Servers** section, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**Primary** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondary** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Tertiary** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quaternary** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![DomainMonster-BP-Redelegate-1-3](../media/978fcd4e-ab26-4dcc-ab27-ffcc3c228718.png)
  
6. Choose **Update Name Servers**.
    
    ![DomainMonster-BP-Redelegate-1-4](../media/2400f725-96cd-4467-9f2e-1ac6baa824d4.png)
  

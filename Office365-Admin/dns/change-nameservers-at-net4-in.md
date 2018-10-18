---
title: "Change nameservers to set up Office 365 with Net4.in"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Net41'
- 'O365M_DOM_Net41'
- 'O365E_DOM_Net41'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7fb7013d-ed6a-4a0f-a0d7-5a4e3fc16930
description: "Learn to set up your Office 365 custom domain with Net4.in if you want Office 365 to manage your DNS records."
---

# Change nameservers to set up Office 365 with Net4.in

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Net4.in](https://support.office.com/article/944b89b6-8cc5-441f-add2-6b14160773c5.aspx).)
  
Here's what you need to do. ([Still need help?](change-nameservers-at-net4-in.md#BKMK_NeedHelp))
  
- [Add a TXT record for verification](change-nameservers-at-net4-in.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-net4-in.md#BKMK_nameservers)
    
## Add a TXT record for verification

1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx). You'll be prompted to login.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **DNS** tab.
    
    ![Choose the DNS tab](../media/a02534d9-8307-47fc-a368-a939007adf37.png)
  
5. In the boxes for the new record in the **DNS Records:  *domain_name* ** section, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
    (Net4.in supplies the **Host** value automatically.) 
    
|**TTL**|**Type**|**Host**|**Data**|
|:-----|:-----|:-----|:-----|
|3600  <br/> (Once this value is set, it is automatically applied to all of the DNS records in the domain.)  <br/> |TXT  <br/> |(This value is supplied automatically by server.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![Enter DNS values](../media/38bf58d2-7371-452d-a3d2-ca43857eddd2.png)
  
6. Choose **Create**.
    
    ![Choose Create](../media/3574bcd0-ee5a-445a-b980-878f207bc3e3.png)
  
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.
  
1. To get started, go to your domains page at Net4.in by using [this link](https://www.net4.com/aspx/account/my-page.aspx). You'll be prompted to login.
    
    ![Log in on your domains page](../media/60b47c80-9aba-4ca0-993e-833ce23bd7a3.png)
  
2. On the **Domains** page, in the **My Services** area, choose **Domain Names**.
    
    ![Choose Domain Names](../media/a0f074d7-f467-4b2d-a2d4-650575b0aa34.png)
  
3. On the **My Domain Names** page, in the **Domain Name** column, choose the name of the domain that you're updating. 
    
    ![Choose the name of the domain](../media/ce0deb04-9481-40b8-bbbb-cbf7d46a1873.png)
  
4. On the **Manage My Services** page, choose the **Manage Domain** tab. 
    
    ![Net4-BP-Redelegate-1-1](../media/5925eae4-90b6-4187-8297-765af90dd00d.png)
  
5. In the **Name Server** row, choose **Manage**.
    
    ![Net4-BP-Redelegate-1-2](../media/7972c356-d4bf-49d0-a762-190d33516f07.png)
  
6. Create the first nameserver record.
    
    In the **Host Name** box on the **NS Change** page, type or copy and paste the value from the first row in the following table. 
    
|||
|:-----|:-----|
|**Host Name** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Host Name** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Net4-BP-Redelegate-1-3](../media/f38595ba-5403-4235-97ae-13bcd61e3a26.png)
  
7. Choose **Add**.
    
    ![Net4-BP-Redelegate-1-4](../media/9796773e-e5d3-4659-a024-21c097132f08.png)
  
8. Using the same process and the value from the second row in the table, create the second nameserver record.
    
9. If there are any nameservers listed other than the two that you have just created, delete each of them by choosing **Delete** in the **Delete** column for that record. 
    
    ![Net4-BP-Redelegate-1-5](../media/fa599169-8066-4214-a4a8-04de4b5c51b1.png)
  
10. Choose **Save Changes**.
    
    ![Net4-BP-Redelegate-1-6](../media/3712bc11-cdb7-46dd-81f2-982a050e77f7.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.

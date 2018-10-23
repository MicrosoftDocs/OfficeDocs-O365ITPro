---
title: "Change nameservers to set up Office 365 with Blacknight"
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
ms.assetid: 99a77a09-87fa-4d93-b5d6-ec25fc4cd3a1
description: "Learn how you can set up Office 365 to manage your DNS records at Blacknight. "
---

# Change nameservers to set up Office 365 with Blacknight

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Blacknight](create-dns-records-at-blacknight.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
    ![Blacknight-BP-Configure-1-3](../media/9a028259-5525-48e2-a071-8948de207fee.png)
  
4. Choose the **DNS** tab. 
    
    ![Blacknight-BP-Configure-1-4-1](../media/fe9bfd97-11aa-49b5-9bfa-e9d9a52ee98c.png)
  
5. Then choose **DNS Records**.
    
    ![Blacknight-BP-Configure-1-4-2](../media/efba13d7-d305-4b76-98cf-fe736304cea1.png)
  
6. Choose **Add New DNS Record**.
    
    ![Blacknight-BP-Configure-1-5](../media/9b843ca3-a1b5-411f-aecb-2d21fead5cb1.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** value from the drop-down list.) 
    
|||
|:-----|:-----|:-----|:-----|
|**DNS Record Type** <br/> |**Domain** <br/> |**Data** <br/> |**TTL** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> 
> [!NOTE] 
> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Select **Custom** and enter the value **3600**.  <br/> |
   
   ![Blacknight-BP-Verify-1-1](../media/b6c3c40b-d2ed-4efe-95ad-1213d57aae94.png)
  
8. Choose **Finish**.
    
    ![Blacknight-BP-Verify-1-2](../media/0cd9134d-bbfa-41a3-913a-d0a223ec6ae4.png)
  
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
1. To get started, go to your domains page at Blacknight by using [this link](https://cp.blacknight.com/servlet/Turbine/frm/single/). You'll be prompted to login first.
    
    ![Blacknight-BP-Configure-1-1](../media/c403a577-083f-4fbf-98dd-4d2ee098902d.png)
  
2. In the **Domains** section, choose **Registered Domains**.
    
    ![Blacknight-BP-Configure-1-2](../media/892979d4-6f98-47d7-9131-3d372249b2bd.png)
  
3. Under **Registered Domains**, locate the domain that you want to edit, and then choose ** *domain_name* **. 
    
    ![Blacknight-BP-Redelegate-1-1](../media/e226363c-7619-4aec-8528-be7147d4c2da.png)
  
4. On the **Name Servers** section, choose **Manage Nameservers**.
    
    ![Blacknight-BP-Redelegate-1-2](../media/90107d0c-c81d-410c-9a4b-ac8bde5fb905.png)
  
5. In the **Domain Name Servers** section, delete each nameserver by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![Blacknight-BP-Redelegate-1-3](../media/3c2d7009-0b0c-4cbd-b86b-ffd0d00ec4c0.png)
  
6. In the boxes in the **Domain Name Servers** section, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**Primary Name Server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondary Name Server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third Name Server** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth Name Server** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Blacknight-BP-Redelegate-1-4](../media/f809aba0-5c6c-4b1f-a7dd-77e0c2a3393e.png)
  
7. Choose **Update Name Server**.
    
    ![Blacknight-BP-Redelegate-1-5](../media/c45f6b18-115b-45d0-b4b2-ce6fed9519a4.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

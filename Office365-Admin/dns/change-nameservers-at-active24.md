---
title: "Change nameservers to set up Office 365 with Active24"
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
ms.assetid: 1637461a-74dc-4a1d-8cf8-606bd8684bd9
description: "Learn how you can set up Office 365 to manage your DNS records at Active24. "
---

# Change nameservers to set up Office 365 with Active24

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Active24](create-dns-records-at-active24.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-active24.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-active24.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-active24.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:  *domain_name* **, choose **DNS administration**.
    
    ![Active24-BP-Configure-1-3](../media/0220173b-f73d-4659-a7d1-6f607afbb6d8.png)
  
4. On the **Customer center** page, in the **Add record** section, choose **TXT**.
    
    ![Active24-BP-Verify-1-1](../media/1e2afb98-af1d-494d-aad8-42ea3c29a675.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Name**|**TTL**|**Text**|
|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Active24-BP-Verify-1-2](../media/ce5bc8bf-2809-4fe4-bcb8-2a281247ce35.png)
  
6. Choose **Create**.
    
    ![Active24-BP-Verify-1-3](../media/1f9c5de8-6360-435a-9d74-5045b0041660.png)
  
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
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:** ** *domain_name* **, choose **Change of nameservers**.
    
    ![Active24-BP-Redelegate-1-1](../media/04db63e4-9641-4b2f-af50-151635799f09.png)
  
4. In the **Nameservers** section, choose **change**.
    
    (You may have to scroll down.)
    
    ![Active24-BP-Redelegate-1-2](../media/3b80c182-a4e0-4dbc-820d-cce1251c37e8.png)
  
5. In the **Nameservers** section, delete each nameserver by selecting it and then pressing the **Delete** key on your keyboard. Next, delete each Ipv4 value by selecting it and then pressing the **Delete** key on your keyboard. 
    
    (You may have to scroll down.)
    
    ![Active24-BP-Redelegate-1-3](../media/2887993a-ff6d-4e3d-a0da-7ec5f6be45c9.png)
  
6. Still in the **Nameservers** section, in the **Nameserver1** to **Nameserver4** boxes, type or copy and paste the values from the following table. 
    
|**Nameservers**|**Hostame**|**Ipv4**|
|:-----|:-----|:-----|
|**Nameserver1**|
|:-----|
|**Nameserver2**|
|:-----|
|**Nameserver3**|
|:-----|
|**Nameserver4**|
|:-----|
   
    ![Active24-BP-Redelegate-1-4](../media/374aad76-a104-48ab-ab87-5cb939999c58.png)
  
7. Choose **Save**.
    
    ![Active24-BP-Redelegate-1-5](../media/0e35ec67-7c3f-4d87-add2-22bdcd01435d.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


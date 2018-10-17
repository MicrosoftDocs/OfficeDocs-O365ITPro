---
title: "Change nameservers to set up Office 365 with OVH"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3facbada-b4f5-42b5-a258-94ee2083e9c2
description: "Learn to set up your Office 365 custom domain with OVH if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with OVH

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.
  
(Need more help? [Still need help?](change-nameservers-at-1-1-internet.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-ovh.md#bkmk_txt)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-ovh.md#bkmk_ns)
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. ﻿To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domains**, choose the name of the domain that you want edit.
    
    ![OVH select a domain](../media/275315de-a457-430c-bb01-99304481d869.png)
  
3. Choose **DNS zone**.
    
    ![OVH select DNS zone](../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Choose **Add an entry**.
    
    ![OVH Add an entry](../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Choose **TXT**.
    
    ![OVH choose TXT entry](../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. To assign a TTL value, select **Personalized**from the drop-down list, and then type the value in the text box.
    
|**﻿Record type**|**Sub-domain**|**TTL**|**Value**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |(leave blank)  <br/> |3600 (seconds)  <br/> |MS=msxxxxxxxx  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)
   
7. Choose **Confirm**.
    
    ![OVH confirm TXT for verification](../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**. The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.
  
1. ﻿To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![OVH login](../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domains**, choose the name of the domain that you want edit.
    
3. Under the **DNS servers** tab, you'll see your current NS servers. By default, they are something like:  *ns108.ovh.net*  and  *dns108.ovh.net*.
    
4. Click the **Modify DNS servers** button to enter edit mode, and replace the server names with the following: 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
5. Click **Apply configuration** to save. 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
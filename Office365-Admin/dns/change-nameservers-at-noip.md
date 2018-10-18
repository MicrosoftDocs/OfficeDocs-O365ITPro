---
title: "Change nameservers to set up Office 365 with NoIP"
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
ms.assetid: aa41cab1-f190-4504-9bb5-1f83b7ef53ce
description: "Learn to set up your Office 365 custom domain with NoIP if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with NoIP

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at NoIP](create-dns-records-at-noip.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-noip.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-noip.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-noip.md#BKMK_nameservers)
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Modify** for the domain that you want to edit. 
    
    > [!IMPORTANT]
    > Choose the naked domain, without prefixes such as "ftp", "mail", or "www". 
  
    ![NoIP-BP-Configure-1-2](../media/d964404e-d5c9-4be7-a060-e48bf8099b3d.png)
  
3. In the **Hostname Information** section, in the **Advanced Records** row, choose **TXT**.
    
    ![NoIP-BP-Verify-1-1](../media/cf8ef84a-fea8-4036-8127-d965a2d91253.png)
  
4. In the **TXT record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
|**TXT Record**|
|:-----|
|MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)
    
    
![NoIP-BP-Verify-1-2](../media/3a7b6740-794c-4b3b-a140-518e1f04fa2a.png)
  
5. Choose **Submit**.
    
    ![NoIP-BP-Verify-1-3](../media/da3030b8-5e0f-4ba1-bb8b-2272eaa38cd4.png)
  
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

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**. The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.
  
1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Domain Registration**.
    
    ![NoIP-BP-Redelegate-1-1](../media/370cc2f0-9aae-472a-b3d5-5ac49df2922a.png)
  
3. On the **Domain Registration** page, choose **Configure** for the domain you want to edit. 
    
    ![NoIP-BP-Redelegate-1-2](../media/51354895-0f81-4fa7-8aa6-4afe65007b17.png)
  
4. Choose **Custom** from the **Nameserver Set** drop-down list. 
    
    ![NoIP-BP-Redelegate-1-3](../media/3f1fc3a2-ba90-4bc8-9a45-75941f2a92af.png)
  
5. Type or copy and paste the values from the following table in the empty boxes.
    
|||
|:-----|:-----|
|**First empty box** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second empty box** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Third empty box** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fourth empty box** <br/> |ns4.bdm.microsoftonline.com  <br/> |
    
![NoIP-BP-Redelegate-1-4](../media/2249d718-c4b0-4dfd-9fc7-2c9cd1afab3f.png)
  
6. Choose **Set Nameservers**.
    
    ![NoIP-BP-Redelegate-1-5](../media/7c2972c9-4656-43b5-bf25-34938536674a.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 

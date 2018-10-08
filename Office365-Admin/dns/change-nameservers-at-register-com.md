---
title: "Change nameservers to set up Office 365 with Register.com"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 5/2/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Reg1'
- 'O365M_DOM_Reg1'
- 'O365E_DOM_Reg1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 65196b80-bbb6-42b6-b920-058349963c37

description: "Learn to set up your Office 365 custom domain with Register.com if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Register.com

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Register.com](create-dns-records-at-register-com.md).)
  
Here's what you need to do. Follow the steps below or [watch the video](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Register-com-eeb5935f-52bf-4f8d-8cc5-8d6899b07d4b?ui=en-US&amp;rs=en-US&amp;ad=US). (Need more help? [Still need help?](change-nameservers-at-register-com.md#BKMK_NeedHelp).)
  
- [Add a TXT record at Register.com to verify that you own the domain](change-nameservers-at-register-com.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-register-com.md#BKMK_nameservers)
    
## Add a TXT record at Register.com to verify that you own the domain
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Follow the steps below or [watch the video (start at 0:43)](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Register-com-eeb5935f-52bf-4f8d-8cc5-8d6899b07d4b?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.
    
2. Choose **Domains**.
    
3. Choose **Manage**.
    
4. Find the row that contains the name of the domain that you want to modify, and then, in that row, choose **Manage**.
    
5. Scroll down to the **Advanced Technical Settings** section, and then choose **Edit TXT Records (SPF)**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**Host Name** <br/> |**TXT Record** <br/> |
|@  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Choose **Continue**.
    
8. On the next page, choose **Continue** again to confirm your changes. 
    
9. Wait a few minutes before you continue so that the record you just created can update across the Internet.
    
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

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain.*  com) will start coming to Office 365 after you make this change. 
  
Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:53)](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Register-com-eeb5935f-52bf-4f8d-8cc5-8d6899b07d4b?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: 
  
1. To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.
    
2. Choose **Domains**.
    
3. Choose **Manage**.
    
4. Find the row that contains the name of the domain that you want to modify; and then, in that row, choose **Manage**.
    
5. Scroll to the **Domain Name System Servers (DNS Servers)** section. 
    
    In the first two boxes in the **New DNS Server** column, type or copy and paste the values in the first two rows of the following table. 
    
|||
|:-----|:-----|
|First row  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second row  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third row  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth row  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Register-BP-Redelegate-1-1](../media/037e14af-0468-42d8-9fa0-adfd3ce6ada6.png)
  
6. Choose **Continue**.
    
    ![Register-BP-Redelegate-1-2](../media/4227a889-e8bf-4be5-a8b8-798d166e04a5.png)
  
7. On the next page, choose **Continue** again to confirm and save your changes. 
    
    ![Register-BP-Redelegate-1-3](../media/929413a5-bfff-4e8a-8e96-18d0f1d10bbe.png)
  
8. The four nameservers that you have added should now be the only nameservers in the list.
    
    ![Register-BP-Redelegate-1-4](../media/5618e0a2-ef28-4795-b2d3-2f8df9f4077b.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
## Still need help?
<a name="BKMK_NeedHelp"> </a>

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


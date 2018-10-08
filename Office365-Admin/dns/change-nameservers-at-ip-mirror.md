---
title: "Change nameservers to set up Office 365 with IP Mirror"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 5/2/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_IPMirror1'
- 'O365M_DOM_IPMirror1'
- 'O365E_DOM_IPMirror1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9e3d5d4c-ee47-4003-8c4c-fe365f25eb66

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at IP Mirror."
---

# Change nameservers to set up Office 365 with IP Mirror

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at IP Mirror](create-dns-records-at-ip-mirror.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-ip-mirror.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-ip-mirror.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-ip-mirror.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at IP Mirror by using [this link](https://customer.ipmirror.com/cctldbox/). You'll be prompted to log in first.
    
2. In the **Manage Domain** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
5. On the **Domain Properties** page, choose **Edit DNS Record**.
    
6. On the **Edit DNS Record** page, at the top of the **Domain** section, check the value in the **TTL** box. 
    
    If the **TTL** value is not already set to **300**, then set it to **300** now. (This value is set only once, and it is applied to all of your DNS records for IP Mirror.) 
    
7. Still on the **Edit DNS Record** page, in the **TXT Records** section, choose the **Host +** icon. 
    
    (You may have to scroll down.) 
    
8. In the **TXT Records** section, in the boxes for the new record, type or copy and paste the following values. 
    
|||
|:-----|:-----|
|**Host** <br/> |**Description** <br/> |
|(Leave this field empty.)  <br/> |MS= *msXXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
9. Choose **Save**.
    
    (You may have to scroll down.)
    
10. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. To get started, go to your domains page at IP Mirror by using [this link](https://customer.ipmirror.com/cctldbox/). You'll be prompted to log in first.
    
2. In the **Manage Domain** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
5. On the **Domain Properties** page, choose **Change Nameserver**.
    
    ![ipMirror-BP-Redelegate-1-1](../media/285fb407-4bb8-468d-b708-373c064600f9.png)
  
6. On the **Change Nameserver** page, in the **Nameservers** area, delete each unwanted nameserver currently listed by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![ipMirror-BP-Redelegate-1-2](../media/412b0845-6745-4626-a74d-5502246b8457.png)
  
7. Still in the **Nameservers** area, if the correct nameservers are not already listed, type or copy and paste the values from the following table in the **Nameserver 1** through **Nameserver 4** boxes. 
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![ipMirror-BP-Redelegate-1-3](../media/2d244f67-46c5-434a-b1ec-fc90915e9d6e.png)
  
8. Choose **Next**.
    
    ![ipMirror-BP-Redelegate-1-4](../media/2f813dd4-d7f7-428c-a5c2-51cbd5663663.png)
  
9. Review your updates, and then choose **Proceed**.
    
    ![ipMirror-BP-Redelegate-1-6](../media/3fe35a90-db5b-4076-838c-395737e26c38.png)
  
10. Choose **Done**.
    
    ![ipMirror-BP-Redelegate-1-7](../media/f15edbfa-b004-4912-a318-fc768f8df2b7.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
## Still need help?
<a name="BKMK_NeedHelp"> </a>

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


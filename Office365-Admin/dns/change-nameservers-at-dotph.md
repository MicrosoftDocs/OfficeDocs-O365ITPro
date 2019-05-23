---
title: "Change nameservers to set up Office 365 with dotPH"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_dotPH1'
- 'O365M_DOM_dotPH1'
- 'O365E_DOM_dotPH1'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d7ed2a40-a724-47da-b42c-ae526c8ff5c1
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at dotPH."
---

# Change nameservers to set up Office 365 with dotPH

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at dotPH](create-dns-records-at-dotph.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at dotPH by using [this link](https://www.dot.ph/domain_manager). You'll be prompted to log in first.
    
2. On the **Registered Domains** page, in the **Domain** section, choose the name of the domain you are updating. 
    
3. 3.In the **DNS Entries** area, choose **Add DNS Entries**.
    
    (You may need to scroll down.)
    
4. In the boxes for the new record, type or copy and paste the following values.
    
    (Select the Type value from the drop-down list.)
    
||||
|:-----|:-----|:-----|
|**Domain** <br/> |**Type** <br/> |**Content** <br/> |
|(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)<br/>    |
   
5. Choose **Add**.
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. in the Microsoft 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the ** Verify domain ** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see[ Find and fix issues after adding your domain or DNS records in Office 365 ](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these three: 
  
> [!NOTE]
> DotPH limits support to three custom nameservers. 
  
1. To get started, go to your domains page at dotPH by using [this link](https://www.dot.ph/domain_manager). You'll be prompted to log in first.
    
2. On the **Registered Domains** page, in the **Domain** section, choose the name of the domain you are updating. 
    
3. In the **NameServers** section, choose **edit**.
    
    (You may have to scroll down.)
    
    ![DotPH-BP-Redelegate-1-1](../media/49fd3b39-07c3-4af0-bbf3-72f379515d7d.png)
  
4. In the **Select nameservers** area, choose **Use Own Nameservers**.
    
    ![DotPH-BP-Redelegate-1-2](../media/0e162a78-6c3a-492d-aeb6-43ca665b43a5.png)
  
5. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).
    
### If there are NO nameservers already listed

1. In the boxes in the **Select nameservers** area, type or copy and paste the values from the following table. 
    
|||||
|:-----|:-----|:-----|:-----|
||**Enter Nameserver** <br/> |**Enter IPv4 Address** <br/> |**Enter IPv6 Address** <br/> |
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |207.46.15.59  <br/> |(Leave this field empty.)  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |157.56.81.41  <br/> |(Leave this field empty.)  <br/> |
|**Nameserver 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |191.232.83.138  <br/> |(Leave this field empty.)  <br/> |
|||
   
   ![DotPH-BP-Redelegate-1-3](../media/40590b1a-1c03-499b-ab5f-ed3af4252fc7.png)
  
2. Choose **Save Changes.**
    
    ![DotPH-BP-Redelegate-1-4](../media/b1f84761-c552-4fcd-bf17-0d140da89a72.png)
  
3. Choose **Proceed**.
    
    ![DotPH-BP-Redelegate-1-6](../media/51d46d06-125d-4791-9a8c-1e8477f658d7.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, or **ns3.bdm.microsoftonline.com**.) 
  
1. If there are any other nameservers listed in the **Select nameservers** area, delete each one by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![DotPH-BP-Redelegate-1-5](../media/14b44375-902c-4a21-8504-6da98c8ca748.png)
  
2. In the boxes in the same area, type or copy and paste the values from the following table.
    
|||||
|:-----|:-----|:-----|:-----|
||**Enter Nameserver** <br/> |**Enter IPv4 Address** <br/> |**Enter IPv6 Address** <br/> |
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |207.46.15.59  <br/> |(Leave this field empty.)  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |157.56.81.41  <br/> |(Leave this field empty.)  <br/> |
|**Nameserver 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |191.232.83.138  <br/> |(Leave this field empty.)  <br/> |
|||
   
   ![DotPH-BP-Redelegate-1-3](../media/40590b1a-1c03-499b-ab5f-ed3af4252fc7.png)
  
3. Choose **Save Changes.**
    
    ![DotPH-BP-Redelegate-1-4](../media/b1f84761-c552-4fcd-bf17-0d140da89a72.png)
  
4. Choose **Proceed**.
    
    ![DotPH-BP-Redelegate-1-6](../media/51d46d06-125d-4791-9a8c-1e8477f658d7.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 


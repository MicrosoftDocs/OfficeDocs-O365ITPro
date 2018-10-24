---
title: "Change nameservers to set up Office 365 with Whiz.in"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Whiz1'
- 'O365M_DOM_Whiz1'
- 'O365E_DOM_Whiz1'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2bb31273-2534-4a54-8922-bd167654635f
description: "Learn to set up your Office 365 custom domain with Whiz.in if you want Office 365 to manage your DNS records.  "
---

# Change nameservers to set up Office 365 with Whiz.in

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Whiz.in](create-dns-records-at-whiz-in.md).)
  
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. In the **Manage Orders** drop down, choose **List/Search Orders**.
    
    ![WhizIn-BP-Configure-1-2](../media/9c9202b1-2463-40a1-ad0f-5e7800e70d6b.png)
  
3. On the **List of Orders** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Configure-1-3](../media/3c241f4f-2ce1-4286-90a2-959a40761b7e.png)
  
4. In the **DNS Management** section, choose **Manage DNS**.
    
    (You may need to scroll down.)
    
    ![WhizIn-BP-Configure-1-4](../media/f94b8ccc-e677-4825-b432-fc26781e1596.png)
  
5. In the **Manage Records for** ** *domain_name* ** section, choose the **TXT Records** tab. 
    
    ![WhizIn-BP-Verify-1-1-1](../media/541c2f15-cebf-472b-80c6-a4312fb65f10.png)
  
6. In the **List of TXT Records** area, choose **Add TXT Record**.
    
    ![WhizIn-BP-Verify-1-1-2](../media/1cdd1e12-da95-421c-ab9a-29ad317cbeae.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|
|@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |7200  <br/> |
   
   ![WhizIn-BP-Verify-1-2](../media/8310a995-a796-4ee4-bbe0-1cee5571ff6d.png)
    
  
8. Choose **Add Record**.
    
    ![WhizIn-BP-Verify-1-3](../media/e0bb42b9-733e-4a51-8aec-a2a7c89f855b.png)
  
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
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**. The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. Choose the **Manage Orders** tab, and then choose **List/Search Orders**.
    
    ![WhizIn-BP-Redelegate-1-1](../media/d673fd3c-1b93-4c9b-a27e-f1fdbbb914a8.png)
  
3. On the **List of Orders** page, in the **Domain Name** column, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Redelegate-1-2](../media/da372b8e-c0f5-4595-82e6-237a4588d9ca.png)
  
4. Choose **Name Servers**.
    
    ![WhizIn-BP-Redelegate-1-3](../media/f447dfa7-e765-4cea-a66c-8042980f15ab.png)
  
    > [!CAUTION]
    > Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
    In the **Manage Name Servers** section, delete each nameserver in the list by selecting that nameserver and then pressing the **Delete** key on your keyboard. 
    
    ![WhizIn-BP-Redelegate-1-4](../media/310243be-8b29-464f-a9d0-23a49846c2de.png)
  
5. In the **Name Server 1** to **Name Server 4** boxes, type or copy and paste the Office 365 nameserver values from the following table. 
    
    |||
    |:-----|:-----|
    |**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
    |**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
    |**Name Server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
    |**Name Server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
    ![WhizIn-BP-Redelegate-1-5](../media/96c2d2d4-c254-416e-b41c-06dbabafe56f.png)!
  
6. Choose **Update Name Servers**.
    
   ![WhizIn-BP-Redelegate-1-6](../media/a059851e-6783-4a15-9c38-83c28975c24f.png)
  
    > [!NOTE]
    > Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
  
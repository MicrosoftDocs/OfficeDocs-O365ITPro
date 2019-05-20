---
title: "Change nameservers to set up Office 365 with Dyn.com"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Nett1'
- 'O365P_DOM_DynCom1'
- 'O365M_DOM_Nett1'
- 'O365M_DOM_DynCom1'
- 'O365E_DOM_Nett1'
- 'O365E_DOM_DynCom1'
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
ms.assetid: 8b2e3bca-c11b-4c10-a6d0-cdc09a83ccb9
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Dyn.com."
---

# Change nameservers to set up Office 365 with Dyn.com

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Dyn.com](create-dns-records-at-dyn-com.md).)
  
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. On the **Zone Level Services** page, choose **Dyn Standard DNS Service** for the domain that you want to edit . 
    
3. On the **DNS** page for your domain, choose **Preferences**.
    
4. Choose **Enable Expert Interface**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
|**Host**|**TTL**|**Type**|**Data**|
|:-----|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.       [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/>   |
   
   ![Dyn-BP-Verify-1-1](../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. Choose **Create Record**.
    
    ![Dyn-BP-Verify-1-2](../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    
  
3. On the **Setup** page, choose **Start setup**.
    
    
  
4. On the **Verify domain** page, choose **Verify**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.
    
    ![Dyn-BP-Configure-1-1](../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. On the **Zone Level Services** page, choose **Domain Registration** for the domain that you want to edit. 
    
    ![Dyn-BP-Redelegate-1-1](../media/f158b33a-d948-4a56-858d-a5b0ad0a8b26.png)
  
3. On the **Domain Name Registration** page, choose **Edit Nameservers**.
    
    ![Dyn-BP-Redelegate-1-2](../media/a9f8c83e-b6d9-42ee-b9d0-a6474d12f300.png)
  
4. On the **Domain** page, in the **Nameservers:** box, delete the default nameservers by selecting them and then pressing the **Delete** key on your keyboard. 
    
    ![Dyn-BP-Redelegate-1-3](../media/35ba82c9-293f-46a2-b67c-20f3e80d4c4c.png)
  
5. Still in the **Nameservers:** box, type or copy and paste the **line 1** nameserver value from the following table, and then press **Enter** on your keyboard to create a new line. 
    
    Then type or copy and paste the **line 2** nameserver value from the table into the new line. Repeat this procedure to add the **line 3** and **line 4** nameserver values. 
    
|||
|:-----|:-----|
|**line 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**line 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**line 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**line 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Dyn-BP-Redelegate-1-4](../media/84ee68f0-ac1c-4364-b749-cb979a02ba33.png)
  
6. Choose **Save Nameservers**.
    
    ![Dyn-BP-Redelegate-1-5](../media/63b2d50f-8623-4404-af58-0ac9bb64ab54.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 


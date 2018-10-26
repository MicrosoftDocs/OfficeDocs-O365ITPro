---
title: "Change nameservers to set up Office 365 with Aabaco Small Business"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Aabaco1'
- 'O365M_DOM_Aabaco1'
- 'O365E_DOM_Aabaco1'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: 0acc30f5-7513-4586-b6d4-38ff78d3f95b
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain with Aabaco Small Business."
---

# Change nameservers to set up Office 365 with Aabaco Small Business

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.
  
    
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
> [!IMPORTANT]
   > Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
   To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
2. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
3. On the **Domain Control Panel** page, in the **TXT Records** section, choose **Add**.
    
    ![Click Add on the Domain Control Panel page](../media/b5814c15-3457-4e72-b2d8-5ee1622d8f83.png)
  
4. On the **Add TXT Record** page, in the boxes for the new record, type or copy and paste the values from the following table. 
    
|**Hostname:**|**Text:**|
|:-----|:-----|
|@  <br/> |MS=ms *XXXXXXXX*  <br/> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/> |
   
   ![Type or paste the DSN values on the Add TXT Record page](../media/ae8386df-6cec-4bbe-a280-9d3fc170d972.png)
  
5. Choose **Add**.
    
    ![Click Add](../media/3fa1c496-a07d-46c2-babd-027aa8c276ac.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md)
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
> [!IMPORTANT]
  > Before you begin this procedure, make sure that you are logged out of any other Aabaco accounts that you may have. 
  
 To get started, go to your domains page at Aabaco Small Business by using [this link](https://www.luminate.com/services/). You'll be prompted to sign in first.
    
2. On the **My Services** page, in the section for the domain you're working with, choose **Domain**.
    
3. On the **Domain Control Panel** page, in the **Name Servers** section, choose **Change**.
    
    ![Click Change on the Domain Control Panel page](../media/6d77c451-0614-4717-be58-46884491ef9e.png)
  
4. On the **Update Name Servers** page, delete each of the nameservers currently listed by selecting it and then pressing the **Delete** key on your keyboard. 
    
    > [!CAUTION]
    > Perform these deletions  *only*  if you have existing nameservers that do not point to Office 365 . (For example, you would delete nameservers named **yns1.yahoo.com** or **ns1.contoso.com**, but  *not*  delete nameservers named **ns1.bdm.microsoftonline.com** or **ns2.bdm.microsoftonline.com** ). 
  
    ![Delete the nameservers on the Update Name Servers page](../media/46997847-099d-49c4-a07b-f1e0f09ff407.png)
  
5. In the **Enter Primary Name Server** and **Enter Secondary Name Server** boxes, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**Enter Primary Name Server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Enter Secondary Name Server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Enter Extra Name Server (Optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Enter Extra Name Server (Optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Enter the primary and secondary name servers on the Update Name Servers page](../media/e1f00cad-3c8a-4050-81c1-cb4c0184f1c9.png)
  
6. Choose **Update**.
    
    ![Click Update](../media/7fbb73fd-4a33-4ff4-ab14-760abc70ad31.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


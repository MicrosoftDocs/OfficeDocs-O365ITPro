---
title: "Change nameservers to set up Office 365 with eNomCentral"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_eNom1'
- 'O365M_DOM_eNom1'
- 'O365E_DOM_eNom1'
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
ms.assetid: e525d8b5-53eb-4581-ba5e-57d900aad4f0

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at eNomCentral."
---

# Change nameservers to set up Office 365 with eNomCentral

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at eNomCentral](create-dns-records-at-enomcentral.md).)
  
    
## Add a TXT record at eNomCentral to verify that you own the domain

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-eNomCentral-4a83685c-5ebf-462b-9d4d-bbdd9f3ffddc?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-Configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Under **my domains**, choose the name of the domain that you want to edit.
    
    ![eNom-BP-Configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. On the **Manage Domain** drop-down list, choose **Host Records**.
    
    ![eNom-BP-Verify-1-1](../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record Type** value from the drop-down list.) 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**Record Type** <br/> |**Address** <br/> |
|@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br/>    |
   
   ![eNom-BP-Verify-1-2](../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. Choose **save**.
    
    ![eNom-BP-Verify-1-3](../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
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
  
Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:13)](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-eNomCentral-4a83685c-5ebf-462b-9d4d-bbdd9f3ffddc?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![eNom-BP-Configure-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Under **my domains**, choose the name of the domain that you want to edit.
    
    ![eNom-BP-Configure-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. On the **Manage Domain** drop-down list, choose **DNS Server Settings**.
    
    ![eNom-BP-Redelegate-1-1](../media/67af5edb-0964-4505-8db7-eea37bfa2e48.png)
  
4. On the **Edit DNS Servers** page, in the **Use our Name Servers?** section, select **Custom**.
    
    ![eNom-BP-Redelegate-1-2](../media/82535e32-9385-4ffa-af9e-4a0b91acb71e.png)
  
5. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).
    
### If there are NO nameservers already listed

1. On the **Edit DNS Servers** page, type or copy and paste the nameserver values from the table below. 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
|||
   
   ![eNom-BP-Redelegate-1-3](../media/5381bfe3-e2d3-43f5-a034-07e3a68a336b.png)
  
2. Choose **save**.
    
    ![eNom-BP-Redelegate-1-4](../media/229e4de3-46bf-4225-b033-c9c686768088.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed


> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![eNom-BP-Redelegate-1-5](../media/ca32bd52-6144-4a69-a978-c0f91d10125b.png)
  
2. Still on the **Edit DNS Servers** page, type or copy and paste the nameserver values from the following table. 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
|||
   
   ![eNom-BP-Redelegate-1-3](../media/5381bfe3-e2d3-43f5-a034-07e3a68a336b.png)
  
3. Choose **save**.
    
    ![eNom-BP-Redelegate-1-4](../media/229e4de3-46bf-4225-b033-c9c686768088.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 

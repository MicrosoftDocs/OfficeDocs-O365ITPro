---
title: "Change nameservers to set up Office 365 with Hover"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Hover1'
- 'O365M_DOM_Hover1'
- 'O365E_DOM_Hover1'
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
ms.assetid: 41934fde-c4d3-4869-95ac-815bb5fdebf8
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Hover."
---

# Change nameservers to set up Office 365 with Hover

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Hover](create-dns-records-at-hover.md).)
  
## Add a TXT record at Hover to verify that you own the domain

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Follow the steps below or [watch the video](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Hover-cc465fa7-0d19-439b-bca2-52d90b5e56a2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Sign in](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Manage Your Domains**, choose the name of the domain that you want to edit.
    
    ![Choose a domain](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Choose the **DNS** tab. 
    
    ![Choose the DNS tab](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Choose **Add New**.
    
    ![Choose Add New](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
||||
|:-----|:-----|:-----|
|Hostname  <br/> |Record Type  <br/> |Value  <br/> |
|@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)    <br/>    |
   
   ![Type or copy and paste DNS values](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. Choose **Save**.
    
    ![Click Save](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying.
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
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
  
Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Hover-cc465fa7-0d19-439b-bca2-52d90b5e56a2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**. The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Sign in](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Manage Your Domains**, choose the name of the domain that you want to edit.
    
    ![Choose a domain](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Choose the **Domain Details** tab. 
    
    ![HoverBP-Redelegate-1-1](../media/8d85a794-2e43-4a54-91d9-5350aca242d5.png)
  
4. Find the **Nameservers** row and choose ** Edit **.
    
    ![HoverBP-Redelegate-1-2](../media/17cf2de1-384f-48d5-8a97-ccf1ce0732f6.png)
  
    In the following two steps, you will first remove all of the nameservers that are currently listed and then add the two nameservers that you need for Office 365.
    
5. In the **Nameservers Edit** section, delete each nameserver entry by selecting the entry and then pressing the **Delete** key on your keyboard. 
    
    > [!IMPORTANT]
    > Be sure to use the **Delete** key on your keyboard for this action, and not the **Delete** control on the screen, which has a different effect.
  
    ![HoverBP-Redelegate-1-3](../media/38ded07c-9201-42eb-840a-d1a1d2d1abcd.png)
  
6. Type or copy and paste the first three values from the following table in the **Nameserver** boxes. 
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Add Nameserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Add Nameserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![HoverBP-Redelegate-1-4-1](../media/a582cea7-d2b4-4866-beaf-393cd7a98da8.png)
  
7. Choose **Save**.
    
    ![HoverBP-Redelegate-1-4-2](../media/a429c1ef-bfd7-47e9-9acd-9eb5cb83fc26.png)
  
8. On the **Domain Details** page, find the **Nameservers** row and choose **Edit** again. 
    
    ![HoverBP-Redelegate-1-4-3](../media/2d970298-3c2e-4b86-9852-32d110c0e962.png)
  
9. Type or copy and paste the last value from the table in the box.
    
    ![HoverBP-Redelegate-1-4-4](../media/097f67c6-5457-483b-b9ef-f6ad6796b052.png)
  
10. Choose **Save**.
    
    ![HoverBP-Redelegate-1-5](../media/11df7048-1ded-41e7-a8ec-d5290f443eba.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.
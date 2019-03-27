---
title: "Change nameservers to set up Office 365 with Melbourne IT"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_MIT1'
- 'O365M_DOM_MIT1'
- 'O365E_DOM_MIT1'
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
ms.assetid: 38ab37cb-2915-4ed5-bd33-4360f8c23f58
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Melbourne IT."
---

# Change nameservers to set up Office 365 with Melbourne IT

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Melbourne IT](create-dns-records-at-melbourne-it.md).)
  
## Add a TXT record at Melbourne IT to verify that you own the domain

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Follow the steps below or [watch the video (start at :50)](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Melbourne-IT-bb98833b-1e7f-4d35-9533-20e37da2187b?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. Under **Domain Name**, choose the name of the domain that you want to edit.
    
    ![MelbourneIT-BP-Configure-1-3](../media/ca52e15f-beda-439f-a9ed-76c103b429cb.png)
  
4. In the **DNS** section, on the **DNS Status** row, choose **Manage Power DNS**.
    
    ![MelbourneIT-BP-Configure-1-4](../media/76dfbf8f-cc9d-4f14-a3aa-37972269e682.png)
  
5. Scroll down to the **TXT Records** section and, in the boxes for the new record, type or copy and paste the following values. 
    
|**HOSTNAME**|**TXT VALUE**|
|:-----|:-----|
|Use your domain name.  <br/> Example: contoso.com.  <br/> **This value MUST end with a period (.)** <br/> |MS=ms *XXXXXXXX*  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![MelbourneIT-BP-Verify-1-1](../media/9ac3a867-51ff-4e86-872e-d7813dea24cd.png)
  
6. Choose the **Add** button indicated in the following illustration. 
    
    ![MelbourneIT-BP-Verify-1-2](../media/d5a8e480-b2e2-44d4-89be-d65544122e97.png)
  
7. Choose **Edit** for the record that you have just created. 
    
    ![MelbourneIT-BP-Verify-1-3](../media/5260b33e-d169-49d0-b5dc-fe3ab9a387f3.png)
  
8. Select **3600** for the **TTL (SEC)** value. 
    
    ![MelbourneIT-BP-Verify-1-4](../media/a8a01807-4388-481f-a967-cb688953b7b4.png)
  
9. Choose **Update**.
    
    ![MelbourneIT-BP-Verify-1-5](../media/9d925e8f-ba87-41fd-927e-47010e064987.png)
  
10. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:25)](https://support.office.com/en-us/article/Video-Change-nameservers-to-set-up-Office-365-with-Melbourne-IT-bb98833b-1e7f-4d35-9533-20e37da2187b?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**. The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.
  
1. To get started, go to your domains page at Melbourne IT by using [this link](https://www.melbourneit.com.au/cc/myaccount/domains/index). You'll be prompted to log in.
    
    ![MelbourneIT-BP-Configure-1-1](../media/f9107021-9c9b-47bd-9e2d-95f752384c2c.png)
  
2. In the **My Purchases** section, choose **Manage Domain Names**.
    
    (You may need to scroll down.)
    
    ![MelbourneIT-BP-Configure-1-2](../media/c01ebdb1-301e-47a5-ba82-69d1bf46a77e.png)
  
3. On the **Manage Domain Names** page, choose the name of the domain that you want to edit. 
    
    ![MelbourneIT-BP-Redelegate-1-1](../media/c9aab719-2100-47ec-90cb-c5be61365503.png)
  
    To change nameservers, you must first cancel the Melbourne IT DNS Management service. The next two steps show you how.
    
4. On the **Manage  *domain_name* ** page, in the **Change Name Servers** row of the **DNS** section, choose **Cancel DNS Management 2.0**.
    
    (You may have to scroll down.)
    
    ![MelbourneIT-BP-Redelegate-1-2](../media/118b0526-4a45-435e-8636-a95f9b676827.png)
  
5. On the **Cancel DNS** page, choose **Yes, I am sure** to confirm your action. 
    
    ![MelbourneIT-BP-Redelegate-1-3](../media/7784e0cf-6511-45c2-8885-1e182cacd985.png)
  
6. On the updated **Manage  *domain_name* ** page, in the **Change Name Servers** row of the **DNS** section, choose **Redelegate Domain Name**.
    
    ![MelbourneIT-BP-Redelegate-1-4](../media/a2d79d74-9e48-4f05-860d-5dcad254688f.png)
  
    In the following two steps, you will first remove all of the nameservers that are currently listed, and then add the two nameservers that you need for Office 365.
    
7. In the **Change Nameserver Delegation** section, delete each nameserver entry by selecting the entry and then pressing the **Delete** key on your keyboard. 
    
    ![MelbourneIT-BP-Redelegate-1-5](../media/3367de5b-b8b7-445b-90e6-046de79af586.png)
  
8. When you have deleted all of the existing nameservers, type or copy and paste the values from the following table in the first four boxes under **Hostname**.
    
|||
|:-----|:-----|
|**Primary Nameserver** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Secondary Nameserver** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MelbourneIT-BP-Redelegate-1-6](../media/6b2916ed-891a-4f25-b716-beea38a253d1.png)
  
9. Choose **Continue**.
    
    ![MelbourneIT-BP-Redelegate-1-7](../media/14739276-8956-47f3-8ff4-be66294372e3.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.

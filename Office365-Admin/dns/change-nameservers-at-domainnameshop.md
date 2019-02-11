---
title: "Change nameservers to set up Office 365 with Domainnameshop"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ad007dd2-707f-433c-9150-00f56118bd19

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Domainnameshop."
---

# Change nameservers to set up Office 365 with Domainnameshop

Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Domainnameshop by using [this link](https://www.domainnameshop.com/login). You'll be prompted to log in. 
    
    ![Login screen in Domainnameshop](../media/94d9df22-d43e-4f12-910c-33df1dd772af.png)
  
2. Choose **My Domains**. 
    
    ![My domains tab selected in Domainnameshop](../media/642a86bc-6c4a-4e39-9639-99513dab9444.png)
  
3. Choose the domain that you want to edit. 
    
    ![Active domain selected in Domainnameshop](../media/a16c33b3-21e4-4112-a4b0-a703a3958601.png)
  
4. Choose the **DNS records** tab. 
    
    ![DNS records tab highlighted in Domainnameshop](../media/9387965e-b467-451a-9311-8a17a09f3546.png)
  
5. Choose **Show advanced settings**. 
    
    ![Show advanced settings in Domainnameshop](../media/b3ed8d12-ba67-4610-bd4b-3c1d0a1db3c8.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
|**Host name**|**TTL**|**RR Type**|**Data**|
|:-----|:-----|:-----|:-----|
|(leave blank)  <br/> |1 hour  <br/> |TXT  <br/> |MS=msXXXXXXXX  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)<br/>      |
   
   ![TXT record in Domainnameshop](../media/f2ec5943-5b8d-4028-90f8-4a1344264e68.png)
  
7. Choose the **+** (Add) button. 
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
## Change your nameservers

1. Log in to the control panel at [https://www.domainnameshop.com/login](https://www.domainnameshop.com/login).
    
2. Click on " **My Domains**."
    
3. Click on the domain in question.
    
4. Click on " **Edit nameservers**" on the right side of the page.
    
5. Edit your nameservers to the addresses below and click on " **Change**" at the bottom of the page.
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   


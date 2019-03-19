---
title: "Change nameservers to set up Office 365 with Onamae"
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
ms.assetid: 51a93b15-b8e5-42ca-af76-b6595c271e1a
description: "Learn to set up your Office 365 custom domain with Onamae if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with Onamae

[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If Onamae is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you change your NS records at Onamae, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.
  
1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log in.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3. Select the radio button next to the domain, and then choose **Next**.
    
    ![Callout next to the domain name in Onamae](../media/2bd27471-8dea-49ea-b4e1-b54fa0f620a2.png)
  
4. Next to **Use DNS record settings**, choose **Set up**.
    
    ![Set up button in Onamae](../media/73def81e-d25a-426b-bde6-cf12c5861885.png)
  
5. In the entry fields for new DNS records, select TXT, and then type or copy and paste the values from the following table.
    
|**Host name**|**Type**|**TTL**|**Value (Points to address or value)**|
|:-----|:-----|:-----|:-----|
|(leave blank)  <br/> |TXT  <br/> |3600          (seconds)  <br/> |MS=msXXXXXXXX  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)
   
![TXT Value for a new DNS record in Onamae](../media/f4f0c932-3659-47dd-90fc-919ed5657c86.png)
  
6. Choose **Add**.
    
    ![Add button for TXT value in Onamae](../media/6aa5b0c2-a20e-453e-9b84-dbdbbcfb3419.png)
  
7. At the bottom of the page, choose **Go to confirmation screen**
    
    ![Go to confirmation screen in Onamae](../media/230f27d6-82b0-42dc-a61a-d26dc1b9cee6.png)
  
8. At the bottom of the Confirmation screen, choose **Set up**.
    
    ![Confirm set up in Onamae](../media/63a91c3a-26b3-42c3-9d40-0922a8398ad6.png)
  
9. At the bottom of the page, select **Continue the procedure**.
    
    ![Continue the procedure button in Onamae](../media/7a38f2db-b9ea-4907-865e-263b0cdc57cd.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    
  
3. On the **Setup** page, choose **Start setup**.
    
    
  
4. On the **Verify domain** page, choose **Verify**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
  
## Change your nameservers

1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log in.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3.  Select your domain with the check box and then select the radio button next to **Use another name server** below.
    
4. Enter the nameservers into the provided fields and then click "**Go to confirmation screen**."
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
5. Confirm that the nameservers are correct and click "**To set up**."

6. Click **Continue the procedure** on the next screen to finish.
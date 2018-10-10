---
title: "Change nameservers to set up Office 365 with name.com"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_name1'
- 'O365M_DOM_name1'
- 'O365E_DOM_name1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab664f29-4e43-4417-9db9-b26bfee12d67

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at name.com."
---

# Change nameservers to set up Office 365 with name.com

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at name.com](create-dns-records-at-name-com.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-name-com.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-name-com.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-name-com.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.
    
    ![Name-BP-Configure-1-1](../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **My Domains**, choose the name of the domain that you want to modify.
    
    ![Name-BP-Configure-1-2](../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. In the **Details** column, choose ** DNS Records **. 
    
    ![Name-BP-Configure-1-3](../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Type** <br/> |**Host** <br/> |**Answer** <br/> |**TTL** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |
   
    ![Name-BP-Verify-1-1](../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. Choose **Add Record**.
    
    ![Name-BP-Verify-1-2](../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify button](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.
    
    ![Name-BP-Configure-1-1](../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **My Domains**, choose the name of the domain that you want to modify.
    
    ![Name-BP-Configure-1-2](../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. In the **Details** column, choose **Nameservers**.
    
    ![Name-BP-Redelegate-1-1](../media/6143be12-c807-4e1f-9032-1cc5ad462886.png)
  
4. In the **Edit Nameserver** section, find the first nameserver in the list, and then choose **Edit** in the **Actions** column. 
    
    ![Name-BP-Redelegate-1-2](../media/2054170e-8205-4529-9aa3-5a34a965a470.png)
  
5. Delete the current entry by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![Name-BP-Redelegate-1-3](../media/91ad5e80-9034-4edb-909d-b3ee3fa7375f.png)
  
6. Add the first nameserver.
    
    In the same box, type or copy and paste the first nameserver value from the following table ( **ns1.bdm.microsoftonline.com** ). 
    
|||
|:-----|:-----|
|First **Nameserver** row  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Second **Nameserver** row  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Third **Nameserver** row  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fourth **Nameserver** row  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Name-BP-Redelegate-1-4-1](../media/6d9575a7-3e46-4acc-a1be-67136fe54459.png)
  
7. Choose **Update**.
    
    ![Name-BP-Redelegate-1-4-2](../media/7ef6b394-c4eb-4bfa-a581-6eab97b1a91c.png)
  
8. Choose **Apply Changes** to save your update. 
    
    ![Name-BP-Redelegate-1-5](../media/b8c356f1-53e3-4f04-952b-b43bda8b96f9.png)
  
9. Add the other nameservers.
    
    Use the same process, but this time replace the nameservers in the list with the  *next*  nameserver from the table above ( **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**).
    
    (Make sure that you finish the addition by choosing first **Update** and then **Apply Changes**.)
    
10. If there are now any nameservers in the list other than **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**, delete each of those other nameservers by choosing **Delete** in the **Actions** column for that record. 
    
    ![Name-BP-Redelegate-1-6](../media/f14519a9-ec70-4fdf-9b5a-1b0f4d3978e4.png)
  
11. Choose **Apply Changes** to save your updates. 
    
    ![Name-BP-Redelegate-1-7](../media/724a866d-44d1-43f0-9a4f-09ba0075b5ea.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 

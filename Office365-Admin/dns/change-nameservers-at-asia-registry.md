---
title: "Change nameservers to set up Office 365 with Asia Registry"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Asia1'
- 'O365M_DOM_Asia1'
- 'O365E_DOM_Asia1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a507f23b-f070-40a2-856a-0d834ac1168d
description: "Learn how you can set up Office 365 to manage your DNS records at Asia Registry. "
---

# Change nameservers to set up Office 365 with Asia Registry

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Asia Registry](create-dns-records-at-asia-registry.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-asia-registry.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-asia-registry.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-asia-registry.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **My Domains** page, in the row for the domain you're changing, choose the domain name. 
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-3](../media/820b6d1a-7fed-48f4-8015-c177693a1f0e.png)
  
4. On the **Domain Info** page, choose **DNS SETTINGS**.
    
    ![AsiaRegistry-BP-Configure-1-4](../media/39b750e4-4ed7-47ca-9a8a-b1b8a9fe77eb.png)
  
5. Select **Use Asia Registry Name Servers**.
    
    ![AsiaRegistry-BP-Configure-1-5](../media/8a05d58d-f5ea-4fb3-aaa4-f4b332c4c6e7.png)
  
6. Choose **EDIT ZONE RECORDS (Advanced)**.
    
    ![AsiaRegistry-BP-Configure-1-6](../media/2074b068-196e-447e-aa0a-99478451545c.png)
  
7. In the **ZONE RECORDS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host**|**Type**|**Content**|
|:-----|:-----|:-----|
|@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![AsiaRegistry-BP-Verify-1-1](../media/a9e44f32-8a50-4b58-ad97-b87bb618bd77.png)
  
8. Choose **ADD** to save the record, which also automatically adds a new empty row. 
    
    ![AsiaRegistry-BP-Verify-1-2](../media/886175ad-1b81-4822-93a7-88379945ca2e.png)
  
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
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Asia Registry by using [this link](https://asiaregistry.secure-admin.com/domain/default/admin). You'll be prompted to login first.
    
    ![AsiaRegistry-BP-Configure-1-1](../media/dd8532ed-9d0c-4b05-b001-288b195f0fe2.png)
  
2. On the **Dashboard** page, choose **MY DOMAINS**.
    
    (You may have to scroll down.)
    
    ![AsiaRegistry-BP-Configure-1-2](../media/caa6a135-47be-47a9-ac36-aefc83b0e30e.png)
  
3. On the **Domain Info** page, in the **Name Server** section, choose **EDIT**.
    
    ![AsiaRegistry-BP-Redelegate-1-1](../media/1aeef8ce-00f1-4451-9b4c-3917de713ab8.png)
  
4. Select **Delegate to Your Name Servers**.
    
    ![AsiaRegistry-BP-Redelegate-1-2](../media/a03466a3-b0e1-4652-859e-6e5081728869.png)
  
5. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](change-nameservers-at-asia-registry.md#BKMK_ProcedureWithOUT).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](change-nameservers-at-asia-registry.md#BKMK_ProcedureWITH).
    
### If there are NO nameservers already listed
<a name="BKMK_ProcedureWithOUT"> </a>

1. In the **Host Name** area, type or copy and paste the **Host Name** values from the following table. 
    
|**Host Name**|**IP Address**|
|:-----|:-----|
|ns1.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns2.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns3.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns4.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
   
    ![AsiaRegistry-BP-Redelegate-1-3-1](../media/1402ab51-7974-4bd8-891d-0d3cd61e6a18.png)
  
2. Add the other two Name Server values.
    
    Choose **ADD** and then type or copy and paste the value from the next row of the table into the box for the record. 
    
    Repeat this process until you have created all four Nameserver records.
    
    ![AsiaRegistry-BP-Redelegate-1-3-2](../media/35dab601-b8e6-4cca-adb9-d9682b9becb2.png)
  
3. Choose **DELEGATE TO YOUR NAME SERVERS**.
    
    ![AsiaRegistry-BP-Redelegate-1-4](../media/cd342f18-8790-4921-9630-f42d2ebdb7d2.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed
<a name="BKMK_ProcedureWITH"> </a>

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. If there are any other nameservers listed, choose the **Edit** icon for each one to update that nameserver. 
    
    ![AsiaRegistry-BP-Redelegate-1-5](../media/5b227e77-9be1-42dc-a0ce-b7e470322fcd.png)
  
2. In the **Host Name** area, delete each nameserver entry by selecting that entry and then pressing the **Delete** key on your keyboard. 
    
    ![AsiaRegistry-BP-Redelegate-1-6](../media/66ff199c-6f1f-4d89-b905-c70494e5cef1.png)
  
3. Add the first nameserver.
    
    Still in the **Host Name** area, type or copy and paste the first **Host Name** value from the following table. 
    
|**Host Name**|**IP Address**|
|:-----|:-----|
|ns1.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns2.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns3.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns4.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
   
    ![AsiaRegistry-BP-Redelegate-1-7](../media/da1ca3f9-3b75-4585-90d5-02a463958088.png)
  
4. Choose **SAVE**.
    
    ![AsiaRegistry-BP-Redelegate-1-8](../media/fd16a832-b3a9-43c8-b096-4f2ecbe3c751.png)
  
5. Add the second nameserver record.
    
    Still in the **Host Name** area, choose the **Edit** icon to update the other record using the values from the second row in the table, and then again choose **SAVE** to complete that record. 
    
6. Add the other Name Server values.
    
    Choose **ADD** and then type or copy and paste the value from the third row of the table above into the box for the next record. Repeat this process until you have created all four Nameserver records. 
    
7. Delete any other incorrect nameservers by choosing the **Edit** icon, deleting each nameserver entry by selecting that entry and pressing the **Delete** key on your keyboard, and then choosing **SAVE**. When you are finished, you should have only four nameservers listed:
    
    ns1.bdm.microsoftonline.com
    
    ns2.bdm.microsoftonline.com
    
    ns3.bdm.microsoftonline.com
    
    ns4.bdm.microsoftonline.com
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


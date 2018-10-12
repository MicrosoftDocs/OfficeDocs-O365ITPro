---
title: "Change nameservers to set up Office 365 with DomainExplorer.com"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DE1'
- 'O365M_DOM_DE1'
- 'O365E_DOM_DE1'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3ddca527-1891-40e5-922f-513af41598e4

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at DomainExplorer.com."
---

# Change nameservers to set up Office 365 with DomainExplorer.com

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at DomainExplorer.com](create-dns-records-at-domainexplorer-com.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-domainexplorer-com.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-domainexplorer-com.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-domainexplorer-com.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **Host Records** section, choose **Edit**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Configure-1-3](../media/5a13170c-9b86-412e-9f74-63dbb5251ea7.png)
  
4. In the **Standard Host Names** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Host Name**|**Type**|**Address**|
|:-----|:-----|:-----|
|@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DomainExplorer-BP-Verify-1-2](../media/df68adf3-72ef-4823-bb35-5dc325365459.png)
  
5. Choose **Save Changes**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Verify-1-3](../media/2ec16974-c660-4a46-89a4-b4ba590cd9ee.png)
  
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
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at DomainExplorer.com by using [this link](http://domainexplorer.com/domain-manager/default.aspx). You'll be prompted to login.
    
    ![DomainExplorer-BP-Configure-1-1](../media/2730d63a-e547-4eb7-9c7f-cb7a32d79909.png)
  
2. Under **Domain Manager**, choose the name of the domain that you want to edit.
    
    ![DomainExplorer-BP-Configure-1-2](../media/8298b2d8-7713-4c38-bf6f-ff4a13d4898d.png)
  
3. In the **DNS Servers** section, choose **Edit**.
    
    (You may have to scroll down.)
    
    ![DomainExplorer-BP-Redelegate-1-1](../media/4a45e1dd-ee30-467c-b835-5fbe57a7d11c.png)
  
4. In the **Select DNS Source** section, select **Custom DNS**.
    
    ![DomainExplorer-BP-Redelegate-1-2](../media/260b0e9d-233c-4813-b3de-b6bc043d2a24.png)
  
5. Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If there are **NO** nameservers already listed, [If there are NO nameservers already listed](change-nameservers-at-domainexplorer-com.md#BKMK_ProcedureWithOUT).
    
  - If there **ARE** nameservers already listed, [If there ARE nameservers already listed](change-nameservers-at-domainexplorer-com.md#BKMK_ProcedureWITH).
    
### If there are NO nameservers already listed
<a name="BKMK_ProcedureWithOUT"> </a>

1. On the **Domain Manager** page, under **Server Address**, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![DomainExplorer-BP-Redelegate-1-3](../media/075c9975-d493-44c1-ba83-1dacb46809e2.png)
  
2. Choose **Save Changes**
    
    ![DomainExplorer-BP-Redelegate-1-5](../media/13af0bce-74b9-4876-8b6f-6dc2d93a0b6c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
### If there ARE nameservers already listed
<a name="BKMK_ProcedureWITH"> </a>

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
1. If there are any other nameservers listed, delete each one by choosing **delete** in the **Options** column for that nameserver. 
    
    ![DomainExplorer-BP-Redelegate-1-4](../media/ee959225-f484-4498-9c73-07039da1b350.png)
  
2. Still on the **Domain Manager** page, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![DomainExplorer-BP-Redelegate-1-3](../media/075c9975-d493-44c1-ba83-1dacb46809e2.png)
  
3. Choose **Save Changes**
    
    ![DomainExplorer-BP-Redelegate-1-5](../media/13af0bce-74b9-4876-8b6f-6dc2d93a0b6c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


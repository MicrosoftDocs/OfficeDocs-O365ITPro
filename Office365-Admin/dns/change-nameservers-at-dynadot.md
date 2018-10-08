---
title: "Change nameservers to set up Office 365 with Dynadot"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 3/28/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Dyna1'
- 'O365M_DOM_Dyna1'
- 'O365E_DOM_Dyna1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6b71d0f1-778d-4691-9876-35191329ffc5

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Dynadot."
---

# Change nameservers to set up Office 365 with Dynadot

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Dynadot](create-dns-records-at-dynadot.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-dynadot.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-dynadot.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-dynadot.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose the **DNS** tab. 
    
    ![Dynadot-BP-Configure-1-4](../media/9f251ffa-569e-402c-ab97-1d5b24d88514.png)
  
4. In the **Domain Record (required)** section, find the boxes for the new record, and then type or copy and paste the values from the following table. 
    
    (Choose the **Record Type** value from the drop-down list.) 
    
|**Record Type**|**IP Address or Target Host**|
|:-----|:-----|
|TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dynadot-BP-Verify-1-1](../media/7be98776-f41d-4317-b93a-afccf72d6590.png)
  
5. Choose **Save DNS**.
    
    (You may have to scroll down.)
    
    ![Dynadot-BP-Verify-1-2](../media/13510279-3652-491d-be26-a3d527eeff2e.png)
  
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
  
1. To get started, go to your domains page at Dynadot by using [this link](https://www.dynadot.com/account/domain/name/server.mdl). You'll be prompted to sign in first.
    
    ![Dynadot-BP-Configure-1-1](../media/e5602931-f9f7-4466-b134-0d35e4b45150.png)
  
2. On the **Manage** page, find the name of the domain that you want to edit, and then, in the **Name Server** column, choose the ** *NS: name servers* ** link. 
    
    ![Dynadot-BP-Configure-1-2](../media/8de8f5c5-a71a-48ef-84c2-e16bf7422b13.png)
  
3. On the **Edit Name Server Settings** page, choose **Name Servers**.
    
    ![Dynadot-BP-Redelegate-1-0](../media/153ea370-99bf-4989-acb8-fbf14e3ec0a7.png)
  
4. On the **Edit Name Server Settings** page, in the **Option 1** section, type or copy and paste the nameserver values from the following table. 
    
|||
|:-----|:-----|
|**1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Dynadot-BP-Redelegate-1-1-1](../media/a33cbdbb-6ee0-4ed1-aed7-ddd20e2d2413.png)
  
5. When you have added both values, choose **Enter Name Servers**.
    
    ![Dynadot-BP-Redelegate-1-1-2](../media/4bf777d2-1008-4a31-8ecb-6c2b132c5ba2.png)
  
6. If the Office 365 nameservers that you added in the previous step are now listed as nameservers **1**, **2**, **3**, and **4** in the **Option 2** section, as shown in the following illustration, then you're done with this procedure. 
    
    ![Dynadot-BP-Redelegate-1-2](../media/1bfcbade-3d3d-445b-9b6e-d8e7ec0a9443.png)
  
    If  *different*  nameservers are shown in the **Option 2** section, however (as shown in the following illustration), then go on to the next step to replace them with the nameservers that you have just added. 
    
    ![Dynadot-BP-Redelegate-1-3](../media/c0aeee17-884f-4bf7-a470-cafcfeac3eec.png)
  
7. **Only** if different nameservers are shown in the **Option 2** section, as described in the preceding step, select **ns1.bdm.microsoftonline.com** in the first drop-down list, and then chose the other nameservers from the remaining drop-down lists. 
    
    ![Dynadot-BP-Redelegate-1-4](../media/4f65985a-5f2d-42b1-b020-b23cf24598e3.png)
  
8. Choose **Select Name Servers**.
    
    ![Dynadot-BP-Redelegate-1-5](../media/9729b5e4-671c-4e91-bf9e-5d769c2331dd.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  
## Still need help?
<a name="BKMK_NeedHelp"> </a>

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


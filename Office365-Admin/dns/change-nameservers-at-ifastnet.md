---
title: "Change nameservers to set up Office 365 with iFastNet"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: cc8a26cb-b01f-4956-8ffd-4fe415989620

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at iFastNet."
---

# Change nameservers to set up Office 365 with iFastNet

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at iFastNet](create-dns-records-at-ifastnet.md).)
  
(Need more help? [Still need help?](change-nameservers-at-ifastnet.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-ifastnet.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-ifastnet.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your cPanel page at iFastNet. You'll be prompted to log in first.
    
    (Each hosted account at iFastNet is assigned a unique cPanel address. Your cPanel address should look like this: https://YourHostAddress:secure-port-number. The sign-up email you received from iFastNet will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with iFastNet. To get started with Office 365, you can either purchase a hosting account from iFastNet or [redelegate your nameservers to point to Office 365](change-nameservers-at-ifastnet.md). 
  
    ![iFast-BP-Configure-1-1](../media/a88310c4-fe7a-48c2-adbb-bd467ad30516.png)
  
2. On the **iFastNet cPanel** page, in the **DOMAINS** area, choose **Advanced Zone Editor**.
    
    (You may have to scroll down.)
    
    ![iFast-BP-Configure-1-2](../media/c41ac6cc-14c3-42b4-8503-c6bf20a0b402.png)
  
3. In the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Type**|**Name**|**TTL**|**TXT Data**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |Use your  *domain_name*  (For example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![iFast-BP-Verify-1-1](../media/badeea37-286e-471e-a333-8ab87b634ae1.png)
  
4. Choose **Add Record**.
    
    ![iFast-BP-Verify-1-2](../media/78d2e8eb-4ebe-476f-8e17-fd009860fcb0.png)
  
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
1. To get started, go to your domain management page at iFastNet by using [this link](https://ifastnet.com/portal/clientarea.php). You'll be prompted to log in.
    
    ![iFast-BP-Redelegate-1-1](../media/ffa13ac6-2a80-4e24-b0fc-83421a407733.png)
  
2. Choose **Domains**.
    
    ![iFast-BP-Redelegate-1-2](../media/07f7c003-36e5-4113-9769-f32ae39fae3d.png)
  
3. On the **My Domains** page, find the domain you want to update. 
    
    ![iFast-BP-Redelegate-1-3-1](../media/097ab6a5-853b-4d81-9667-1b6166913b0b.png)
  
4. Choose **Manage Nameservers** from the drop-down list. 
    
    ![iFast-BP-Redelegate-1-3-2](../media/743d3853-8313-43df-863b-c5893edd1ab1.png)
  
5. Choose **Use custom nameservers (enter below)**.
    
    ![iFast-BP-Redelegate-1-4](../media/05e19327-5d25-4a77-b81f-8d53152cb390.png)
  
6. Still on the **Nameservers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard. 
    
    > [!CAUTION]
    > Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
    ![iFast-BP-Redelegate-1-5](../media/05482ec5-f524-4467-94ab-5c5495fab506.png)
  
7. Still in the list of nameservers, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![iFast-BP-Redelegate-1-6](../media/a9cf9602-3ad2-40cd-84ef-bdb619d61841.png)
  
8. Choose **Change Nameservers**.
    
    ![iFast-BP-Redelegate-1-7](../media/77cb25a8-c2f8-4055-a288-c845de63bfc4.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

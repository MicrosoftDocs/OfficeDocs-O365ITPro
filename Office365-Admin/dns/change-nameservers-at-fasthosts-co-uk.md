---
title: "Change nameservers to set up Office 365 with Fasthosts.co.uk"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Fast1'
- 'O365M_DOM_Fast1'
- 'O365E_DOM_Fast1'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fdf005a0-eb03-4eb1-aa77-5e9b5dfbe749

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Fasthosts.co.uk."
---

# Change nameservers to set up Office 365 with Fasthosts.co.uk

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Fasthosts.co.uk](create-dns-records-at-fasthosts-co-uk.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-fasthosts-co-uk.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-fasthosts-co-uk.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-fasthosts-co-uk.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/Auth/Login). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then choose the **DNS** icon for that domain name. 
    
4. On the **Advanced DNS** page for your domain, in the **TXT Records** section, choose ** Add TXT Record **.
    
    (You may have to scroll down.) 
    
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**Host Name** <br/> |**Value** <br/> |
|@  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Choose **Save**.
    
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain.*  com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: 
  
1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/Auth/Login). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then select the check box for that domain name. 
    
    ![FasthostsUK-BP-Redelegate-1-1](../media/0ff34451-3430-416b-bc4d-66d08a6228f5.png)
  
    With the check box selected, in the **Perform action on selected items** row, select **Update name servers** in the drop-down menu, and then choose **Continue**.
    
    ![FasthostsUK-BP-Redelegate-1-1-2](../media/acebddec-6c8a-4d93-ac0f-4570ecf9bf6f.png)
  
4. Select **Specify name servers**.
    
    ![FasthostsUK-BP-Redelegate-1-2](../media/314837cb-b174-443d-8e74-efe4bcf7a959.png)
  
5. Delete each of the nameservers currently listed by selecting it and then pressing the **Delete** key on your keyboard. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or ** ns4.bdm.microsoftonline.com **.) 
  
    ![FasthostsUK-BP-Redelegate-1-3](../media/b6e4ad6d-2782-457c-9588-903808e5df45.png)
  
6. In the **Name server details** section, in the boxes for the new records, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![FasthostsUK-BP-Redelegate-1-4](../media/8e3bfed3-85a9-444a-8208-e434d04a6520.png)
  
7. Choose **Update Name Server Details.**
    
    ![FasthostsUK-BP-Redelegate-1-5](../media/e1a9afaf-6965-45ad-98e9-d91e84cc33f5.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 

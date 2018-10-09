---
title: "Change nameservers to set up Office 365 with Heart Internet"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_HI1'
- 'O365M_DOM_HI1'
- 'O365E_DOM_HI1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 726b5033-0b64-4750-bf2e-0a57c398c8a7

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Heart Internet."
---

# Change nameservers to set up Office 365 with Heart Internet

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Heart Internet](create-dns-records-at-heart-internet.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-heart-internet.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-heart-internet.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-heart-internet.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.uk/manage/login.cgi?destination=%2Fmanage%2Fmanage.cgi). You'll be prompted to log in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the **Manage Domain Parking** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
4. In the **Manage Domain** section, choose **DNS Management**.
    
5. In the **TXT Records** section, in the **Text** box for the new record, type or copy and paste the value from the following table. 
    
    (You may have to scroll down.) 
    
|||
|:-----|:-----|
|**Subdomain** <br/> |**Text** <br/> |
|(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Choose **Update DNS**.
    
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](https://support.office.com/article/40398b0b-bdd0-4afd-ab5e-b5ae6b7990b.aspx). 
  
## Change your domain's nameserver (NS) records
<a name="BKMK_nameservers"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four: 
  
1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.uk/manage/login.cgi?destination=%2Fmanage%2Fmanage.cgi). You'll be prompted to log in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the ** Manage Domain Parking ** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
    ![HeartInternet-BP-Configure-1-3](../media/51e545f1-176b-4569-b98f-bf5e673facb3.png)
  
4. Choose **Change Nameservers**.
    
    ![HeartInternet-BP-Redelegate-1-1](../media/169738f9-7c89-475f-be6a-aa0e71539f62.png)
  
5. Select **Custom nameservers**.
    
    ![HeartInternet-BP-Redelegate-1-2-1](../media/7973cf04-f17c-48cd-8826-e7c729dd31a2.png)
  
6. Depending on whether or not the correct nameservers are already listed on the page that is displayed now, continue to one of the two following procedures:
    
  - If the correct nameservers **ARE** already listed, [If the correct nameservers ARE already listed](change-nameservers-at-heart-internet.md#BKMK_ProcedureWithOUT).
    
  - If the correct nameservers are **NOT** already listed, [If the correct nameservers are NOT already listed](change-nameservers-at-heart-internet.md#BKMK_ProcedureWITH).
    
### If the correct nameservers ARE already listed
<a name="BKMK_ProcedureWithOUT"> </a>

- If the correct nameservers are already listed, you can skip this step.
    
    ![HeartInternet-BP-Redelegate-1-2-2](../media/1895aa4e-b1d9-4662-98d0-f64c070ea3ac.png)
  
### If the correct nameservers are NOT already listed
<a name="BKMK_ProcedureWITH"> </a>

> [!CAUTION]
> Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. 
  
1. On the Change Nameservers page, in the **Set nameservers to:** area, type or copy and paste the values from the following table into the boxes. 
    
|||
|:-----|:-----|
|**1.** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**2.** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**3.** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**4.** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![HeartInternet-BP-Redelegate-1-3](../media/51e45082-6461-4a70-aa57-d280aedeba1c.png)
  
2. Choose **Change Nameservers**.
    
    ![HeartInternet-BP-Redelegate-1-4](../media/1a4973f8-519b-49fb-81b5-5b9c593bdbb5.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

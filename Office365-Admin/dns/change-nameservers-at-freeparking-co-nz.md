---
title: "Change nameservers to set up Office 365 with Freeparking.co.nz"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_FreeP1'
- 'O365M_DOM_FreeP1'
- 'O365E_DOM_FreeP1'
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
ms.assetid: 91065a6c-3e6b-4614-9bfc-8a45cc05a48b
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Freeparking.co.nz."
---

# Change nameservers to set up Office 365 with Freeparking.co.nz

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at FreeParking.co.nz](create-dns-records-at-freeparking-co-nz.md).)
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, choose the **Service Management** tab. 
    
    ![FreeparkingNZ-BP-Configure-1-3-1](../media/23a0863e-d792-4026-a05e-6598af21e1fd.png)
  
4. In the **Name Server Records** section, choose **Modify**.
    
    ![FreeparkingNZ-BP-Configure-1-3-2](../media/9767944c-a27a-4b66-949e-d2d3d2c7cf2d.png)
  
5. Choose **Advanced View**.
    
    ![FreeparkingNZ-BP-Configure-1-4-1](../media/f1d95e8d-7a63-4511-b53e-4c8d15c266c3.png)
  
6. Set the **Time to Live (TTL)** value for all records by selecting the **Data** value specified in the following table. 
    
    (Select the **Data** value from the drop-down list.) 
    
|**Host Name**|**Record Type**|**Data**|
|:-----|:-----|:-----|
| *All records*  <br/> |Caching Time (TTL)  <br/> |1 Hour  <br/> |
   
   ![FreeparkingNZ-BP-Configure-1-4-2](../media/7caef32d-ba28-4d57-8ea3-7d694af5a47e.png)
  
7. Choose **Add another record**.
    
    ![FreeparkingNZ-BP-Configure-1-4-3](../media/9f204f1f-6078-4504-8ba7-e73bbcd96da6.png)
  
8. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record Type** value from the drop-down list.) 
    
|**Host Name**|**Record Type**|**Data**|
|:-----|:-----|:-----|
|Use your domain name (for example, fourthcoffee.com)  <br/> |Descriptive (TXT)  <br/> |MS=ms *XXXXXXXX* <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |
   
   ![FreeparkingNZ-BP-Verify-1-1](../media/927e8240-9cba-4431-bbc0-a016f5a44d0b.png)
  
9. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Verify-1-2](../media/2b721ea6-bb7e-4fea-8d51-13c9bdd11973.png)
  
10. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Verify-1-3](../media/9d7a3161-cd95-4f50-9809-d3d745be6f7c.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    
  
3. On the **Setup** page, choose **Start setup**.
    
    
  
4. On the **Verify domain** page, choose **Verify**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change your domain's nameserver (NS) records

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, in the **Domain Name Servers** section, choose **Modify**.
    
    (You may have to scroll down.)
    
    ![FreeparkingNZ-BP-Redelegate-1-1](../media/f31b0bf3-64c2-4264-b067-023c1b3e6b73.png)
  
4. In the **Nameserver provider** drop-down list, choose **Other/Custom**.
    
    ![FreeparkingNZ-BP-Redelegate-1-2](../media/ac0e1997-30f2-4ffa-ac53-a5676e253189.png)
  
5. Delete each nameserver by selecting it and then pressing the **Delete** key on your keyboard. 
    
    > [!CAUTION]
    > Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
    ![FreeparkingNZ-BP-Redelegate-1-3](../media/3e76a341-3abe-45f7-b66b-a39e9537b39a.png)
  
6. In the boxes in the **Name Servers** area, type or copy and paste the values from the following table. 
    
    > [!IMPORTANT]
    > Freeparking NZ will show a warning message. If you have added the correct nameserver value, you can safely ignore this message. 
  
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![FreeparkingNZ-BP-Redelegate-1-4](../media/3d7d4615-4289-4ee8-b2bb-e78b0a829072.png)
  
7. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Redelegate-1-5](../media/9ff45891-3217-4b83-8969-85a23e5222aa.png)
  
8. Choose **Continue** again to confirm your changes. 
    
    ![FreeparkingNZ-BP-Redelegate-1-6](../media/f2b2d3ad-d95f-4d20-8644-f19638137ee6.png)
  
9. Review and update your **Technical Contact** information, and then choose **Save Changes**.
    
    > [!IMPORTANT]
    > You  *must*  update the Technical Contact information with your own company or personal information; for example, the name of your domain administrator. 
  
    (You may need to scroll down.)
    
    ![FreeparkingNZ-BP-Redelegate-1-7](../media/7429f699-981a-497f-b00d-fdd1932f33c7.png)
  
    > [!NOTE]
    > Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

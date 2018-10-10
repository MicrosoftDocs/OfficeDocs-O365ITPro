---
title: "Change nameservers to set up Office 365 with Crazy Domains"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Crazy1'
- 'O365M_DOM_Crazy1'
- 'O365E_DOM_Crazy1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d939c8c9-cf26-4258-a957-881b482dba89

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Crazy Domains."
---

# Change nameservers to set up Office 365 with Crazy Domains

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Crazy Domains](create-dns-records-at-crazy-domains.md).)
  
Here's what you need to do. (Need more help? [Still need help?](change-nameservers-at-crazy-domains.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](change-nameservers-at-crazy-domains.md#BKMK_verify)
    
- [Change your domain's nameserver (NS) records](change-nameservers-at-crazy-domains.md#BKMK_nameservers)
    
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.
    
    ![CrazyDomains-BP-Configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. In the **My Account** section, choose **Domains**.
    
    ![CrazyDomains-BP-Configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. On the **Domain Names** page, in the **Domain** section, choose the name of the domain that you are updating. 
    
    ![CrazyDomains-BP-Configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. In the **DNS Settings** section, choose the drop-down list icon. 
    
    ![CrazyDomains-BP-Configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Choose **Add Record**.
    
    ![CrazyDomains-BP-Configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Choose **TXT Record** from the **Add Record** drop-down list. 
    
    ![CrazyDomains-BP-Verify-1-1](../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. Choose **Add**.
    
    ![CrazyDomains-BP-Verify-1-2](../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Sub Domain**|**Text Record**|
|:-----|:-----|
|(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. Choose **Update**.
    
    ![CrazyDomains-BP-Verify-1-4](../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
  
1. To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.
    
    ![CrazyDomains-BP-Configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. In the **My Account** section, choose **Domains**.
    
    ![CrazyDomains-BP-Configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. On the **Domain Names** page, in the **Domain** section, choose the name of the domain that you are updating. 
    
    ![CrazyDomains-BP-Configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. In the **Name Servers** section, do one of the following: 
    
  - If there are  *only four*  nameservers currently in the list, and if they are named **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com** then you already have the correct nameservers, and you can skip the remainder of this procedure entirely. 
    
  - If the correct nameservers ( **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com** ) are  *not*  already in the list, then continue to the next step in this procedure. 
    
  - If the correct nameservers  *are*  already in the list, but there are also one or more other nameservers listed, skip down and follow Steps 9 through 11 to remove those other nameservers. 
    
5. If the correct nameservers are not yet in the list, choose the drop-down list icon.
    
    ![CrazyDomains-BP-Redelegate-1-1](../media/6d0a5722-ef40-4ed1-8b11-e9838efa47a6.png)
  
6. Choose **Add Name Server** to create an empty row. 
    
    ![CrazyDomains-BP-Redelegate-1-2](../media/f4b01b90-1766-4126-8adb-ac827a524ac2.png)
  
7. Add the first nameserver.
    
    In the **Name Servers** section, in the **Name Server** box in the first empty record, type or copy and paste the **Host Name Field** value from the first row of the following table. 
    
    > [!IMPORTANT]
    > Crazy Domains automatically populates the **IP Address** field after you enter the **Host Name Field** value. 
  
|**Host Name Field**|**IP Address Field**|
|:-----|:-----|
|ns1.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns2.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns3.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
|ns4.bdm.microsoftonline.com  <br/> |(Leave this field empty.)  <br/> |
   
    ![CrazyDomains-BP-Redelegate-1-3](../media/125b4634-5aab-49e7-9e60-a0429e179622.png)
  
8. Add the other nameservers.
    
    Still in the **Name Servers** section, choose **Add Name Server** again and then, in the **Name Server** box in the first empty record, type or copy and paste the **Host Name Field** value from the second row of the table. Repeat these steps for the third and fourth nameservers. 
    
    In the following three steps, you will remove any other nameservers that are listed in the **Name Servers** section. 
    
9. If there are any other nameservers listed in the **Name Servers** section, mark one of those nameservers for deletion by choosing **Delete** for that record. 
    
    ![CrazyDomains-BP-Redelegate-1-4](../media/a901ba93-b072-462a-92fa-ffe2f7dd450c.png)
  
10. Use the same process to mark any other nameservers for deletion, until only the two that you added earlier in this procedure remain unmarked.
    
    ![CrazyDomains-BP-Redelegate-1-5](../media/fe792e47-9d6c-4ef0-93aa-ac8713ef6546.png)
  
11. Choose **Update** to confirm your changes. 
    
    ![CrazyDomains-BP-Redelegate-1-6](../media/be35f940-f8df-49b7-a37e-dbf4be6828da.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  

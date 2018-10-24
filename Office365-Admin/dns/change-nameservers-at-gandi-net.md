---
title: "Change nameservers to set up Office 365 with Gandi.net"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Gandi1'
- 'O365M_DOM_Gandi1'
- 'O365E_DOM_Gandi1'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: e79106cd-5cd1-4d2b-8b60-e6378ec75b51

description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at Gandi.net."
---

# Change nameservers to set up Office 365 with Gandi.net

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Gandi.net](create-dns-records-at-gandi-net.md).)
  
    
## Create a zone file for Office 365 verification

> [!IMPORTANT]
> To verify your domain for Office 365, you need to add a record to the zone file for that domain. You cannot edit an active Gandi.net zone file to create the TXT record you will need. Instead, you must make  *a copy*  of the active Gandi.net zone file to use in the verification process. > This new zone file is used only to help verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the **Default Gandi zone file** row, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-3](../media/2d424e7f-2bc0-4e14-badb-0ebfbedbd632.png)
  
4. In the **Zone file versions** area, choose **Normal** in the **Edit mode** drop-down list. 
    
    ![GandiNet-BP-Configure-1-4-1](../media/584dacfa-2553-4204-a6de-9836528cab41.png)
  
5. Then choose **Copy this zone to edit**.
    
    ![GandiNet-BP-Configure-1-4-2](../media/45656a52-ce16-4198-bb98-ac3f412521b1.png)
  
6. In the **Copy a zone** dialog box, type a new zone name in the **Name** field (for example, Office 365 Verify). 
    
    ![GandiNet-BP-Configure-1-5-1](../media/ad6ec049-8e25-49f6-9d0d-063a03b5f5ea.png)
  
7. Then choose **Submit**.
    
    ![GandiNet-BP-Configure-1-5-2](../media/f038fc81-9751-405a-972e-d6a6c2232033.png)
  
8. On the **Zones \>** ** *zone_name* ** page, choose **Create a new version**.
    
    ![GandiNet-BP-Configure-1-6](../media/35c7f396-5981-4763-b43a-e7355bcc3106.png)
  
Now that you have created the zone file, go on to the next section, where you will add the record that you will need in order to verify your Gandi.net domain with Office 365.
  
## Add a TXT record for verification

> [!IMPORTANT]
> If you have not already done so, complete the [Create a zone file for Office 365 verification](change-nameservers-at-gandi-net.md#BKMK_CreateVerifyZone) procedure in the first section of this article before you begin the procedure in this section. 
  
Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the row for the zone file you created for Office 365 verification, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-14](../media/4a64f39f-c217-4678-b7a3-73c88b366118.png)
  
4. In the **Zone file versions** area, choose **Version 2**.
    
    (Do  *not*  yet choose **Use this version**.)
    
    ![GandiNet-BP-Configure-1-7](../media/b80e4d70-d0e8-48ad-b430-31a1ed203dfb.png)
  
5. Still in the **Zone file versions** area, choose **Add**.
    
    (You may have to scroll down.)
    
    ![GandiNet-BP-Configure-1-8](../media/91742f45-63af-4617-9861-e4c381a8a3d7.png)
  
6. In the **Add a record** section, in the boxes for the new record, type or copy and paste the following values. 
    
    (Select the **Type** and **hours** values from the drop-down lists.) 
    
|**Type**|**TTL**|**Name**|**Value**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |1 hours  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |
   
   ![GandiNet-BP-Verify-1-1](../media/81376f64-3206-4eaa-9ca2-ba0d89266393.png)
  
7. Choose **Submit** to confirm your changes. 
    
    ![GandiNet-BP-Verify-1-2](../media/438d9ebc-4405-4ef8-b7ae-8ca1d73f8251.png)
  
Now that you have created the TXT file that Office 365 will use to verify your Gandi.net domain, go on to the next section, where you will activate the new zone file that contains the record.
  
## Activate the zone file for Office 365 verification

> [!IMPORTANT]
> If you have not already done so, complete the procedures in the first two sections of this article ([Create a zone file for Office 365 verification](change-nameservers-at-gandi-net.md#BKMK_CreateVerifyZone) and [Add a TXT record for verification](change-nameservers-at-gandi-net.md#BKMK_AddVerifyTXT)) before you begin the procedure in this section. 
  
Now you will update your Gandi.net default settings, so that the Office 365 verification zone file becomes the active zone file for the domain that you're changing.
  
> [!CAUTION]
> Failure to do this will prevent Office 365 from verifying your domain. 
  
1. In the **Zone file versions** area, choose **Version 2**.
    
    ![GandiNet-BP-Configure-1-9-1](../media/643fe1c5-6bf6-4f94-ae25-81bffda5a28a.png)
  
2. Then choose **Use this version**.
    
    ![GandiNet-BP-Configure-1-9-2](../media/c7817ce4-c47b-4bf8-a3cb-dca61df111ee.png)
  
3. In the **Use this version** dialog box, choose **Submit**.
    
    ![GandiNet-BP-Configure-1-10](../media/d70a91f6-0633-40a9-8860-ac9ef5287c04.png)
  
4. On the top navigation bar, choose **Domains**.
    
    ![GandiNet-BP-Configure-1-11](../media/ed6981bf-2f97-475c-9e32-c595296e7577.png)
  
5. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
6. On the **Batch zone file change** page, find the new zone file, and then choose **Choose**.
    
    ![GandiNet-BP-Configure-1-12](../media/ae6ce5e4-201e-4cba-998f-3ccfc0dfc874.png)
  
7. Choose **Submit** to confirm your changes. 
    
    ![GandiNet-BP-Configure-1-13](../media/21432aad-91df-448d-bf4a-96245734426c.png)
  
To complete the process of verifying your Gandi.net domain with Office 365, follow the instructions in the next section.
  
## Verify your domain with Office 365

> [!IMPORTANT]
> If you have not already done so, complete the procedures in the first three sections of this article ([Create a zone file for Office 365 verification](change-nameservers-at-gandi-net.md#BKMK_CreateVerifyZone), [Add a TXT record for verification](change-nameservers-at-gandi-net.md#BKMK_AddVerifyTXT), and [Activate the zone file for Office 365 verification](change-nameservers-at-gandi-net.md#BKMK_ActivateVerifyZone)) before you begin the procedure in this section. 
  
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
  
Now that you have verified your Gandi.net domain with Office 365, you can go on to change your nameserver records so that they point to Office 365. The following section will guide you through that process.
  
## Change your domain's nameserver (NS) records

> [!IMPORTANT]
> If you have not yet verified your Gandi.net domain with Office 365, do so now by following the procedures in the first four sections of this article, beginning with [Create a zone file for Office 365 verification](change-nameservers-at-gandi-net.md#BKMK_CreateVerifyZone). 
  
To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
> [!IMPORTANT]
>  When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list. 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Update DNS**.
    
    ![GandiNet-BP-Redelegate-1-1](../media/3353f34f-f306-430a-8fdc-9c019c4a5dcd.png)
  
3.     > [!CAUTION]
    > Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.) 
  
    On the **Domain Names** page, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard. 
    
    ![GandiNet-BP-Redelegate-1-2](../media/d8ba3226-a863-46cf-b2cd-8addb8f7a4c6.png)
  
4. In the **DNS1** - **DNS4** boxes, type or copy and paste the values from the following table. 
    
|||
|:-----|:-----|
|**DNS1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**DNS2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**DNS3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**DNS4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![GandiNet-BP-Redelegate-1-3](../media/6ef2bec6-d637-4e72-8ea6-8e47fb09f492.png)
  
5. Choose **Submit**.
    
    ![GandiNet-BP-Redelegate-1-4](../media/c711868c-9206-4f47-8b12-f33d70405bab.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


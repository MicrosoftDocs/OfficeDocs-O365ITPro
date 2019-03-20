---
title: "Create DNS records at Gandi.net for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Gandi'
- 'O365M_DOM_Gandi'
- 'O365E_DOM_Gandi'
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
ms.assetid: 5e605518-086a-4f58-95c7-8622666ad347
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Gandi.net for Office 365.
"
---

# Create DNS records at Gandi.net for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Gandi.net is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
There are two main parts to this process: first you will verify your domain, and then you will add DNS records to it. 

To verify and configure your domain for Office 365, you need to add several DNS records to that domain, using what is called a zone file. You cannot edit an active Gandi.net zone file. Instead, you will make  *only one copy*  of the active Gandi.net zone file for the purpose of verifying your domain, and then create  *only one other copy*  in which you will create  *all*  of your DNS records for Office 365. 
  
When you have completed both of these tasks, your Gandi.net domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Create a zone file for Office 365 verification
<a name="BKMK_CreateVerifyZone"> </a>

To verify your domain for Office 365, you need to add a record to the zone file for that domain. As stated above, you cannot edit an active Gandi.net zone file. Instead, you will make  *only one copy*  of the active Gandi.net zone file to use in the process of verifying your Gandi.net domain with Office 365. 
  
(When you have completed the verification process, you will create  *only one other copy*  , in which you will create  *all*  of your DNS records for Office 365.) 
  
This first zone file is used only to help verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. (The second zone file, on the other hand, you will keep, as it will contain all of the DNS records that you have created so that your domain will work with Office 365.)
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the **Default Gandi zone file** row, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-3](../media/2d424e7f-2bc0-4e14-badb-0ebfbedbd632.png)
  
4. In the **Zone file versions** area, choose **Normal** in the **Edit mode**.
    
    ![GandiNet-BP-Configure-1-4-1](../media/584dacfa-2553-4204-a6de-9836528cab41.png)
  
5. Then choose **Copy this zone to edit**.
    
    ![GandiNet-BP-Configure-1-4-2](../media/45656a52-ce16-4198-bb98-ac3f412521b1.png)
  
6. In the **Copy a zone** dialog box, type a new zone name in the **Name** field (for example, Office 365 Verify). 
    
    ![GandiNet-BP-Configure-1-5-1](../media/ad6ec049-8e25-49f6-9d0d-063a03b5f5ea.png)
  
7. Then choose **Submit**.
    
    ![GandiNet-BP-Configure-1-5-2](../media/f038fc81-9751-405a-972e-d6a6c2232033.png)
  
8. On the **Zones \>** ***zone_name*** page, choose **Create a new version**.
    
    ![GandiNet-BP-Configure-1-6](../media/35c7f396-5981-4763-b43a-e7355bcc3106.png)
  
Now that you have created the zone file, go on to the next section, where you will add the TXT record that you will need in order to verify your Gandi.net domain with Office 365.
  
## Add a TXT record for verification
<a name="BKMK_AddVerifyTXT"> </a>

If you have not already done so, complete the [Create a zone file for Office 365 verification](#create-a-zone-file-for-office-365-verification) procedure in the first section of this article before you begin the procedure in this section. 
  
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
  
6. In the **Add a record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type**, **TTL**, and **hours** values from the drop-down lists.) 
    
    |**Type**|**TTL**|**Name**|**Value**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |1 hours  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![GandiNet-BP-Verify-1-1](../media/81376f64-3206-4eaa-9ca2-ba0d89266393.png)
  
7. Choose **Submit** to confirm your changes. 
    
    ![GandiNet-BP-Verify-1-2](../media/438d9ebc-4405-4ef8-b7ae-8ca1d73f8251.png)
  
Now that you have created the TXT file that Office 365 will use to verify your Gandi.net domain, go on to the next section, where you will activate the new zone file that contains the record.
  
## Activate the zone file for Office 365 verification
<a name="BKMK_ActivateVerifyZone"> </a>

If you have not already done so, complete the procedures in the first two sections of this article ([Create a zone file for Office 365 verification](#create-a-zone-file-for-office-365-verification) and [Add a TXT record for verification](#add-a-txt-record-for-verification)) before you begin the procedure in this section.
  
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
<a name="BKMK_VerifyDomain"> </a>

If you have not already done so, complete the procedures in the first three sections of this article ([Create a zone file for Office 365 verification](#create-a-zone-file-for-office-365-verification), [Add a TXT record for verification](#add-a-txt-record-for-verification), and [Activate the zone file for Office 365 verification](#activate-the-zone-file-for-office-365-verification)) before you begin the procedure in this section.
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
Now that you have verified your Gandi.net domain with Office 365, you can go on to create  *only one other copy*  of the active Gandi.net zone file, in which you will create  *all*  of the DNS records that your Gandi.net domains will need to work with Office 365. The remaining sections in this article will guide you through that process. 
  
## Create a zone file for Office 365 DNS records
<a name="BKMK_CreateDNSzone"> </a>

If you have not yet verified your Gandi.net domain with Office 365, do so now by following the procedures in the first four sections of this article, beginning with [Create a zone file for Office 365 verification](#create-a-zone-file-for-office-365-verification).
  
The zone file that you will create now is where you will create the DNS records that you need for Office 365. Your Office 365 account will not work without these records. When you have finished creating  *all of*  your DNS records, you will designate this zone file as your active Gandi.net zone file, using it instead of the zone file that you created to verify your domain in the previous sections. 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the **Default Gandi zone file** row, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-15](../media/72bd5080-e28c-4e58-acd3-3f77c073a270.png)
  
4. In the **Zone file versions** area, choose **Normal** in the **Edit mode** drop-down list. 
    
    ![GandiNet-BP-Configure-1-4-1](../media/584dacfa-2553-4204-a6de-9836528cab41.png)
  
5. Then choose **Copy this zone to edit**.
    
    ![GandiNet-BP-Configure-1-4-2](../media/45656a52-ce16-4198-bb98-ac3f412521b1.png)
  
6. In the **Copy a zone** dialog box, type a new zone name in the **Name** field (for example, Office 365 DNS Records). 
    
    ![GandiNet-BP-Configure-1-16-1](../media/ce611f1c-c277-4e2b-ada1-b3bc634a7e04.png)
  
7. Then choose **Submit**.
    
    ![GandiNet-BP-Configure-1-16-2](../media/a43366f5-0c4e-4885-969d-c534d8fb8649.png)
  
8. On the **Zones \>** ***zone_name*** page, choose **Create a new version**.
    
    ![GandiNet-BP-Configure-1-17](../media/613fd204-3a51-4f60-8caa-7aba391836eb.png)
  
Now that you have created the new zone file, you will add to it all of the DNS records that your Gandi.net domain must contain to work correctly with Office 365. You will create four types of records: MX, CNAME, SPF, and SRV. You can create these records in any order, but you should create  *all of them*  before you activate your new zone file, which you will do in the final section of this article. 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_AddMX"> </a>

> [!IMPORTANT]
> Before you create DNS records for your Gandi.net domain, you must first verify your domain with Office 365 (see the first four sections of this article) and then [Create a zone file for Office 365 DNS records](#create-a-zone-file-for-office-365-verification) in which you will create the DNS records. When you have created all of the records that you need, you will [activate the zone file for Office 365 DNS records](#activate-the-zone-file-for-office-365-dns-records). 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the row for the zone file you created for Office 365 DNS records, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-18](../media/a9927c0b-bd6f-416c-9104-a40cd23eb6ae.png)
  
4. In the **Zone file versions** area, choose **Version 2**.
    
    (Do  *not*  yet choose **Use this version**.)
    
    ![GandiNet-BP-Configure-1-7](../media/b80e4d70-d0e8-48ad-b430-31a1ed203dfb.png)
  
5. Still in the **Zone file versions** area, choose **Add**.
    
    (You may have to scroll down.)
    
    ![GandiNet-BP-Configure-1-8](../media/91742f45-63af-4617-9861-e4c381a8a3d7.png)
  
6. In the **Add a record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type**, **TTL**, and **hours** values from the drop-down lists.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Type  <br/> |TTL  <br/> |Name  <br/> |Value  <br/> |MX Priority  <br/> |
    |MX  <br/> |1 hours  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/>**Note:** Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![GandiNet-BP-Configure-2-1](../media/d05d2d09-bd6c-4d60-998c-3a9e8a0057e6.png)
  
7. Choose **Submit**.
    
    ![GandiNet-BP-Configure-2-2](../media/32cacfc1-ae64-4ac2-a59d-21064276caa0.png)
  
8. If there are any other MX records, delete one of them by choosing the **Delete (X)** icon for that record. 
    
    ![GandiNet-BP-Configure-2-3](../media/0a54a8b9-272f-4654-83b3-972105d51e82.png)
  
9. Choose **Delete** to confirm the deletion. 
    
    ![GandiNet-BP-Configure-2-4](../media/89c920d8-ed26-4507-935d-8e0772691286.png)
  
10. Use the same process to delete any other remaining MX records, leaving only the one that you created earlier in this procedure.
    
## Add the six CNAME records that are required for Office 365
<a name="BKMK_AddCNAMEs"> </a>

> [!IMPORTANT]
> Before you create DNS records for your Gandi.net domain, you must first verify your domain with Office 365 (see the first four sections of this article) and then [Create a zone file for Office 365 DNS records](#create-a-zone-file-for-office-365-verification) in which you will create the DNS records. When you have created all of the records that you need, you will [Activate the zone file for Office 365 DNS records](#activate-the-zone-file-for-office-365-dns-records). 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the row for the zone file you created for Office 365 DNS records, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-18](../media/a9927c0b-bd6f-416c-9104-a40cd23eb6ae.png)
  
4. In the **Zone file versions** area, choose **Version 2**.
    
    (Do  *not*  yet choose **Use this version**.)
    
5. Still in the **Zone file versions** area, choose **Add**.
    
    (You may have to scroll down.)
    
    ![GandiNet-BP-Configure-1-7](../media/b80e4d70-d0e8-48ad-b430-31a1ed203dfb.png)
  
6. Add the first of the six CNAME records.
    
    In the **Add a record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
    (Select the **Type**, **TTL**, and **hours** values from the drop-down lists.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |Type  <br/> |TTL  <br/> |Name  <br/> |Value  <br/> |
    |CNAME  <br/> |1 hours  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |CNAME  <br/> |1 hours  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |CNAME  <br/> |1 hours  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |CNAME  <br/> |1 hours  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |CNAME  <br/> |1 hours  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |CNAME  <br/> |1 hours  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![GandiNet-BP-Configure-3-1](../media/a707be8b-a362-44ac-a1b6-0bca3fe94a90.png)
  
7. Choose **Submit**.
    
    ![GandiNet-BP-Configure-3-2](../media/9d3c02c1-37be-413a-a390-b9af815728d2.png)
  
8. Add the other five CNAME records.
    
    In the **Zone file versions** area, choose **Add**, create a record using the values from the next row in the table, and then again choose **Submit** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_AddSpamTXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
> [!IMPORTANT]
> Before you create DNS records for your Gandi.net domain, you must first verify your domain with Office 365 (see the first four sections of this article) and then [Create a zone file for Office 365 DNS records](#create-a-zone-file-for-office-365-verification) in which you will create the DNS records. When you have created all of the records that you need, you will [activate the zone file for Office 365 DNS records](#activate-the-zone-file-for-office-365-dns-records). 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the row for the zone file you created for Office 365 DNS records, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-18](../media/a9927c0b-bd6f-416c-9104-a40cd23eb6ae.png)
  
4. In the **Zone file versions** area, choose **Version 2**.
    
    (Do  *not*  yet choose **Use this version**.)
    
    ![GandiNet-BP-Configure-1-7](../media/b80e4d70-d0e8-48ad-b430-31a1ed203dfb.png)
  
5. Still in the **Zone file versions** area, choose **Add**.
    
    (You may have to scroll down.)
    
    ![GandiNet-BP-Configure-1-8](../media/91742f45-63af-4617-9861-e4c381a8a3d7.png)
  
6. In the **Add a record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type**, **TTL**, and **hours** values from the drop-down lists.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |Type  <br/> |TTL  <br/> |Name  <br/> |Value  <br/> |
    |TXT  <br/> |1 hours  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![GandiNet-BP-Configure-4-1](../media/2e5fc2a4-cd0d-4074-8552-08e07dcfa1ee.png)
  
7. Choose **Submit**.
    
    ![GandiNet-BP-Configure-4-2](../media/b4ef4686-9653-459b-868c-45ae2d64b571.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_AddSRVs"> </a>

> [!IMPORTANT]
> Before you create DNS records for your Gandi.net domain, you must first verify your domain with Office 365 (see the first four sections of this article) and then [Create a zone file for Office 365 DNS records](#create-a-zone-file-for-office-365-verification) in which you will create the DNS records. When you have created all of the records that you need, you will [activate the zone file for Office 365 DNS records](#activate-the-zone-file-for-office-365-dns-records). 
  
1. To get started, go to your domains page at Gandi.net by using [this link](https://www.gandi.net/admin/domain). You'll be prompted to log in first.
    
    ![GandiNet-BP-Configure-1-1](../media/7f746401-f204-4b10-b2d3-bf3312185b62.png)
  
2. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
3. On the **Batch zone file change** page, in the row for the zone file you created for Office 365 DNS records, choose the **Modify (pencil)** icon. 
    
    ![GandiNet-BP-Configure-1-18](../media/a9927c0b-bd6f-416c-9104-a40cd23eb6ae.png)
  
4. In the **Zone file versions** area, choose **Version 2**.
    
    (Do  *not*  yet choose **Use this version**.)
    
    ![GandiNet-BP-Configure-1-7](../media/b80e4d70-d0e8-48ad-b430-31a1ed203dfb.png)
  
5. Still in the **Zone file versions** area, choose **Add**.
    
    (You may have to scroll down.)
    
    ![GandiNet-BP-Configure-1-8](../media/91742f45-63af-4617-9861-e4c381a8a3d7.png)
  
6. Add the first of the two SRV records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type**, **TTL**, and **hours** values from the drop-down lists.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |Type|TTL|Name|Value|
    |SRV|1 hours|_sip._tls|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
    |SRV|1 hours|_sipfederationtls._tcp|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![GandiNet-BP-Configure-5-1](../media/5c43cffc-771e-494b-ab68-ad1fbd05e00a.png)
  
7. Choose **Submit**.
    
    ![GandiNet-BP-Configure-5-2](../media/5570bb95-ba99-442b-972e-c4d54bac7db7.png)
  
8. Add the other SRV record:
    
    In the **Zone file versions** area, choose **Add**, create a record using the values from the next row in the table, and then again choose **Submit** to complete that record. 
    
## Activate the zone file for Office 365 DNS records
<a name="BKMK_ActivateDNSzone"> </a>

> [!IMPORTANT]
> If you have  *not*  yet verified your domain and created  *all*  of the DNS records that you need, we strongly recommend that you do so before performing this final procedure. All of the instructions you will need are provided in the preceding sections of this article. 
  
If you  *have*  now verified your domain and created all of the MX, CNAME, SPF, and SRV records that you need for Office 365, you will now again update your Gandi.net default settings, this time so that the Office 365 DNS Records zone file replaces the Office 365 Verification zone file, becoming the active zone file for the domain that you're changing. 
  
> [!CAUTION]
> Failure to make this change will prevent your Gandi.net domain from working properly with Office 365. 
  
1. In the **Zone file versions** area, choose **Version 2**.
    
    ![GandiNet-BP-Configure-1-9-1](../media/643fe1c5-6bf6-4f94-ae25-81bffda5a28a.png)
  
2. Then choose **Use this version**.
    
    ![GandiNet-BP-Configure-1-9-2](../media/c7817ce4-c47b-4bf8-a3cb-dca61df111ee.png)
  
3. In the **Use this version** dialog box, choose **Submit**.
    
    ![GandiNet-BP-Configure-1-10](../media/d70a91f6-0633-40a9-8860-ac9ef5287c04.png)
  
4. On the top navigation bar, choose **Domains**.
    
    ![GandiNet-BP-Configure-1-19](../media/3c3370ae-1e30-49b3-9bc1-99fdecbdc9da.png)
  
5. On the **Domains** page, select the check box beside the name of the domain that you're changing. 
    
    Then, in the **Select the lines and choose an action** drop-down list that opens, scroll to the **Technical changes** section, and then choose **Change the zone file**.
    
    ![GandiNet-BP-Configure-1-2](../media/33e64794-02b9-467b-bb47-e9de583683b8.png)
  
6. On the **Batch zone file change** page, find the new zone file (the one to which you've added all of your Office 365 DNS records), and then choose **Choose**.
    
    ![GandiNet-BP-Configure-1-20](../media/5e945bde-56a8-495e-9a36-def13e4f70e6.png)
  
7. Choose **Submit** to confirm your changes. 
    
    ![GandiNet-BP-Configure-1-21](../media/f4c330e8-2cbc-4aa6-9962-aea4cd1e766e.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

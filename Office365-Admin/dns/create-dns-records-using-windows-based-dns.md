---
title: "Create DNS records for Office 365 using Windows-based DNS"
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Windows-based DNS for Office 365."
---

# Create DNS records for Office 365 using Windows-based DNS

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
|||
|:-----|:-----|
|[![Telephone](../media/f6cb0dc3-d57c-4870-9447-ba000b66d846.png)](../contact-support-for-business-products.md)|**Want some help?** <br/> [Call support](../contact-support-for-business-products.md) .  <br/> |
   
If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.
  
To get started, you need to [find the DNS records for your domain in Windows-based DNS](create-dns-records-using-windows-based-dns.md#BKMK_find_your_dns_1) so you can update them. Also, if you're planning to synchronize your on-premises Active Directory with Office 365, [Non-routable email address used as a UPN in your on-prem Active Directory](create-dns-records-using-windows-based-dns.md#BKMK_ADNote).
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-using-windows-based-dns.md#BKMK_NeedHelp).)
  
- [Add MX record](create-dns-records-using-windows-based-dns.md#BKMK_add_MX)
    
- [Add CNAME records](create-dns-records-using-windows-based-dns.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-using-windows-based-dns.md#BKMK_add_TXT)
    
- [Add SRV records](create-dns-records-using-windows-based-dns.md#BKMK_add_SRV)
    
If you haven't yet verified your domain, you'll also need to add a record to do that:
  
- [Add a record to verify that you own the domain, if you haven't already](create-dns-records-using-windows-based-dns.md#BKMK_verify)
    
If you have a SharePoint Online Public Website, you can [set it up to use your custom domain](https://support.office.com/article/d4a91862-4707-45fd-998f-4beb5ee26b65.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Find your DNS records in Windows-based DNS
<a name="BKMK_find_your_dns_1"> </a>

|****Task****|
|:-----|
|Go to the page that has the DNS records for your domain.  <br/> If you're working in Windows Server 2008, go to Start \> Run. If you're working in Windows Server 2012, press the Windows key and r. Type dnsmgmnt.msc, and then choose OK. In DNS Manager, expand \<DNS server name\>  \> Forward Lookup Zones. Choose your domain. You're now ready to create the DNS records.  <br/> |
   
## Add MX record
<a name="BKMK_add_MX"> </a>

Add an MX record so email for your domain will come to Office 365.
  
|****Task****|
|:-----|
|The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.  <br/> From the MX row in the Exchange Online section of the Add DNS records page in Office 365, copy the value listed under Points to address. You'll use this value in the record you're creating in this task. On the DNS Manager page for the domain, go to Action \> Mail Exchanger (MX). To find this page for the domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Host Name: @Address: Paste the Points to address  value that you just copied from Office 365 here.  Pref: 0 For more information about priority, see What is MX priority?Choose Save Changes. |
|Remove any obsolete MX records.  <br/> If you have any old MX records for this domain that route email somewhere else:  <br/> Select the check box next to each old record, and then choose Delete. Choose OK. |
   
## Add CNAME records
<a name="BKMK_add_CNAME"> </a>

Add the CNAME records that are required for Office 365. If additional CNAME records are listed in Office 365, add those following the same general steps shown here.
  
> [!IMPORTANT]
> If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (If you do not have MDM, you can skip this step.) 
  
|****Task****|
|:-----|
|Add the email (Exchange) Autodiscover CNAME record.  <br/> On the DNS Manager page for the domain, go to Action \> CNAME (CNAME). To find this page for your domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Host Name: autodiscoverType: CNAMEAddress: autodiscover.outlook.comChoose OK. |
|Add the SIP CNAME record.  <br/> On the DNS Manager page for the domain, go to Action \> CNAME (CNAME). To find this page for your domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Host Name: sipType: CNAMEAddress: sipdir.online.lync.comChoose OK. |
|Add the Skype for Business Online Autodiscover CNAME record.  <br/> On the DNS Manager page for the domain, go to Action \> CNAME (CNAME). To find this page for your domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Host Name: lyncdiscoverType: CNAMEAddress: webdir.online.lync.comChoose OK. |
   
### Add two CNAME records for Mobile Device Management (MDM) for Office 365

> [!IMPORTANT]
> If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (If you do not have MDM, you can skip this step.) 
  
|****Task****|
|:-----|
|Add the MDM Enterpriseregistration CNAME record.  <br/> On the DNS Manager page for the domain, go to Action \> CNAME (CNAME). To find this page for your domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Host Name: enterpriseregistrationType: CNAMEAddress: enterpriseregistration.windows.netChoose OK. |
|Add the MDM Enterpriseenrollment CNAME record.  <br/> On the DNS Manager page for the domain, go to Action \> CNAME (CNAME). To find this page for your domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Host Name: enterpriseenrollmentType: CNAMEAddress: enterpriseenrollment-s.manage.microsoft.comChoose OK. |
   
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
Add the SPF TXT record for your domain to help prevent email spam.
  
|****Task****|****What you'll see****|
|:-----|:-----|
|You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.  <br/> |
On the DNS Manager page for your domain, go to Action \> Text (TXT). To find this page for your domain, see Find your DNS records in Windows-based DNS.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values.  Important In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain. In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name. This KB article on setting up SPF records has more information.  Host type: @Record Type: TXTAddress: v=spf1 include:spf.protection.outlook.com -all We recommend copying and pasting this entry, so that all of the spacing stays correct.  Choose OK. |
   
## Add SRV records
<a name="BKMK_add_SRV"> </a>

Add the two SRV records that are required for Office 365.
  
|****Task****|
|:-----|
|Add the SIP SRV record for Skype for Business Online web conferencing.  <br/> On the DNS Manager page for your domain, go to Action \> Other New Records. To find this page for your domain, see Find your DNS records in Windows-based DNS. In the Resource Record Type window, choose Service Location (SRV), and then click Create Record.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Service: _sipProtocol: _tlsPriority: 100Weight: 1Port: 443Target (Hostname): sipdir.online.lync.comChoose OK. |
|Add the SIP SRV record for Skype for Business Online federation.  <br/> On the DNS Manager page for your domain, go to Action \> Other New Records. To find this page for your domain, see Find your DNS records in Windows-based DNS. In the Resource Record Type window, choose Service Location (SRV), and then click Create Record.  In the New Resource Record dialog box, make sure that the fields are set to precisely the following values:  Service: _sipfederationtlsProtocol: _tcpPriority: 100Weight: 1Port: 5061Target (Hostname): sipfed.online.lync.comChoose OK. |
   
## Add a record to verify that you own the domain, if you haven't already
<a name="BKMK_verify"> </a>

Before you add the DNS records to set up your Office 365 services, Office 365 has to confirm that you own the domain you're adding. To do this, you add a record, following the steps below.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. 
  
|****Task****|
|:-----|
|Gather information from Office 365.  <br/> Sign in to Office 365  with your work or school account. Choose Setup \> Domains. On the Manage domains page, in the Action column for the domain that you are verifying, choose Start setup. NoteIf you haven't yet added a domain, see Verify your domain in Office 365. On the Add a domain to Office 365 page, choose Start step 1. On the Confirm that you ownyour_domain  page, in the See instructions for performing this step with drop-down list, choose General instructions. From the table, copy the Destination or Points to Address value. You'll need it for the next step. We recommend copying and pasting this value, so that all of the spacing stays correct. |
|Add a TXT record.  <br/> On the DNS Manager page for your domain, go to Action \> Text (TXT). To find this page for your domain, see Find your DNS records in Windows-based DNS. In the New Resource Record dialog box, choose Edit.  In the Custom Host Names area of the New Resource Record dialog box, make sure that the fields are set to precisely the following values.  Important In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain. In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name. This KB article on setting up SPF records has more information.  Host Name: @Type: TXTAddress: Paste the Destination or Points to Address value that you just copied from Office 365 here.  Choose OK, and then choose Done. |
|Verify your domain in Office 365.  <br/> > [!IMPORTANT]> Wait about 15 minutes before you do this, so the record you just created can update across the Internet.           Go back to Office 365 and follow the steps below to request a verification check. The check looks for the TXT record you added in the previous step. When it finds the correct TXT record, the domain is verified.  <br/> Choose Setup \> Domains. On the Manage domains page, in the Action column for the domain you are verifying, choose Start setup. On the Confirm that you ownyour_domain  page, choose done, verify now and then, in the confirmation dialog box, choose Finish. |
   
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Non-routable email address used as a UPN in your on-prem Active Directory
<a name="BKMK_ADNote"> </a>

If you're planning to synchronize your on-premises Active Directory with Office 365, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local. If you need to change your UPN suffix, [How to prepare a non-routable domain for directory synchronization](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

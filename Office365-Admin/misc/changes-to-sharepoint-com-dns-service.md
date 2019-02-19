---
title: "Changes to SharePoint.com DNS service"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- MET150
- SPO160
ms.assetid: 7d4ae748-f504-44c8-b958-c79c1486801c
ROBOTS: NOINDEX
description: "Learn about the transition to a new DNS provider to improve DNS reliability for your SharePoint.com domains."
---

# Changes to SharePoint.com DNS service

On October 15, 2017, we transitioned to a new DNS provider to improve DNS reliability for your SharePoint.com domains.
  
 **This is only applicable for SharePoint sites ending with  ".sharepoint.com".**
  
If you need to find out how many DNS queries were received for your SharePoint domain names, please engage support.
  
If you have hard-coded server addresses for SharePoint.com domains in your DNS configurations, please update them with the provided new server addresses before January 30th, 2018 or you will experience a service outage when trying to access SharePoint.com.  No change is required for any other domain (like yourdomain.com) 
  
## Check to see which nameserver your organization is using

1. Open a command prompt from any computer from your organization
    
2. Enter this command:
    
  ```
  nslookup -querytype=soa sharepoint.com
  ```

3. You'll get a response that looks something like this:
    
  ```
  Server:  UnKnown
  Address:  2001:4898::1050:1050
  Non-authoritative answer:
  sharepoint.com
          primary name server = ns1-203.azure-dns.com
          responsible mail addr = azuredns-hostmaster.microsoft.com
          serial  = 1
          refresh = 3600 (1 hour)
          retry   = 300 (5 mins)
          expire  = 2419200 (28 days)
          default TTL = 300 (5 mins)
  ```

4. If the  *"primary name server ="*  field says **\*-\*.azure-dns.\*** as above, no action is needed. 
    
5. If the  *"primary name server ="*  field says **\*.bdm.microsoftonline.com** it means you need to update NS servers in your DNS configuration. You can either engage Microsoft support or work with your DNS administrators to fix this. 
    
> [!NOTE]
> If you have any monitoring software which sends DNS requests to SharePoint.com domains, verify that they use the new server addresses for all DNS queries. 
  
- **New DNS server addresses:**
    
  - ns4-203.azure-dns.info
    
  - ns3-203.azure-dns.org
    
  - ns2-203.azure-dns.net
    
  - ns1-203.azure-dns.com
    
- **For reference, here are the old DNS server addresses:**
    
  - ns1.bdm.microsoftonline.com
    
  - ns2.bdm.microsoftonline.com
    
  - ns3.bdm.microsoftonline.com
    
  - ns4.bdm.microsoftonline.com
    


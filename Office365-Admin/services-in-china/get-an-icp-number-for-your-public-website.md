---
title: "Get an Internet Content Provider (ICP) number for your public website"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 12/28/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: bfa6e6b8-3301-4da8-b9e4-1a7c36aabd10
description: "This topic applies to Office 365 operated by 21Vianet in China. This is how you get an Internet Content Provider (ICP) number for your public website."
---

# Get an Internet Content Provider (ICP) number for your public website

All public websites in China must have an ICP number. This means that if you have a SharePoint Online public website, it must be associated with an ICP number, whether you're using the default partner.onmschina.cn domain provided by Office 365 operated by 21Vianet, or your own domain name. The ICP number must appear on your website home page, and you must install a certificate.
  
> [!CAUTION]
>  If you don't have an ICP number, your website can be shut down by the hosting provider with no notice. 
  
You can use one ICP number for multiple websites owned by the same company. If you already have an ICP number for your company website, you can add your SharePoint Online public website to that ICP number by changing your ICP information at your hosting provider or domain provider. You can use the MIIT website to check whether a domain already has an ICP number: **http://www.miibeian.gov.cn** (in Chinese). 
  
> [!NOTE]
> The SharePoint Online Public Website information in this article only applies if your organization purchased Office 365 prior to March 9, 2015. 
  
## Which type of ICP number do I need?
<a name="__ref353434425"> </a>

There are two types of ICP numbers issued by the Chinese Ministry of Industry and Information Technology (MIIT) (中华人民共和国工业和信息化部) at the provincial level:
  
- ICP license **** — for example, 京ICP证XXXXXXXX号 — is used for commercial (operational) websites. This applies to any website that allows a customer to purchase goods or services online. 
    
- ICP filing **** — for example, 京ICP备XXXXXXXX号 — is used for non-commercial (informational) websites. This applies to websites that don't include direct sales. 
    
## Get a new ICP number
<a name="__ref353434425"> </a>

After you provide the necessary documents to your provider, the provider registers the ICP number for you. After all required documents are submitted, it typically takes 20 business days to get an ICP number. Although there is no cost to register with MIIT, your provider charges you a fee. For more information about the cost, the documents required, and detailed steps for ICP license and ICP filing, contact your provider. Here's an overview of the process:
  
1. Submit the required documents to the provider. 
    
2. The provider reviews your documents. 
    
  - If the documents are not valid, you're asked to submit additional documents. 
    
  - If the documents are valid, the provider submits the documents to the provincial MIIT ICP license registration system. 
    
3. MIIT reviews the ICP license application documents. 
    
  - If approved, MIIT sends you an email message with an official ICP license registration number and a certificate. MIIT adds your ICP number to the MIIT ICP registration system.
    
  - If not approved, MIIT tells the provider the reason. Then the provider asks you for more documents and you return to step 2. 
    
### Required documents

In general, if you own your website as an individual, you have to submit the following:
  
- Copy of your personal ID
    
- Website information authenticity form
    
- Information security form
    
- Copy of your domain certificate 
    
If you represent a commercial company, you also have to submit the following: 
  
- Copy of your business license 
    
- Your organization code certificate
    
> [!NOTE]
>  21Vianet can also help you register the ICP number. You can sign in to the ICP application website supported by 21Vianet at **http://icp.cloud.21vianet.com** and follow the prompts to provide required information. For more information, contact [mailto:icpsupport@21vianet.com](mailto:icpsupport@21vianet.com). 
  
Learn more about MIIT License Registration at **http://www.miibeian.gov.cn** (in Chinese). 
  
## Update your website after receiving your ICP number
<a name="__ref353434425"> </a>

After you receive the ICP license and the certificate, do the following:
  
1. Copy or upload the certificate file **bazx.cert** to the directory **cert/.** This file must be accessible through the following link:  *http://your website IP or domain name* **/cert/bazs.cert**.
    
    > [!NOTE]
    >  If you can't upload the certificate to the directory, contact your provider. 
  
2. At the bottom of your website's home page:
    
1. Add the ICP number.
    
2. Add a link to MIIT License Registration at **http://www.miibeian.gov.cn** (in Chinese). 
    


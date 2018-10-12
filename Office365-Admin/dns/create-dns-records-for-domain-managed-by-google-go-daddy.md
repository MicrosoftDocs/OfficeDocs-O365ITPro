---
title: "Create DNS records when your domain is managed by Google (Go Daddy)"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f1369214-9880-48c0-923c-d28eb795ef7b
description: "Learn to access GoDaddy and create DNS through the Google Domains page."
---

# Create DNS records when your domain is managed by Google (Go Daddy)

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.
  
If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with GoDaddy. 
  
You can access GoDaddy, and create DNS, through the Google **Domains** page. Just follow the steps in this article. (Need more help? [Still need help?](create-dns-records-for-domain-managed-by-google-go-daddy.md#BKMK_NeedHelp).)
  
## Create the DNS record

1. At the [Google Admin console](https://www.google.com/work/apps/business), choose **Sign In**.
    
    ![Google-Apps-Configure-1-1-0](../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Enter your domain name, and then choose **Go**.
    
    ![Google-Apps-Configure-1-1-1](../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. At the bottom of the page, choose **More controls**.
    
    ![Google-Apps-Configure-1-2-0](../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Choose **Domains**.
    
    ![Google-Apps-Configure-1-2-1](../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. On the **Domains** page, choose **Add/remove domains**.
    
    ![Google-Apps-Configure-1-2-2](../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. On the **Domains** page, choose **Advanced DNS settings**.
    
    > [!NOTE]
    > If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page. Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps. [See Access DNS records from a partner host](https://support.google.com/a/answer/54693?hl=en) for more information. 
  
    ![Google-Apps-Configure-1-3](../media/93504e2e-ab6b-4545-b9da-198c723bc825.png)
  
7. On the **Advanced DNS settings** page, choose **Sign in to DNS Console**. Note the **Sign-in name** and **Password** information. You'll need it in the next step. 
    
    ![Google-Apps-Configure-1-4](../media/56302527-1fc5-48a1-99b2-e7accf3a92b2.png)
  
8. Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page. 
    
    ![Google-Apps-Configure-1-5](../media/6e9cdab4-9691-4ddc-b6d4-cbb9e0cf9d96.png)
  
9. On the **Domains** page, choose your ** *domain_name* **. 
    
    ![Google-Apps-Configure-1-6](../media/9f81e100-24bf-4692-a3b9-0eb5b35ef097.png)
  
10. On the **Domain Details** page, choose the **DNS Zone File** tab, and then choose **Add Record**.
    
    ![Google-Apps-Configure-1-7](../media/485ded2d-22d3-43d2-ac1e-c7b659dff157.png)
  
11. On the **Add Zone Record** page, in the boxes for the new record, type or copy and paste the following values. 
    
|****RECORD TYPE****|****HOST****|****TXT VALUE****|****TTL****|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> ||1 Hour  <br/> |
> [!NOTE]
> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. 
  
[How do I find this?](../get-help-with-domains/information-for-dns-records.md)
  

   
  
12. Choose **Finish**.
    
    ![Google-Apps-Configure-1-10](../media/ee5695cd-b53f-4dd3-9c70-ee0a5380ddf3.png)
  
13. Choose **Save Changes**.
    
    ![Google-Apps-Configure-1-11](../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

---
title: "Manage Yammer domains in Office 365"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 9/11/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: 9d9f9ee8-7c56-4f50-81f3-aa0a8d761e14
description: "When you add or remove verified domains in Office 365, they are automatically added or removed from your Yammer network."
---

# Manage Yammer domains in Office 365

As the Office 365 administrator, you manage Yammer domains in Office 365 from the **Domains** link in the Office 365 admin center. When you add or remove a domain in Office 365, it will be automatically added to or removed from the corresponding Yammer network, usually within minutes. 
  
- If you just have one domain, or don't have a legacy Yammer network from before you started using Office 365, once your domain is set up in Office 365, your Yammer network is automatically created.
    
- If you have multiple domains but no legacy Yammer networks, setting up your domains in Office 365 is straightforward. Users in all domains you add to Office 365 can use your Yammer network.
    
- It gets a little more complicated when you have a legacy Yammer network associated with one or more of your domains.
    
## Add a domain to Yammer
<a name="add"></a>
 
1. To add a domain in Yammer, add your domain in Office 365 by following the directions in [Add a domain to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611). You must be a global administrator on Office 365 who was synchronized to Yammer as a verified admin to perform these steps.

    For example, say you have an Office 365 subscription that uses the domain contoso.com, and a corresponding Yammer network. If you add a domain contosopharmaceuticals.com to your Office 365 tenant, that domain will be automatically added to Yammer. After this, a new user of that domain, such as ryani@contosopharmaceuticals.com, can log in to Yammer seamlessly with Office 365 credentials.

2. Verify that the domain you added in Office 365 has been added to Yammer.  
  
    a. In Yammer, select the Yammer settings icon ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png) in the left nav, and then click **Network Admin**.
    
    ![Yammer navigation, including Settings icon](../media/d1ec06fa-c2fb-4dcb-b21f-6dff1d20d6ad.png)
  
    b. In the **Network** section choose **Network Migration**.
    
    ![Screenshot of the Network Migration menu item for Yammer Admins](../media/f9ae9328-9cb2-46f7-9bce-26bcdc29b3fa.png)
  
    c. In the **Step 1 of 3 - Check/Add Verified Domains** page, you'll see the list of domains on the Yammer network. 
    
    ![Screen shot of Step 1 of 3 - Check/Add Verified Domains before migrating a Yammer network](../media/cac649d6-9245-4645-8f59-fb27dffd87e8.png)
  
## Remove a domain from Yammer 
<a name="remove"></a>

When you remove a domain from Office 365, the domain is immediately removed from Yammer. This means everyone with email addresses on the domain you remove will no longer be able to access your Yammer network.

For instructions, follow the steps in [Remove a domain from Office 365](https://support.office.com/en-us/article/Remove-a-domain-from-Office-365-f09696b2-8c29-4588-a08b-b333da19810c). 

If instead you want to consolidate multiple domains into one Yammer network, see [Consolidate multiple Yammer networks](https://docs.microsoft.com/en-us/Yammer/configure-your-yammer-network/consolidate-multiple-yammer-networks) and [FAQ: Consolidating multiple Yammer networks](https://docs.microsoft.com/en-us/Yammer/configure-your-yammer-network/faq-consolidate-multiple-yammer-networks).

## Change the domain for a Yammer network
<a name="change"> </a>

When your Yammer domains are managed in Office 365, to change anything about the domain, you must make the change in the Office 365 admin center. You can't just change the Yammer domain. For information about Office 365 domains, see [Domains FAQ](https://support.office.com/en-us/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a
).

### Change the network name displayed in the left navigation in Yammer
1. Change the name in the Office 365 Organization profile. For steps, see [Change your organization's address, technical contact, and more](https://support.office.com/en-us/article/Change-your-organization-s-address-technical-contact-and-more-a36e5a52-4df2-479e-bb97-9e67b8483e10.)
 
    The Yammer network name shown in the left navigation is synced as the name listed in the Organization profile of the Office 365 tenant. This overrides the Network Name set in the Yammer Network admin.  
    ![List of Yammer groups on the Yammer page](../media/0a1125b1-74d2-4ea5-b8e4-6d52456a527e.jpg)
  
### Change the default domain
When the default domain changes in Office 365 to a verified domain, for example, contosoart.com, the primary domain of the corresponding Yammer network is updated. The updated Yammer primary domain, for example, contosoart.com, is used whenever you invite a new user to Yammer.
    
    ![The primary domain shows when you invite users to your Yammer group](../media/5d98c158-3ce4-4404-97e9-1557382216e8.png)
  
If the default domain is the initial domain that ends with .onmicrosoft.com, or the Office 365 tenant is associated with more than one Yammer network, the primary domain of the corresponding Yammer network will not be updated.
  
## If your Yammer network has domains not verified on the Office 365 tenant

If your Yammer network has domains that are not verified on the corresponding Office 365 tenant, you can't manage your domains from Office 365. For example:
  
- Verified domains on the Office 365 tenant: contoso.onmicrosoft.com, contoso.com, northwind.com 
    
- Domains on the corresponding Yammer network: contoso.com, tailspin.com 
    
Note that tailspin.com on the Yammer network is not verified on the Office 365 tenant. If your network is in this situation, you can remedy the situation so that you can manage the domains from Office 365. To do this, you have two options. You can either:
  
1. Add and verify the missing domains to the Office 365 tenant. In the example above, you would add tailspin.com to the Office 365 tenant. 
    
2. Remove the additional domain in Yammer. To remove Yammer domains from your network, contact the Yammer support team. In the example above, you would remove tailspin.com 
    
After you take one of the actions above, the rest of the domains (contoso.onmicrosoft.com, northwind.com) will be added to Yammer, and from this point on, you can manage your domains across their lifecycle in Office 365.
  
> [!TIP]
> To ensure that you don't miss this step, all Yammer verified administrators will receive an email notification if the list of domains on Yammer is out of sync with the list on Office 365. 
  
## If your Office 365 tenant is associated with more than one Yammer network

These additional networks could be free Yammer Basic networks created by employees of your company. For example:
  
- Verified domains on the Office 365 tenant: contoso.onmicrosoft.com, contoso.com, northwind.com 
    
- Domain on Yammer network1: contoso.com 
    
- Domain on Yammer network2: northwind.com 
    
This configuration is no longer supported as of October 16, 2018. For more information, see [Consolidate multiple Yammer networks](https://docs.microsoft.com/en-us/Yammer/configure-your-yammer-network/consolidate-multiple-yammer-networks) and [FAQ: Consolidating multiple Yammer networks](https://docs.microsoft.com/en-us/Yammer/configure-your-yammer-network/faq-consolidate-multiple-yammer-networks). 
  
## If you have more than one Office 365 tenant associated with one Yammer network

This configuration is not supported. For more information, see [About Yammer networks and Office 365 tenants](yammer-and-office-365.md). 

For example:
  
- Verified domains on the Office 365 tenant1: contoso.onmicrosoft.com, contoso.com 
    
- Verified domains on the Office 365 tenant2: northwind.onmicrosoft.com, northwind.com 
    
- Domains on Yammer network: contoso.com, northwind.com 
    
  
## FAQ
<a name="FAQ"></a>

### Q: I'm an existing Office 365 customer with one domain, and I have already added my company domain to my account. Do I have to do any more domain setup for Yammer?

A: No. To get started with administering Yammer, go to the Yammer admin center from Office 365 or from Yammer and continue from there. 
  


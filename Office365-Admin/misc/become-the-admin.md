---
title: "Do an admin takeover in Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'Setup_AdminTakeover'
- 'O365P_DomainsSetup_Merge'
- 'O365E_FreemiumExternalTakeover_1457'
- 'O365E_DomainsSetup_Merge'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
 - Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: "Learn to verify your email and domain ownership to become the admin."
---

# Do an admin takeover in Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 

If you are an admin and want to take over an unmanaged or "shadow" tenant created by users who used self-service sign-up, you can do this with an internal admin takeover.
  
## Step 1: Verify your email address

1. Create a user context in the unmanaged tenant through signing up with such as Power BI. For the convenience of example, these steps assume that path.

2. Open the [Power BI site](https://powerbi.com) and select **Start Free** and on the next page **Try Free**. 

3. Fill out the text box with a user account that uses the domain name for the organization (like `powerbiadmin@contoso.com`)

    3.1 Review your email for the *verification code* (this validates your email address)

    3.2 In case your account is already in use you'll be requested to sign in using your current password

4. Check your email for the confirmation code.

5. [Sign out of Office 365](https://login.microsoftonline.com/logout.srf) from your current account. 

6. Follow the email link that shows your email address and a **Yes, that's me** button. 

    
## Step 2: Create a new account

1. When you follow the **Yes, that's me** link in your email, you'll be brought to a page where you can create a new account. 
    
2. Please fill on the user name and password fields with the account that you want to use when you finish click on **Start**. 
    
## Step 3: Verify domain ownership and become the admin

1. A wizard will open called **"Become the admin"**. If the wizard doesn't start for you, look for the **Admin tile** and click on it. 
    
2. Click **"Yes, I want to be the admin"**
    
3. You'll need to verify that you own the domain you want to take over by adding a TXT record to your domain registrar.
    
1. The wizard will show you the TXT record to add as well as provide a link to your registrar's website and a link to step-by-step instructions.
    
2. Once you've added the TXT record at your registrar site, come back to the wizard and click **Okay, I've added the record** to confirm the record.
    
> [!NOTE]
> If someone in the account signed up to use Office Online at work (instead of one of the other subscriptions, like Power BI), you'd be prompted to and required to buy licenses for them as part of becoming the admin for the domain. But you can add or remove licenses after you finish the admin setup. 
Please note that taking over the shadow tenant will not impact any existing services. The rest of the information and services will remain as is.
  
## Some Terminology:

- **Unmanaged Tenant/shadow tenant**: no administrator account can manage the tenant itself

- **Managed Tenant**:    It's an office tenant that do have an administrator account already


## More:

YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)
  
[Become an admin in Office 365 Education](https://go.microsoft.com/fwlink/?LinkId=512141)
  


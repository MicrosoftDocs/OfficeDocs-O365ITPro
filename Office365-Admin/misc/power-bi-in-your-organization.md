---
title: "Power BI in your organization"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.date: 4/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
description: "Learn about Power BI and how users in your organization can use this business analytics service."
---

# Power BI in your organization

This page describes how users in your organization can use Power BI and how you can control how your organization acquires this service.
  
## In this article

- [What is Power BI?](power-bi-in-your-organization.md#BKMK_WhatIsPowerBI)
    
- [Does Power BI meet national, regional, and industry-specific compliance requirements?](power-bi-in-your-organization.md#BKMK_compliance)
    
- [How do users sign up for Power BI?](power-bi-in-your-organization.md#BKMK_HoiwDoUsersSignUp)
    
- [How do individual users in my organization sign up?](power-bi-in-your-organization.md#BKMK_HowDoIndUsersSignUp)
    
- [How will this change the way I manage identities for users in my organization today?](power-bi-in-your-organization.md#BKMK_HowWillManageIdent)
    
- [What is the process to manage a tenant created by Microsoft for my users?](power-bi-in-your-organization.md#BKMK_WhatIsProcessToManageTenant)
    
- [If I have multiple domains, can I control the Office 365 tenant that users are added to?](power-bi-in-your-organization.md#BKMK_MultDomains)
    
- [How can I prevent users from joining my existing Office 365 tenant?](power-bi-in-your-organization.md#BKMK_PreventJoining)
    
- [How can I allow users to join my existing Office 365 tenant?](power-bi-in-your-organization.md#BKMK_HowCanIAllowO365Tenant)
    
- [How do I verify if I have the block on in the tenant?](power-bi-in-your-organization.md#BKMK_VerifyBlock)
    
- [How can I prevent my existing users from starting to use Power BI?](power-bi-in-your-organization.md#BKMK_PreventExistingUsersStarting)
    
- [How can I allow my existing users to sign up for Power BI?](power-bi-in-your-organization.md#BKMK_HowCanIAllowSignUp)
    
- [How do I remove Power BI for users that already signed up?](power-bi-in-your-organization.md#BKMK_HowDoIRemoveUsers)
    
- [How do I know when new users have joined my tenant?](power-bi-in-your-organization.md#BKMK_HowDoIKnowUsersJoinTen)
    
- [Are there any additional things I should be prepared for?](power-bi-in-your-organization.md#BKMK_AreThereAdditionalPrepareFor)
    
- [Why did 1 million licenses for Microsoft Power BI show up in my Office 365 tenant?](power-bi-in-your-organization.md#BKMK_WhyDid1MillShowUp)
    
- [Is this free? Will I be charged for these licenses?](power-bi-in-your-organization.md#BKMK_IsThisFree)
    
- [Why 1 million licenses?](power-bi-in-your-organization.md#BKMK_Why1Million)
    
- [What if I need more than 1 million licenses?](power-bi-in-your-organization.md#BKMK_WhatIfINeedMore)
    
## What is Power BI?
<a name="BKMK_WhatIsPowerBI"> </a>

Microsoft Power BI enables users to visualize data, share discoveries, and collaborate in intuitive new ways. To learn more, see the [Power BI Web site](https://powerbi.microsoft.com/?WT.mc_id=Old_Site).
  
## Does Power BI meet national, regional, and industry-specific compliance requirements?
<a name="BKMK_compliance"> </a>

To learn more about Power BI compliance, see the [Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## How do users sign up for Power BI?
<a name="BKMK_HoiwDoUsersSignUp"> </a>

As an administrator, you can sign up for Power BI through the [Power BI web site](https://www.microsoft.com/en-us/powerbi/default.aspx). You can also sign up through the purchase services page on the Office 365 admin center. When an administrator signs up for Power BI, they can assign user subscription licenses to users who should have access.
  
Additionally, individual users in your organization may be able to sign up for Power BI through the [Power BI web site](https://www.microsoft.com/en-us/powerbi/default.aspx). When a user in your organization signs up for Power BI, that user is assigned a Power BI license automatically.
  
## How do individual users in my organization sign up?
<a name="BKMK_HowDoIndUsersSignUp"> </a>

There are three scenarios that might apply to users in your organization:
  
### Scenario 1: Your organization already has an existing Office 365 environment and the user signing up for Power BI already has an Office 365 account.

In this scenario, if a user already has a work or school account in the tenant (for example, contoso.com) but does not yet have Power BI, Microsoft will simply activate the plan for that account, and the user will automatically be notified of how to use the Power BI service.
  
### Scenario 2: Your organization has an existing Office 365 environment and the user signing up for Power BI doesn't have an Office 365 account.

In this scenario, the user has an email address in your organization's domain (for example, contoso.com) but does not yet have an Office 365 account. In this case, the user can sign up for Power BI and will automatically be given an account. This lets the user access the Power BI service. For example, if an employee named Nancy uses her work email address (for example, Nancy@contoso.com) to sign up, Microsoft will automatically add Nancy as a user in Contoso's Office 365 environment and activate Power BI for that account.
  
### Scenario 3: Your organization does not have an Office 365 environment connected to your email domain.

There are no administrative actions your organization needs to take to take advantage of Power BI.
  
> [!IMPORTANT]
> If your organization has multiple email domains and you prefer all email address extensions to be in the same tenant, before any users create your primary tenant, add all email address domains to that tenant before any users create your primary tenant. There is no automated mechanism to move users across tenants after they have been created. For more information on this process, see [If I have multiple domains, can I control the Office 365 tenant that users are added to?](power-bi-in-your-organization.md#BKMK_MultDomains) later in this article and [Add your domain to Office 365](https://support.office.com/en-us/article/Add-your-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7) online. 
  
## How will this change the way I manage identities for users in my organization today?
<a name="BKMK_HowWillManageIdent"> </a>

If your organization already has an existing Office 365 environment and all users in your organization have Office 365 accounts, identity management will not change.
  
If your organization already has an existing Office 365 environment but not all users in your organization have Office 365 accounts, we will create a user in the tenant and assign licenses based on the user's work or school email address. This means that the number of users you are managing at any particular time will grow as users in your organization sign up for the service.
  
If you are managing your directory on-premises, and use Active Directory Federation Services (AD FS), Microsoft will not add users to your tenant, and users attempting to join your tenant will receive a message to contact their organization's admin.
  
If your organization does not have an Office 365 environment connected to your email domain, there will be no change in how you manage identity. Users will be added to a new, cloud-only user directory, and you will have the option to elect to take over as the tenant admin and manage them.
  
## What is the process to manage a tenant created by Microsoft for my users?
<a name="BKMK_WhatIsProcessToManageTenant"> </a>

If a tenant was created by Microsoft, you can claim and manage that tenant by following these steps:
  
1. Join the tenant by [signing up for Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) using an email address domain that matches the tenant domain you want to manage. For example, if Microsoft created the contoso.com tenant, you will need to join the tenant with an email address ending with @contoso.com. 
    
2. Claim admin control by verifying domain ownership: once you are in the tenant, you can promote yourself to the admin role by verifying domain ownership. To do so, follow these steps:
    
1. Go to **https://portal.office.com**.
    
2. Select the app launcher icon in the upper-left and choose **Admin**.
    
    ![The Office 365 app launcher with the Admin app highlighted](../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
3. Read the instructions on the **Become the admin** page and then choose **Yes, I want to be the admin**.
    
    > [!NOTE]
    >  If this option doesn't appear, there is already an Office 365 administrator in place. 
  
## If I have multiple domains, can I control the Office 365 tenant that users are added to?
<a name="BKMK_MultDomains"> </a>

If you do nothing, a tenant will be created for each user email domain and subdomain.
  
If you want all users to be in the same tenant regardless of their email address extensions:
  
- Create a target tenant ahead of time or use an existing tenant, and add all the existing domains and subdomains that you want consolidated within that tenant. Then all the users with email addresses ending in those domains and subdomains will automatically join the target tenant when they sign up.
    
> [!IMPORTANT]
> There is no supported automated mechanism to move users across tenants once they have been created. To learn about adding domains to a single Office 365 tenant, see [Add your users and domain to Office 365](https://support.office.com/article/ffdb2216-330d-4d73-832b-3e31bcb5b2a7.aspx). 
  
> [!IMPORTANT]
> For additional information and guidance on managing tenants, see [Power BI Tenant Management Guidance](https://support.office.com/article/d5ec06f3-0ed5-489e-8b8f-4820c80c96ac.aspx). 
  
## How can I prevent users from joining my existing Office 365 tenant?
<a name="BKMK_PreventJoining"> </a>

There are steps you can take as an admin to prevent users from joining your existing Office 365 tenant. If you do block this, users' attempts to sign in will fail and they will be directed to contact their organization's admin. You do not need to repeat this process if you have already disabled automatic license distribution before (e.g. Office 365 Education for Students, Faculty and Staff).
  
These steps require the use of Windows PowerShell. To get started with Windows PowerShell, see the [PowerShell getting started guide](https://go.microsoft.com/fwlink/p/?LinkID=286814).
  
To perform the following steps, you must install the latest 64-bit version of the [Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=236297).
  
After you click the link, click **Run** to run the installer package. 
  
 **Disable automatic tenant join**: Use this Windows PowerShell command to prevent new users from joining a managed tenant:
  
To disable automatic tenant join for new users:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
To enable automatic tenant join for new users:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> This blocking prevents new users in your organization from signing up for Power BI. Users that sign up for Power BI prior to disabling new signups for your organization will still retain their licenses. See the How Can I Remove Licenses? section for instructions on how you can remove access to Power BI for users that had previously signed up for the service. 
  
## How can I allow users to join my existing Office 365 tenant?
<a name="BKMK_HowCanIAllowO365Tenant"> </a>

To allow users to join your tenant, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## How do I verify if I have the block on in the tenant?
<a name="BKMK_VerifyBlock"> </a>

Use the following PowerShell script:  `Get-MsolCompanyInformation | fl allow*`
  
## How can I prevent my existing users from starting to use Power BI?
<a name="BKMK_PreventExistingUsersStarting"> </a>

 **Disable automatic license distribution:** Use this Windows PowerShell script to disable automatic license distributions for existing users. You do not need to repeat this process if you have already disabled automatic license distribution before (e.g. Office 365 Education for Students, Faculty and Staff). 
  
To disable automatic license distribution for existing users:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
To enable automatic license distribution for existing users:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> The AllowAdHocSubscriptions flag is used to control several user capabilities in your organization, including the ability for users to sign up for the Azure Rights Management Service. Changing this flag will affect all of these capabilities. 
  
## How can I allow my existing users to sign up for Power BI?
<a name="BKMK_HowCanIAllowSignUp"> </a>

To allow your existing users to sign up for Power BI, run the opposite command as described in the question above:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## How do I remove Power BI for users that already signed up?
<a name="BKMK_HowDoIRemoveUsers"> </a>

If a user signed up for Power BI but you no longer want them to have access to Power BI, you can remove the Power BI license for that user.
  
1. Navigate to the [Office 365 Admin Center](https://portal.office.com/).
    
2. In the left navigation bar, click **Users** then **Active Users**.
    
3. Find the user you want to remove the license for, then click their name.
    
4. On the user details page, click **Licenses** in the left navigation bar. 
    
5. Uncheck **Microsoft Power BI**.
    
6. Click **Save**.
    
## How do I know when new users have joined my tenant?
<a name="BKMK_HowDoIKnowUsersJoinTen"> </a>

Users who have joined your tenant as part of this program are assigned a unique license that you can filter on within your active user pane in the admin dashboard.
  
To create this new view, in the Office 365 admin center, go to ** Users ** \> **Active Users**, and on the **Select a View** menu, select **New View**. Name your new view, and under **Assigned license**, select **Microsoft Power BI**. Once the new view has been created, you will be able to see all the users in your tenant who have enrolled in this program.
  
## Are there any additional things I should be prepared for?
<a name="BKMK_AreThereAdditionalPrepareFor"> </a>

You might experience an increase in password reset requests. For information about this process, see [Reset a user's password](../add-users-2/reset-passwords.md).
  
You can remove a user from your tenant via the standard process in the Office 365 admin center. However, if the user still has an active email address from your organization, they will be able to rejoin unless you block all users from joining.
  
## Why did 1 million licenses for Microsoft Power BI show up in my Office 365 tenant?
<a name="BKMK_WhyDid1MillShowUp"> </a>

As a qualifying organization, users in your organization are eligible to use the Microsoft Power BI service and these licenses represent the available capacity for new Power BI users in your tenant. There is no charge for these licenses. If you've chosen to allow users to sign up for Power BI themselves, they will be assigned one of these available free licenses when they complete the sign up process. You can also choose to assign these licenses to users yourself through the Office 365 admin center.
  
## Is this free? Will I be charged for these licenses?
<a name="BKMK_IsThisFree"> </a>

These licenses are for the free version of Power BI. If you're interested in additional capabilities, take a look at the Power BI Pro version.
  
## Why 1 million licenses?
<a name="BKMK_Why1Million"> </a>

We chose a number that was large enough that the majority of organizations would have ample licenses to provide this benefit without delay to their users.
  
## What if I need more than 1 million licenses?
<a name="BKMK_WhatIfINeedMore"> </a>

Contact your Microsoft account representative for more information if you will need to acquire additional licenses.
  


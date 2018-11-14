---
title: "Reset Office 365 business passwords"
ms.author: kwekua
author: kwekua
manager: scotv

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_SupportHm_ResetPassword'
- 'O365M_SupportHm_ResetPassword'
- 'O365M_E_Learn_AdminSetup_AdminPasswordRecommendations'
- 'O365E_SupportHm_ResetPassword'
- 'O365E_E_Learn_AdminSetup_AdminPasswordRecommendations'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Top
- Adm_UI_Elements
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Top
- Core_O365Admin_Migration
- MiniMaven
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: "Learn how to reset password for a user in Office 365 business subscription. "
---

# Reset Office 365 business passwords

 *Last updated 26 March, 2018* 
  
## Let users reset their own passwords

We strongly recommend that you set up self-service password reset. This way you don't have to manually reset passwords for your users. To learn how, see [Let users reset their own passwords in Office 365](let-users-reset-passwords.md).
  
## Reset an Office 365 business password for someone else

These steps are only for people using an Office 365 business plan. To do them, you need to sign in with your Office 365 admin account. [What's an Office 365 admin account?](../admin-overview/admin-overview.md)
  
 
::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. Go to [Users \> Active users](https://go.microsoft.com/fwlink/?linkid=866448).
    
3. Select your users.
    
    ![Choose one or more users.](../media/f537b3c8-8bc7-44a6-a548-8969c4ab2d73.png)
  
4. Click **Reset password**. 
    
    ![The Reset password button.](../media/b2c7f0c6-3297-48a6-b77e-e6877222b9db.png)
  
5. Follow text on page.
    
    ![Create a password.](../media/dc90e67d-65ec-49d1-a3af-8bc53b59b4fb.png)

::: moniker range="o365-worldwide"

Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to get help.

Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end
  
## Reset my Office 365 tenant admin password
<a name="bkmk_forgot"> </a>

- Use these steps if you forgot your password but you're able to sign in to Office 365 because, for example, your password is saved in your browser: 
    
1. In Office 365, choose **Settings** \> **Office 365** \> **Personal info**. 
    
    ![An image that shows where to click on Settings.](../media/5d13d864-09dd-45be-b60e-28a977ecc13e.png)
  
2. Double-check that your **Contact details** and **Alternate email** are accurate. If not, change them now. 
    
3. Sign out of Office 365: click on your name in the upper right corner (in the above image, shown as **Diane**) \> **Sign out**. 
    
4. Now sign in again to Office 365: type your user name \> **Next** \> and then choose **Forgot password**. 
    
    ![Choose Forgot my password](../media/06a9e4b6-8fcd-45fe-9f37-b33511bc72fb.png)
  
5. Follow the steps in the wizard to reset your password. It uses your alternate contact info to verify you're the right person to reset your password. 
    
- If you forgot your password and can't sign in to Office 365: 
    
  - Ask another global admin in your business to reset your password for you.
    
  - Or, [call Microsoft Support](https://support.office.com/en-us/article/contact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&amp;rs=en-US&amp;ad=US#ID0EAADAAA=Phone_support_). 
    
## Reset all Office 365 business passwords for everyone in your organization at the same time
<a name="bkmk_forgot"> </a>

These steps work for a business with tens of users. If you have hundreds or thousands of users, see the next section on resetting passwords in bulk.
  
1. In the Office 365 admin center, go to [Users \> Active users](https://go.microsoft.com/fwlink/?linkid=866448).
    
2. Choose the box at top to select everyone in your business. Then unselect yourself. You can't reset your own password at the same time you reset everyone else's password.
    
    ![Choose the box at top to select everyone in your organization.](../media/e82efe16-24d7-4812-aad4-f5bd5c72ea66.png)
  
3. On the right side of page, choose **Reset passwords**. 
    
    ![Choose Reset passwords](../media/dbbf2f03-28a8-4c1b-a64d-6c821dbd3a7e.png)
  
4. Follow text on rest of page.
    
    ![Create a password.](../media/dc90e67d-65ec-49d1-a3af-8bc53b59b4fb.png)
  
## Reset Office 365 business passwords in bulk
<a name="bkmk_forgot"> </a>

Use PowerShell! Check out this post by Eyal Doron: [Managing passwords with PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Here's a related article: [Set the passwords for multiple user accounts](https://support.office.com/article/014fc912-bee1-461d-ad00-56b80428b907.aspx#bkmk_password).
  
For overview information, see [PowerShell for Office 365 administrators](https://support.office.com/article/40fdcbd4-c34f-42ab-8678-8b3751137ef1.aspx).
  
## Force a password change for all users in your business
<a name="bkmk_forgot"> </a>

Check out this great blog post by Vasil Michev, Microsoft MVP: [Force password change for all users in Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## I'm lost!
<a name="bkmk_forgot"> </a>

Try this article: [I forgot the username or password for the account I use with Office.](https://support.office.com/en-us/article/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## More info on resetting passwords
<a name="bkmk_forgot"> </a>

[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md)
  
[Set an individual user's password to never expire](set-password-to-never-expire.md)
  


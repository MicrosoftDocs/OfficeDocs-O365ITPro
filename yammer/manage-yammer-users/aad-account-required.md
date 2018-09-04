---
title: "AAD credentials will be required for Yammer Enterprise log in"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 9/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
description: "Starting January 31, 2019, Yammer Enterprise users can no longer use legacy Yammer credentials. If self-service signup is enabled, users will be automatically prompted to change their password."
---

# AAD credentials will be required for Yammer Enterprise log in 
 
Starting January 31, 2019, Yammer Enterprise users that try to log in using legacy Yammer credentials instead of an Azure Active Directory (AAD) account will be redirected to a new sign up flow and will be asked to create a new password. After completing the required steps, an AAD account with no Office 365 licenses will be automatically created for the user. This process is called self-service signup.  

- After changing their password, these users will be able to access your Yammer network, and will have access to all their groups and data. 
- After the AAD account is created for a user, admins can manage the user from the Office 365 admin center.  

As a Yammer admin, if you want to prevent these users who don’t have Office 365 licenses from accessing your Yammer network, you can choose to enforce Office 365 licenses. For instructions, see [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md).
 
## Why is Yammer doing this? 

There are existing and upcoming features that only work when all users use AAD credentials, including having one place to manage users for all Office 365 apps, and using Office 365 connected groups. 

## Prepare for self-service signup 

Self-service signup is turned on by default everywhere except in the European Union. 

> [!IMPORTANT]
> Admins that have self-service signup disabled must make sure that they enable it before January 31, or any users who try to log in using legacy Yammer credentials will not be able to log in. 

### Step 1: If self-service signup is not enabled, enable it

Self-service signup can only be enabled by using Windows PowerShell. To enable self-service signup:
1. Follow the instructions provided in [Directory self-service signup](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-self-service-signup). 
 
2. In the PowerShell script, set the values for **AllowEmailVerifiedUsers** and **AllowAdHocSubscriptions** to **true**: 

```powershell
Set-MsolCompanySettings -AllowEmailVerifiedUsers $true -AllowAdHocSubscriptions $true
```
 
### Step 2: Make sure users are aware that they will be asked to create a new password.  

Users will be asked to create a new password the first time they try to log in after January 31, 2019. After creating their new password and validating their email address, they will have to use their new credentials to log in. 

Except for having to create a new password, this change will be completely transparent to users. Their data will not be affected in any way. They will continue to see all their groups, external networks, and content, just as they did before the change. 

**Identify affected users and notify them**  

To identify which users you need to notify, follow the instructions in [Audit Yammer users](audit-users-connected-to-office-365.md) to get the contact information for users who currently are not using AAD credentials. 

## FAQ 

**Q: Will this change users' experience?**

A: After January 31, 2019, the user's experience will change:
- If self-service signup is enabled, this impacts the user’s next login in. The first time a user with legacy credentials tries to log in they will be asked to create a new password and validate their email address. After that they will always need to use their newly created AAD credentials when they log in to Yammer.  When they use their new AAD credentials to log in, their Yammer experience will be the same as it was before this change. They will have access to the same groups and external networks as they currently do.

- If self-service signup is not enabled, users using legacy Yammer credentials won’t be able to log in after January 31 until the Office 365 admin manually creates an AAD account for these users and gives each user the new log-in information. 

**Q: What happens if as an admin, I don’t take action by January 31?** 

A: If self-service sign-up is enabled, users will be redirected to the self-service signup flow and they will be able to create their own password, even if no action is taken. However, we recommend letting the users know in advance so they are not surprised by the change. 

If self-service signup is not enabled, users using legacy Yammer credentials won’t be able to log in after January 31 unless you manually create at AAD account for them. 

**Q: Will this impact guest users?** 

A: No, this change will not impact guest users. 
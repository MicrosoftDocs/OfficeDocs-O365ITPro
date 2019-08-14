---
title: "Give access to MileIQ"
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: "Give access to another user to help you manage MileIQ."
---

# Give a user access to MileIQ

## How do I access the MileIQ admin center?

You can access the MileIQ admin center at [www.admin.mileiq.com](https://www.admin.mileiq.com) once you have set an account with a Business Administrator role. The Global IT Admin can assign a new administrator role, Business Administrator, in the Azure Active Directory. Once you've designated a Business Administrator, they can manage the workflows in the MileIQ admin center. More than one Business Administrator can be assigned.

### Assign a user to the Business Administrator role

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) with an account that's a global admin for the directory.
2. Select **Admin centers** and then select **Azure Active Directory**. 

    ![Azure Active Directory](media/mileiq-azure-active-directory.png)

3. On the Azure Active Directory admin center, select **Enterprise applications**.
4. On the **Enterprise applications** blade, select **All applications**. Then select **Apply**.

    ![Enterprise applications all applications](media/mileiq-enterprise-applications-all.png)

5. On the **Enterprise applications - All applications** blade, select **Application Type - All Applications** and search for MileIQ. Select **MileIQ Admin Center**.  

     ![Select MileIQ admin center](media/mileiq-admin-center.png)

6. On the **MileIQ Admin Center** blade, select **Users & Groups**.  
7. On the **MileIQ Admin Center - User & Group Assignment** blade, select the **Add user** command.

     ![Add user](media/mileiq-add-user.png)

8. On the **Add Assignment** blade, select **Users and groups**.  
9. On the **Users and groups** blade, select one or more users or groups from the list and then select the **Select** button at the bottom of the blade. 
10. On the **Add Assignment** blade, MDLAdminCenterRole.Admin is selected and is dimmed. Select the **OK** button at the bottom of the blade. 
11. On the **Add Assignment** blade, select **Assign** button at the bottom of the blade. The assigned user or groups will now be able to enter the [MileIQ admin center](https://www.admin.mileiq.com).  

> [!NOTE]
> Only Global IT Admins have access to the MileIQ admin center by adding themselves in the Business Administrator role. Global IT Admins can manage MileIQ admin access by adding or removing Business Administrators at any time through the Azure Portal.

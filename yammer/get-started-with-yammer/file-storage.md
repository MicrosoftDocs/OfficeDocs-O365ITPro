---
title: "Yammer file storage overview"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
description: "Where files are stored in Yammer depends on whether or not the network is using Microsoft 365 connected groups."
---

# Yammer file storage overview

As of May 2019, Yammer is rolling out changes to file storage for files uploaded to Yammer in Microsoft 365 connected Yammer groups. Formerly, all files uploaded to Yammer were stored in Yammer cloud storage. Once your organization gets these changes, all new files uploaded through Yammer in Microsoft 365 connected Yammer groups will be stored in the group's default SharePoint document library. These files can still be accessed from within Yammer.

For information about using Yammer files stored in SharePoint, see the following topics:

- [Where are my Yammer files stored?](https://support.office.com/article/how-do-i-tell-where-my-yammer-files-are-being-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443)

- [Attach a file to a Yammer message](https://support.office.com/article/attach-a-file-or-image-to-a-yammer-message-f576d4d1-ad66-4ce4-9c43-46cf75978dbf)

- [Edit documents from Yammer](https://support.office.com/article/edit-documents-from-yammer-913dbeab-7efd-4789-8f4d-a666fe315d85)

- [Edit a previously uploaded file when your Yammer connected group now stores files in SharePoint](https://support.office.com/article/edit-a-previously-uploaded-file-when-your-yammer-connected-group-now-stores-files-in-sharepoint-4b2cfde2-871e-4f0d-9936-db5a57ef5f87)

## Benefits

For network and tenant administrators:

- SharePoint has a rich set of security and compliance features that will now apply to files uploaded in Yammer for Office 365 connected Yammer groups, including eDiscovery, data loss protection, and in-geo residence for files at rest.  

For end users:
  
- A familiar user interface for file navigation and management in SharePoint.

- Greater discoverability and easier access via Microsoft search.

    Users with appropriate permissions can find and access the files through Yammer, and can also access the files through SharePoint and other Microsoft 365 and Office 365 resources by using browse or search in SharePoint and Delve.  

- Offline access to files by syncing a SharePoint folders to a folder on their computer.  

## What determines where a file is stored

Files are stored in SharePoint when they are uploaded to a Microsoft 365 connected Yammer group. This includes:  
  
- Files that are attached to a message in a Microsoft 365 connected Yammer group.  

- Files that are uploaded to a group from the **Files** page of an Microsoft 365 connected Yammer group.

- Files that are attached to an email that is sent to a Microsoft 365 connected Yammer group.

 > [!NOTE]
 > Any policies applied on the SharePoint document library take precedent over the Yammer upload admin configuration when a user tries to upload a file in a connected Yammer community.
  
Files will continue to be stored in Yammer cloud storage in the following instances:

- If the Yammer network does not use Microsoft 365 connected groups. This includes:

  - Office 365 tenants that have more than one Yammer network  
  
  - Yammer networks that don't enforce Office 365 identity  

  - Yammer Basic networks  

- When the location the file is being uploaded to is not a Microsoft 365 connected Yammer group:

    - Groups that are not Microsoft 365 connected groups, including All Company, external groups, and secret groups
  
    - Yammer private messages
 
        >[!NOTE]
        > Existing files stored in Yammer legacy storage will not be moved to SharePoint.  

- If your organization is using a third-party app that uses Yammer Files APIs:

  - If we detect that you are currently using the Yammer Files APIs, even if you're using connected groups, files for your tenant will be stored in legacy storage until your app is updated to be an Azure Marketplace app that calls Yammer APIs. We’ll share details on how to create an Azure Marketplace Yammer app soon. If you're a developer and have questions about this change, please email api@yammer-inc.com.

    >[!IMPORTANT]
    > If you create a third-party app that uses Files APIs after your organization has received the Yammer files in SharePoint feature, file calls will fail. Users will see an HTTP 401 error (unauthorized client error) because the Yammer OAuth token does not include claims from Azure Active Directory, which is required for accessing files stored in SharePoint.

 > [!NOTE]
 > Moving a conversation to a Microsoft 365 connected Yammer group will not change where the file is stored.
  
## Where files are stored in SharePoint

Files that users upload in Microsoft 365 connected groups are saved in the **Apps > Yammer** subfolder of the SharePoint document library for the Microsoft 365 connected group. The SharePoint document library can be accessed from Yammer under **Microsoft 365 Resources** or **Office 365 Resources** on the right side of a Microsoft 365 connected Yammer group, as well as through SharePoint itself.

 > [!NOTE]
 > We recommend that you do not delete, move, or rename files in the **Apps > Yammer** subfolder.
  
## Guest and external user access to files

The following table shows how each type of guest and external user can access files uploaded in Yammer and stored in SharePoint.

|**Type of user**|**Access to group files in Yammer**|**Access to group files in SharePoint**|
|----------|----------|----------|
|**Conversation-level guest that is in your network**|**Private group**: Can view files that have been shared in the conversation, but can't upload files.<br/>**Public group**: Can view, edit, and upload files.|Conversation level guests cannot access any files saved in SharePoint nor upload any files. If you want to enable access to specific files in the conversation, add them as an Azure B2B guest on the Office 365 tenant. File upload is not permitted.|
|**Network-level guest that is also an Azure B2B guest, and also a member of the group in Microsoft 365**|Can view, edit, and upload files.|These Azure B2B guests can view, upload, or edit files from the SharePoint Document library only. File access from Yammer is not permitted.|
|**Azure B2B guest, but not a member of the group<br/>Network-level guest<br/>Conversation-level guest that is not in your network**|Automatic file access is not allowed. These users can request access to specific files.<br/>Can't upload files.|Automatic file access is not permitted. Guest users can request access to specific files. File upload is not permitted.|   
|**Network-level guest, but not Azure B2B guest**|Automatic file access is not allowed. A guest user must become an Azure B2B guest and a member of the group in Microsoft 365. Alternatively, other group members can grant access to specific files or the entire document library through one of many SharePoint external sharing methods.|No automatic access for network level guests to Yammer files saved in SharePoint. If you want to enable access to specific files, add them as an Azure B2B guest on the Office 365 tenant. For more information, see [Azure Active Directory B2B documentation](https://docs.microsoft.com/azure/active-directory/b2b/). If guest users need to upload files to a specific group from SharePoint or have automatic access to files uploaded to SharePoint, add them as a group member in SharePoint.|

> [!NOTE]
> Membership in the group for guests in Azure Active Directory (AAD) and Yammer are completely separate. Deleting a network-level guest from an Microsoft 365 connected Yammer group or from the tenant in AAD does not remove the user in Yammer, and deleting a user from Yammer does not delete the user from an Microsoft 365 group or AAD.

For more information about Azure B2B guests, see [Guest user access in an Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

## Requirements

- Yammer version requirements

    Ensure your users are using the most recent Yammer versions. At a minimum, users should be using the following or newer versions:

    - Yammer on iOS - 7.33.0  

    - Yammer on Android - 5.5.84

    - Yammer desktop on Windows or Mac - 3.4.2

- Cookie and browser requirements

    To store Yammer files in SharePoint, we use the ADAL library and use Azure Directory (AAD) tokens for authentication. If browsers don’t have third-party cookies enabled or if the security zone settings are incorrect in Internet Explorer 11 or Edge, the ADAL library used to refresh AAD tokens can't send information needed to AAD.

    > [!NOTE]
    > Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting November 30, 2020.) [Learn more](https://aka.ms/AA97tsw) Please note that Internet Explorer 11 will remain a supported browser. Internet Explorer 11 is a component of the Windows operating system and [follows the lifecycle policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is installed.

    When a token refresh call fails, users will see:

    - On the Yammer page for a connected group, Microsoft 365 Office 365 Resources will be grayed out

    - File operations will fail

    - Yammer live events can't be created

     For more information, see [A silent sign-in request was sent but no user is signed in](https://github.com/AzureAD/azure-activedirectory-library-for-js/wiki/FAQs#q6-aadsts50058-a-silent-sign-in-request-was-sent-but-no-user-is-signed-in).

    To avoid problems:

    - Ensure there aren’t any extensions that block or prevent reading of cookies, such as Ghostery.

    - In Internet Explorer 11 or Edge, ensure protected mode is disabled for the trusted zone.

        Yammer.com and related URLs should be a part of trusted zone. For more information, see [Office 365 URLs and IP address ranges](https://support.office.com/en-gb/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_yammer)

    - In complex environments, especially those using wildcard configurations such as *.fabrikam.com, additional effort may be required to find the right configuration. URLs may need to be moved between zones, or replaced with the absolute versions in some cases.

    - Users shouldn’t access Yammer by using incognito or InPrivate mode or equivalent modes in other browsers.

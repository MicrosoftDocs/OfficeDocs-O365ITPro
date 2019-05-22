---
title: "Yammer file storage overview"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 5/22/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
description: "Where files are stored in Yammer depends on whether or not the network is using Office 365 connected groups."
---

as of May 2019, Yammer is rolling out changes to file storage for Yammer files in Office 365 connected groups. Formerly, all Yammer files were stored in Yammer cloud storage. Once your organization gets these changes, all new Yammer files for connected groups will be stored in SharePoint, but can still accessed from within Yammer.

For information about using Yammer files stored in SharePoint, see the following topics: 

- [Where are my Yammer files stored?](https://support.office.com/article/how-do-i-tell-where-my-yammer-files-are-being-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443)

- [Attach a file to a Yammer message](https://support.office.com/article/attach-a-file-or-image-to-a-yammer-message-f576d4d1-ad66-4ce4-9c43-46cf75978dbf)

- [Edit documents from Yammer](https://support.office.com/article/edit-documents-from-yammer-913dbeab-7efd-4789-8f4d-a666fe315d85)

- [Edit a previously uploaded file when your Yammer connected group now stores files in SharePoint](https://support.office.com/article/edit-a-previously-uploaded-file-when-your-yammer-connected-group-now-stores-files-in-sharepoint-4b2cfde2-871e-4f0d-9936-db5a57ef5f87)

# Benefits

For network and tenant administrators:

- SharePoint has security and compliance features that are not available for files stored in Yammer, including eDiscovery, data loss protection, and in-geo residence for files at rest.  

For end users: 
  
- A familiar user interface for file navigation, management, and version control. 
  
- Greater organizational capabilities. 

    Files are saved in a SharePoint App Root special folder and are linked to via docID, so users can organize files in folders and rename files without breaking links to the files. 
 
- Greater discoverability and easier access to files saved in Yammer. 

    Users with appropriate permissions can find and access the files through Yammer, and can also access the files through SharePoint and other Office 365 resources by using browse or search in SharePoint and Delve.  
     
- More powerful collaboration and versioning capabilities using SharePoint versioning.  

# What determines where a file is stored    
 
Files are stored in SharePoint when they are uploaded to a Yammer Office 365 connected group:  
  
- Files that are attached to a message in an Office 365 connected group.  

- Files that are uploaded to a group from the **Files** page of an Office 365 connected group. 
 
- Files that are attached to an email that is sent to the Office 365 connected group.   
  
Files are stored in Yammer cloud storage in the following instances:   
 
- If the Yammer network does not use Office 365 connected groups. This includes:
 
  - Office 365 tenants that have more than one Yammer network  
  
  - Yammer  networks that don't enforce Office 365 identity  

  - Yammer Basic networks  
 
- In an Office 365 connected network, if the specific group is not a connected group for one of the following reasons:   
 
   - The group is either All Company, an external group or a secret group. These types of groups are not eligible to be Office 365 connected groups.  
  
   - The group either has no group admin, or has no group admin with Office 365 group creation rights.  
  
    - Files are uploaded in Yammer private messages.  
  
   - Files that were uploaded to an Office 365 connected Yammer group before this feature was enabled. Files that are currently stored in Yammer legacy storage will not be moved to SharePoint.   
  
 # Where files are stored in SharePoint
 
Files that users upload in Office 365 connected groups are saved in the **Apps/Yammer** subfolder of the SharePoint document library for the Office 365 connected group. The SharePoint document library can be accessed under **Office 365 Resources** on the right side of an Office 365 connected group, as well as through SharePoint itself.   
  
# Renaming and moving files stored in SharePoint  
  
Yammer uses SharePoint Document IDs and the 'AppRoot' special folder for the storage of files. This means that users can move and rename files and folders without breaking links to previously uploaded files or blocking upload of new files.

While you can't choose the destination folder at upload time, you can move it afterwards. For example, move the **Yammer** subfolder out of the **Apps folder** (and even rename it, if you want to), and all future uploads to the group will be saved in the new location. Similarly, links to files previously uploaded to SharePoint will continue to work even if the file is renamed or moved to a different location within the document library for the Office 365 connected group.  
  
# Guests and external users
  
In order to upload files to SharePoint, a person needs to be a user in your Office 365 tenant. This means that guest users can't upload files in the connected group unless they have also been added to your tenant as an Azure B2B guest from the AAD admin center for the connected group. Guests can continue to be able to attach links to other cloud files if they are not an Azure B2b guest.  

Users who don't have access to the group's SharePoint document library will need to use a link to a cloud-stored file. Alternatively they can ask another member of the group to share the file with them. Another option would be for you to add the Yammer guest onto your tenant via Azure B2B, and then add them as an external guest in the AAD admin center.

External users and guests in your Yammer network are not currently synchronized with or managed in Azure Active Directory (AAD) and will not have default access to view or upload files in Office 365-connected groups. See the next section for changes you can make to give these users access to files, based on typical SharePoint security settings. 

### Giving Network Level Guests access to files in SharePoint

If the network-level guest is added as an Azure B2B guest on the tenant, the network-level guest will be able to request access to SharePoint files to which they don't have access. 
 
If the network-level guest is also added as a member of the Office 365 group through either the AAD or Microsoft 365 admin centers, the network-level guest will be able to upload files to the group and have default access to other files uploaded to the group. This should be done for both public and private groups, if default access is desired.  

It is important to remember that the membership in the group for guests in AAD and Yammer are completely decoupled. Deleting the network-level guest from a group (or from the tenant) in AAD, does not remove the user from Yammer, nor vice versa.
  
External users in External Groups are not impacted by this feature because external groups are not Office-365 connected. 

External participants added to threads from connected groups can be added as an Azure B2B guest on the tenant level so that the participant will be able to request access to the files shared in those threads.  

# FAQ

**Q: Are there features which are supported for files in legacy Yammer storage that aren't supported for files stored in SharePoint?**  

A: There are some little-used features in Yammer that aren't supported for files that are saved in SharePoint.   

- Because collaboration is managed through SharePoint, it won't be possible to mark files as official within Yammer.  

    Users will need to use permissions in SharePoint to restrict changes to a file. 
   
- For Office 365 connected groups, users can't create a new document file or new version of an existing file within Yammer legacy storage. 

    Because versioning is managed through SharePoint, users will need to go to SharePoint to see previous versions of a file that has been saved to SharePoint. Instead of editing or uploading a file within Yammer to create a new version of a file, users will need to upload the latest version of the file to the group so it is saved in SharePoint, and then the versioning capabilities of SharePoint can be used going forward.  

**Q: What happens when I remove external participants from a thread in a connected group?**  

A: When you remove participants in a thread, the user will no longer have access to the thread. If there has been a file shared in that thread, the user may still have permissions to the file in SharePoint. This means that unless another user explicitly goes to SharePoint and removes permissions to the file for that user, the user may still have access. 
     
     
     
     
     
     
     
     
     
     
     

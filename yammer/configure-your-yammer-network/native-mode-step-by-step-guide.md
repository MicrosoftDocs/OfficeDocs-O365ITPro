---
title: "Yammer Native Mode: step-by-step guide"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 09/09/2020
audience: Admin
ms.topic: article
ms.service: yammer
ms.subservice:
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn more about the process of migrating to Native Mode with this in-depth step-by-step guide."
---
# Yammer Native Mode: step-by-step guide

Networks that want to take advantage of the new compliance features available in Yammer will need to make sure their network is aligned to Native Mode. Native Mode also provides additional benefits, such as the ability to host Live Events in every Yammer community, simplify file administration through SharePoint, and also apply Microsoft 365 Group management policies.

Any network that was created after January 16, 2020 is already in Native Mode and can make use of these features right out of the box! Networks created prior to this date will need to use the Native Mode Alignment Tool to ensure their network is fully backed by Microsoft 365 prior to accessing these new features.

The following steps show you what actions to take before and during a transition to Native Mode. For more information on what Native Mode means for your Yammer Network, see [Overview of Native Mode](../configure-your-yammer-network/native-mode.md).

## 1. Initial Steps to access the Native Mode Alignment Tool

Once you are ready to align your network to Native Mode, you’ll need to make sure that your Microsoft tenant has just one Yammer Network associated with it.  If you have more than one Yammer Network on your Microsoft tenant, you’ll first need to complete the steps listed in [Consolidate multiple Yammer networks](../configure-your-yammer-network/consolidate-multiple-yammer-networks.md).

After you have ensured that there is just one Yammer Network in your Microsoft tenant, you will need to ensure that that network enforces Microsoft 365 Identity. Additional information on enforcing Identity can be found in [Enforce Microsoft 365 Identity](./enforce-office-365-identity.md).

## 2. Accessing the Native Mode Alignment Tool

The Native Mode Alignment Tool can only be accessed by tenant-level Global Admins. It’s important to know that during times of high network traffic it can take up to a few hours for Global Admin privileges to be reflected in Yammer. If your account is only granted these privileges on a temporary basis, it may not be visible immediately after your account is elevated. Once Yammer recognizes that your account has Global Admin capabilities, you can access the Native Mode Alignment Tool by logging in to Yammer, navigating to the Network Admin section, and then accessing the menu item for Native Mode for Microsoft 365.

> [!IMPORTANT] 
> The alignment tool can take a long time to process. Most customers are able to complete the tool in one to two weeks, but it can take up to 90 days in some extreme circumstances. The account used to initiate the alignment tool must maintain global admin privileges for the duration of the alignment process.

## 3. Preparing to run the Native Mode Alignment Tool
Prior to running the Native Mode Alignment Tool, you should generate and review the Alignment Report. This report can be generated for your network directly from within the tool by clicking the **Generate Report** button in the middle of the screen. Clicking on the **Generate Report** button will not make any changes in your network and will not begin the alignment process. This will begin the process of generating a report, which will output a list of all Users and Communities in your Yammer Network.

This report will initially be in a .yml format. If you would prefer to review the file as a .csv, we provide a tool available via GitHub, which will convert this file to a .csv enabling you to open the file in a variety of other formats for further analysis.

This report should be reviewed to identify the following:

- **Which users are currently unmapped?**
When run, the Alignment Tool will attempt to map all unmapped users to an existing Azure AD account, but any users who do not have an Azure AD account which the tool can map to will be deleted from the network.

- **How many files does each user have stored in Private Messages?**

  When run, the Alignment Tool will hard-delete all files that are attached to private messages. These files will be unrecoverable after the alignment completes.

- **Which communities in your network are Private and Unlisted?**

   Unlisted communities will become standard private communities when the alignment available through the Azure B2B Guest framework. The Native Mode Alignment Tool will convert all your external groups to internal groups. If you have enabled Azure B2B Guests in your Yammer network, you will be able to reinvite your guests as Azure B2B guests as part of the migration.

- **Which communities in your network allow external guests?**

  External groups are not permitted in Native Mode. Guest access in Native Mode is only available through the Azure B2B Guest framework. The Native Mode Alignment Tool will convert all your external groups to internal groups. If you have enabled Azure B2B Guests in your Yammer network, you will be able to reinvite your guests as Azure B2B guests as part of the migration.

- **Which communities in your network do not have any owners or have owners without Microsoft 365 Group Creation Rights?**

  The Native Mode Alignment Tool will create a new Microsoft 365 Group, which is authorized using the credentials of the existing owners of the Yammer community. If the Yammer community does not have any owners, or if none of those owners are authorized to create Microsoft 365 Groups, the tool will create the group using the credentials of the Global Admin who has initiated the Alignment Tool. For this reason, it is important that your Global Admin maintains their privileges for the duration of the Alignment process.

  We recommend sending out advanced communications to all users who have files stored in private messages, owners of any groups that are marked as unlisted, and owners of any groups that are currently external.

## 4. Exporting the content in your Yammer Network

  Immediately before running the Alignment Tool, you should export any content from your Yammer Network that is not already backed up. The best practice is to export this content on a regular basis. We encourage you to set up automated backups every month or so. Once these regular backups are in place, it will be much easier to export any additional data as needed for processes like this one. 

  If you do not take regular backups of your data, you will need to export all the data in your home network  which you want to have a copy of. External networks can be ignored, as they are not impacted by the Native Mode Alignment Tool. You have the option to export data going as far back as the beginning of your network, but you may decide you only need to backup data going back a certain amount of time. Please keep in mind that the Native Mode Alignment tool will delete certain data such as the files attached to private messages and any messages posted in previously deleted groups from your network, so any data which is not backed up may be entirely non-recoverable after the tool has run.

  Exporting a large volume of content from your network is a multi-step process:

  1.	**Export message data** 
          - We suggest exporting the message data using the [Network Data Export feature](../manage-security-and-compliance/export-yammer-enterprise-data.md#ExportNetworkData) within the Yammer Admin panel.
          - We suggest limiting your export to a maximum date range of 2 months at a time and excluding attachments. If you choose to include attachments, you may need to limit your date range significantly further (often just one week at a time) to prevent the system from encountering timeout errors.

  2. **Export files**
        - We suggest exporting files separately from messages using the [Yammer file export API](../manage-security-and-compliance/export-yammer-enterprise-data.md#export-yammer-files-via-api).
        - Using this API you can export all the files from a specified date range. This API supports concurrent requests (up to 6) and each request should be limited to a two-month date range. This will allow you to simultaneously export a full year of files in one API call.

## 5. Running the Alignment Tool for the first time

Once you’ve reviewed the Alignment Report, communicated upcoming changes to the users in your network, exported all of your data, and are confident in what changes the tool will make in your network, you should now be ready to run the tool for the first time. The tool will run in the background of your network and will have no noticeable impact to end users. As soon as the tool starts running, it will be making some changes to your network to prevent new unmapped users, unconnected groups, etc.

It is important to note that in most cases, the tool will need to be run more than once. To run the tool, scroll to the very bottom of the page and click the **Continue** button. You will then be presented with an authorization form asking you to confirm that you have read and understand the documentation and reports, which will have informed you about the changes the tool will make to your network. Please read through the form and this guide carefully and ensure you fully understand the implications of running this tool.

> [!IMPORTANT]
> Running the Native Mode Alignment tool will make permanent and irreversible changes in your network. Data deleted through this process cannot be recovered through any available process.

When you are ready, complete the authorization form and initiate the Alignment Tool. You will need to keep the window open for one-five minutes while the initial phase of the tool processes, after which you will be able to navigate away from the page without consequence. If you try to navigate away from the page during the initial setup phase, you will receive a warning that prevents you from accidentally navigating away too early.

## 6.	Tracking Alignment Tool Progress

The Alignment Tool will run in the background of your system and should not cause any noticeable impact for end users. The account used to run the alignment tool must maintain global admin status for the duration of the alignment process. Many smaller networks may be able to fully process in one to two weeks, however for larger networks this process can take up to 90 days the first time. If your network needs to run the tool multiple times, each run will take significantly less time than the last as it will only need to process content that failed to process in the previous runs.

To check on the progress of the alignment tool, just navigate back to the page where you started the tool. At the top of the page you will see a banner that will tell you the current status of the tool as well as the next steps you need to take (if the tool is ready for you to take next steps).

You can also see a more detailed status update towards the bottom of the screen, which updates every 30 minutes to tell you the number of users, groups, files, etc. that have successfully been migrated.

## 7. Resolving the error report

Once the tool has finished running, the banner at the top of the page will say one of two things. If the banner says that your network is successfully aligned to Native Mode, you are now finished and can be confident that you have no further actions required. If the banner says that the alignment has failed and an error report was generated, then it’s time to download that error report. The vast majority of errors are very easy to resolve, and usually just require you to rename a file that has characters not allowed in SharePoint files.

> [!NOTE]
> The error report can be found at the very bottom of the page. This is a separate report from the Alignment Report that you reviewed earlier. 

The error report will be in .csv format by default and will remain available until the next time the Alignment Tool is run. When the tool is run again, a new error report will be generated.
The error report will contain a list of files that failed to migrate from Azure to SharePoint, as well as error codes. For a list of common error codes and the necessary steps to remediate these codes, see the [Error Codes section of the Troubleshoot native mode article](../troubleshoot-problems/troubleshoot-native-mode.md#error-codes). You also have the option of working with our Premier Support Team, who can help with resolving these error reports. If you have a high volume of errors, the support team can provide scripts that will allow you to bulk update the files in your network to allow for faster remediation.

It is possible that your error report may contain errors that are not found in the documentation above or which do not appear to be actionable. Often these errors are generated as duplicates of other errors, which are actionable. We suggest working through all the errors that you can, and then re-running the Alignment Tool. Often, we find that most of these errors will resolve themselves when the tool is rerun after resolving the actionable errors.

> [!IMPORTANT]
> Once a network is successfully aligned to Native Mode, the system will automatically prevent any action that would break this alignment. You will not need to go through this process again once it has run successfully. 







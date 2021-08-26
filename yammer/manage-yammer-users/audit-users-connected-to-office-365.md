---
title: "Audit Yammer users in networks connected to Office 365"
f1.keywords:
- NOCSH
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 99f6f0e1-5a8d-4546-979d-564a5a453a8c
description: "Audit Yammer users: export a list of users, find the status of those users in Office 365, and analyze the results and take action."
---

# Audit Yammer users in networks connected to Office 365

Your company's Yammer network might have users who no longer work for your company. Or, some Yammer users might be logging in with their email and password because they don't have a corresponding Office 365 account. In order to analyze such situations and take action, you can audit your Yammer users. This involves exporting the list of Yammer users, finding the status of these Yammer users in Office 365 by using Azure Active Directory Module for Windows PowerShell, and analyzing the results and taking action.
  
In addition to auditing Yammer users, you may want to understand more about how the Yammer service can be seamlessly managed from Office 365. For example, you can [Manage Yammer users across their life cycle from Office 365](manage-users-across-their-lifecycle.md) and [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md).
  
## Export the Yammer users list

Before you can run the audit script, you create an input file that contains the list of user accounts for the script to use. You create the input file by using the **Export Users** function in Yammer. 
  
1. In Yammer, click the Yammer settings icon ![Yammer settings icon.](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then click **Network Admin**.
    
2. Click **Export Users**.
    
    ![Yammer Export Users menu.](../media/69748f25-6619-4d2f-b9c8-17f02b726a98.png)
  
3. On the Export Users page, choose **Export all users**, and then click **Export**.
    
    ![Yammer Export Users options - Export all users or Export all users since (date).](../media/71c292af-9ca0-447a-8750-20b49bd1330e.png)
  
4. Save the exported file. The file is saved as a compressed file with a .zip file name extension.
    
5. Go to the location where you saved the compressed file and expand it.
    
    > [!NOTE]
    > There are several files that are contained within the compressed file. You only need the file that is named users.csv. 
  
## Find status of Yammer users in Office 365

1. Install and configure the Azure Active Directory Module for Windows PowerShell. For instructions on this, read the following document: [Azure AD Help](/previous-versions/azure/jj151815(v=azure.100)).
    
2. Copy the following sample code, paste it into a text editor like Notepad, and then save the file as UserMatchToAzureAD.ps1.
    
    Feel free to modify it to suit your organization's needs.
    
```powershell

<#Copyright 2016  Microsoft Licensed under the Apache License, Version 2.0 (the "License");  you may not use this file except in compliance with the License.  You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0  Unless required by applicable law or agreed to in writing, software  distributed under the License is distributed on an "AS IS" BASIS,  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the License for the specific language governing permissions  and limitations under the License.  Yammer auditing tool for Office 365 looks for active Yammer accounts  that  are missing from Office 365 / Azure AD.  Takes User.csv file from Yammer Data Export as the input file.   Compares all Active Yammer accounts in the input file to user   lookup in Azure AD. User is searched by both email and proxyAddresses.   The output csv file is exactly matching the source file, but it includes  three new columns: exists_in_azure_ad, object_id and azure_licenses:  exists_in_azure_ad: Will be TRUE or FALSE, and signals that the user can be, or cannot be found in Office 365 / Azure AD  object_id: For users that can be found, lists the ObjectId in Azure AD  azure_licenses: For users that can be found, lists the plans assigned to the user in Azure AD. 

This information can be used to double check licenses are assigned correctly for each user.  

Params -  UseExistingConnection: Defines if the script should try to use an existing Azure AD connection. Will prompt for credentials and will start a new connection if $FALSE. Default is $FALSE  InputFile: Source CSV file of users, coming from the Yammer User Export tool  OutputFile: Output location to save the final CSV to  Example -  UserMatchToAzureAD.ps1 -InputFile .\Users.csv -OutputFile .\Results.csv  #> 
  
Param(
     [bool]$UseExistingConnection = $FALSE,
     [string]$InputFile = ".\Users.csv",
     [string]$Outputfile = ".\Results.csv"
    ) 
  if(!$UseExistingConnection){
       Write-Host "Creating a new connection. Login with your Office 365 Global Admin Credentials..."
       $msolcred = get-credential
       connect-msolservice -credential $msolcred
   }
   Write-Host "Loading all Office 365 users from Azure AD. This can take a while depending on the number of users..."
   $o365usershash = @{}
   get-msoluser -All | Select userprincipalname,proxyaddresses,objectid,@{Name="licenses";Expression={$_.Licenses.AccountplanId}} | ForEach-Object {
       $o365usershash.Add($_.userprincipalname.ToUpperInvariant(), $_)
       $_.proxyaddresses | ForEach-Object {
           $email = ($_.ToUpperInvariant() -Replace "SMTP:(\\*)*", "").Trim()
           if(!$o365usershash.Contains($email))
           {
               $o365usershash.Add($email, $_)
           }
       }
   }
   Write-Host "Matching Yammer users to Office 365 users"
   $yammerusers = Import-Csv -Path $InputFile | Where-Object {$_.state -eq "active"}
   $yammerusers | ForEach-Object {
       $o365user = $o365usershash[$_.email.ToUpperInvariant()]
       $exists_in_azure_ad = ($o365user -ne $Null)
       $objectid = if($exists_in_azure_ad) { $o365user.objectid } else { "" }
       $licenses = if($exists_in_azure_ad) { $o365user.licenses } else { "" }
       $_ | Add-Member -MemberType NoteProperty -Name "exists_in_azure_ad" -Value $exists_in_azure_ad
       $_ | Add-Member -MemberType NoteProperty -Name "azure_object_id" -Value $objectid
       $_ | Add-Member -MemberType NoteProperty -Name "azure_licenses" -Value $licenses
   } 
  Write-Host "Writting the output csv file..."
  $yammerusers | Export-Csv $Outputfile -NoTypeInformation 
  Write-Host "Done." 
  
```
   
3. From a Azure Active Directory Module for Windows PowerShell command window, run the command as in the example below, passing the input file exported from Yammer and an output file location.
    
    Example usage:
    
  ```
  UserMatchToAzureAD.ps1 -InputFile .\Users.csv -OutputFile .\Results.csv
  
  ```

    For more information on how to run the script, look at the PS1 file above.
    
## Analyze the results and take action

1. Open the result CSV file, and filter out all the rows that show the exists_in_azure_ad column as FALSE.
    
    Each of them are accounts that exist in Yammer, but not in Office 365 / Azure AD. For each of them, decide if you need to:
    
      - Suspend the user account in Yammer if the user shouldn't have access.
    
      - Create the user in Office 365 / Azure AD.
    
2. After you have completed these operations, we recommend that you run these steps again from the start to confirm all the users are now found in Office 365 and Azure AD.
    
If you are enforcing Office 365 identity, then after a full audit you may want to consider logging off all current users, so that you can be sure that everyone is now logging in with their Office 365 credentials, and not using cached credentials. If you choose to do this, ensure that this is communicated to your users. More information in [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md).

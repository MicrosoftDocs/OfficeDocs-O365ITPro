---
title: "Prerequisites for making Planner changes in Windows PowerShell"
f1.keywords:
- NOCSH
ms.author: nisteidl
author: nisteidl
manager: arshishk
ms.date: 01/05/2021
audience: Admin
ms.topic: Overview
layout: LandingPage
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
description: "This procedure walks you through downloading the files needed to run Planner admin commands in PowerShell"
---

# Prerequisites for making Planner changes in Windows PowerShell

This procedure walks you through downloading the files needed to run Planner admin commands in PowerShell:

- Two Active Directory DLLs
- One PowerShell script
- The script's manifest

If you're new to Windows PowerShell, see [Getting started with Windows PowerShell](/powershell/scripting/learn/ps101/01-getting-started).

1. Navigate to https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/3.19.8.

2. On the right, select **Manual download**, choose **Save as**, choose a location to save it to, and choose **Save**.

3. Find the file in File Explorer and change its file extension from .nupkg to .zip.

4. Right-click the file and select Properties. On the General tab, select the Unblock check box if you see one, and then select **OK**. 

5. Right-click the .zip file and choose **Extract All**. Choose **Extract**. You'll end up with an unzipped folder entitled "microsoft.identitymodel.clients.activedirectory.3.19.8".

6. Copy the following code into a text editor and save it as SetPlannerTenantSettings.psm1 in the "microsoft.identitymodel.clients.activedirectory.3.19.8\lib\net45" folder.

    ```powershell
    function Connect-AAD () 
    {
    <#
    .Synopsis
    (Private to module) Attempts to obtain a token from AAD.
    .Description
    This function attempts to obtain a token from Azure Active Directory.
    .example
    $authorizationContext = Connect-AAD
    #>
    
        $authUrl = "https://login.microsoftonline.com/common" # Prod environment
        $resource = "https://tasks.office.com" # Prod environment
        $clientId = "d3590ed6-52b3-4102-aeff-aad2292ab01c"
        
        $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Always"
        
        $authentiationContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authUrl, $False
        
        $authenticationResult = $authentiationContext.AcquireTokenAsync($resource, $clientId, $redirectUri, $platformParameters).Result
        return $authenticationResult
    }
    
    function Set-PlannerConfiguration
    {
    <#
    .Synopsis
    Configures tenant level settings for Microsoft Planner.
    .Description
    This cmdlet allows tenant administrators to change policies regarding availability of certain features in Microsoft Planner. The changes to settings take effect immediately. This cmdlet specifies the administrator preference on whether the feature should be available. The features can still be disabled due to Microsoft Planner behavior, at the discretion of Microsoft.
    .Parameter Uri
    The URL of the Tenant-Level Settings API for the Planner instance to control.
    .Parameter AccessToken
    A valid access token of a user with tenant-level administrator privileges.
    .Parameter AllowCalendarSharing
    If set to $false, disables creating iCalendar links from Microsoft Planner, and disables previously created iCalendar links.  If set to $true, enables creating iCalendar links from Microsoft Planner and re-enables any previously created iCalendar links.
    .Parameter AllowTenantMoveWithDataLoss
    If set to $true, allows the tenant to be moved to another Planner environment or region. This move will result in the tenant's existing Planner data being lost.
    .Parameter AllowRosterCreation
    If set to $true, allows the users of the tenant to create rosters as the container for a plan to facilitate ad-hoc collaboration. This setting does not restrict the use of existing roster contained plans.
    .Parameter AllowPlannerMobilePushNotifications
    If set to $true, allows the use of direct push mobile notifications in Tenant
    .example
    
    Set-PlannerConfiguration -AllowCalendarSharing $true
    
    .example
    
    Set-PlannerConfiguration -AllowTenantMoveWithDataLoss $true
    
    .example
    
    Set-PlannerConfiguration -AllowRosterCreation $false
    
    .example
    
    Set-PlannerConfiguration -AllowPlannerMobilePushNotifications $false
    #>
        param(
            [ValidateNotNull()]
            [System.String]$Uri="https://tasks.office.com/taskAPI/tenantAdminSettings/Settings",
    
            [ValidateNotNullOrEmpty()]
            [Parameter(Mandatory=$false)][System.String]$AccessToken,
            [Parameter(Mandatory=$false, ValueFromPipeline=$true)][System.Boolean]$AllowCalendarSharing,
            [Parameter(Mandatory=$false, ValueFromPipeline=$true)][System.Boolean]$AllowTenantMoveWithDataLoss,
            [Parameter(Mandatory=$false, ValueFromPipeline=$true)][System.Boolean]$AllowRosterCreation,
            [Parameter(Mandatory=$false, ValueFromPipeline=$true)][System.Boolean]$AllowPlannerMobilePushNotifications
            )
        
        if(!($PSBoundParameters.ContainsKey("AccessToken"))){
            $authorizationContext = Connect-AAD
            $AccessToken = $authorizationContext.AccessTokenType.ToString() + ' ' +$authorizationContext.AccessToken
        }
        
        $flags = @{}
        
        if($PSBoundParameters.ContainsKey("AllowCalendarSharing")){
            $flags.Add("allowCalendarSharing", $AllowCalendarSharing);
        }
    
        if($PSBoundParameters.ContainsKey("AllowTenantMoveWithDataLoss")){
            $flags.Add("allowTenantMoveWithDataLoss", $AllowTenantMoveWithDataLoss);
        }
    
        if($PSBoundParameters.ContainsKey("AllowRosterCreation")){
            $flags.Add("allowRosterCreation", $AllowRosterCreation);
        }
    
        if($PSBoundParameters.ContainsKey("AllowPlannerMobilePushNotifications")){
            $flags.Add("allowPlannerMobilePushNotifications", $AllowPlannerMobilePushNotifications)
        }
    
        $propertyCount = $flags | Select-Object -ExpandProperty Count
        
        if($propertyCount -eq 0) {
            Throw "No properties were set."
        }
        
        $requestBody = $flags | ConvertTo-Json
    
        Invoke-RestMethod -ContentType "application/json;odata.metadata=full" -Headers @{"Accept"="application/json"; "Authorization"=$AccessToken; "Accept-Charset"="UTF-8"; "OData-Version"="4.0;NetFx"; "OData-MaxVersion"="4.0;NetFx"} -Method PATCH -Body $requestBody $Uri
    }
    
    function Get-PlannerConfiguration
    {
    <#
    .Synopsis
    Retrieves tenant level settings for Microsoft Planner.
    .Description
    This cmdlet allows users and tenant administrators to retrieve policy preferences set by the tenant administrator regarding availability of certain features in Microsoft Planner.  While a feature may be permitted by a tenant administrator's preference, features can still be disabled due to Microsoft Planner behavior, at the discretion of Microsoft.
    .Parameter Uri
    The URL of the Tenant-Level Settings API for the Planner instance to retrieve.
    .Parameter AccessToken
    A valid access token of a user with tenant-level administrator privileges.
    
    .example
    
    Get-PlannerConfiguration
    #>
        param(
            [ValidateNotNull()]
            [System.String]$Uri="https://tasks.office.com/taskAPI/tenantAdminSettings/Settings",
    
            [Parameter(Mandatory=$false)]
            [ValidateNotNullOrEmpty()]
            [System.String]$AccessToken
            )
        
        if(!($PSBoundParameters.ContainsKey("AccessToken"))){
            $authorizationContext = Connect-AAD
            $accessToken = $authorizationContext.AccessTokenType.ToString() + ' ' +$authorizationContext.AccessToken
        }
        
        $response = Invoke-RestMethod -ContentType "application/json;odata.metadata=full" -Headers @{"Accept"="application/json"; "Authorization"=$AccessToken; "Accept-Charset"="UTF-8"; "OData-Version"="4.0;NetFx"; "OData-MaxVersion"="4.0;NetFx"} -Method GET $Uri
        $result = New-Object PSObject -Property @{
            "AllowCalendarSharing" = $response.allowCalendarSharing
            "AllowTenantMoveWithDataLoss" = $response.allowTenantMoveWithDataLoss
            "AllowRosterCreation" = $response.allowRosterCreation
            "AllowPlannerMobilePushNotifications" = $response.allowPlannerMobilePushNotifications
        }
    
        return $result
    }
    
    Export-ModuleMember -Function Get-PlannerConfiguration, Set-PlannerConfiguration
    ```
    
7. Copy the following code into a text editor and save it as SetPlannerTenantSettings.psd1 in the "microsoft.identitymodel.clients.activedirectory.3.19.8\lib\net45" folder.

    ```powershell
    #
    # Module manifest for module 'SetTenantSettings'
    #
    # Generated by: Microsoft Corporation
    #
    # Generated on: 12/17/2017
    #
    
    @{
    
    # Script module or binary module file associated with this manifest.
    RootModule = 'SetPlannerTenantSettings.psm1' 
    # Version number of this module. 
    ModuleVersion = '1.0' 
    # Supported PSEditions # 
    CompatiblePSEditions = @() 
    # ID used to uniquely identify this module 
    GUID = '6250c644-4898-480c-8e0b-bd3ebdf246ca' 
    # Author of this module 
    Author = 'Microsoft Corporation' 
    # Company or vendor of this module 
    CompanyName = 'Microsoft Corporation' 
    # Copyright statement for this module 
    Copyright = '(c) 2017 Microsoft Corporation. All rights reserved.' 
    # Description of the functionality provided by this module 
    Description = 'Planner Tenant Settings client' 
    # Minimum version of the Windows PowerShell engine required by this module #
    PowerShellVersion = '' 
    # Name of the Windows PowerShell host required by this module # 
    PowerShellHostName = '' 
    # Minimum version of the Windows PowerShell host required by this module #
    PowerShellHostVersion = '' 
    # Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only. #
    DotNetFrameworkVersion = '' 
    # Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only. # 
    CLRVersion = '' 
    # Processor architecture (None, X86, Amd64) required by this module #
    ProcessorArchitecture = '' 
    # Modules that must be imported into the global environment prior to importing this module # 
    RequiredModules = @() 
    # Assemblies that must be loaded prior to importing this module 
    RequiredAssemblies = @("Microsoft.IdentityModel.Clients.ActiveDirectory.dll","Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll") 
    # Script files (.ps1) that are run in the caller's environment prior to importing this module. # 
    ScriptsToProcess = @() 
    # Type files (.ps1xml) to be loaded when importing this module # 
    TypesToProcess = @() 
    # Format files (.ps1xml) to be loaded when importing this module # 
    FormatsToProcess = @() 
    # Modules to import as nested modules of the module specified in RootModule/ModuleToProcess # 
    NestedModules = @() 
    # Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export. 
    FunctionsToExport = @("Get-PlannerConfiguration", "Set-PlannerConfiguration") 
    # Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export. 
    CmdletsToExport = @() 
    # Variables to export from this module 
    VariablesToExport = '*' 
    # Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export. 
    AliasesToExport = @() 
    # DSC resources to export from this module # 
    DscResourcesToExport = @() 
    # List of all modules packaged with this module # 
    ModuleList = @() 
    # List of all files packaged with this module # 
    FileList = @("SetTenantSettings.psm1") 
    # Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell. 
    PrivateData = @{ PSData = @{ 
    # Tags applied to this module. These help with module discovery in online galleries. # 
    Tags = @() 
    # A URL to the license for this module. # 
    LicenseUri = '' 
    # A URL to the main website for this project. # 
    ProjectUri = '' 
    # A URL to an icon representing this module. # 
    IconUri = '' 
    # ReleaseNotes of this module # 
    ReleaseNotes = '' } 
    # End of PSData hashtable 
    } 
    # End of PrivateData hashtable 
    # HelpInfo URI of this module # 
    HelpInfoURI = '' 
    # Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix. # 
    DefaultCommandPrefix = '' }
    ```
    
8. Run this command to import these files into PowerShell, making sure to add your unique file path from your computer:

    ```powershell
    Import-Module [File path on your computer]microsoft.identitymodel.clients.activedirectory.3.19.8\lib\net45\SetPlannerTenantSettings.psd1 
    ```
    
Now you're ready to make changes to Planner at the organizational level using PowerShell.
---
title: "Set up directory synchronization for Office 365"
ms.author: robmazz
author: robmazz
manager: serdars
ms.date: 4/30/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846

description: "Learn how to set up directory synchronization between Office 365 and your on-premises Active Directory."
---

# Set up directory synchronization for Office 365

Office 365 uses the cloud-based user identity management service Azure Active Directory to manage users. You can also integrate your on-premises Active Directory with Azure AD by synchronizing your on-premises environment with Office 365. Once you set up synchronization you can decide to have their user authentication take place within Azure AD or within your on-premises directory.
  
## Office 365 Directory synchronization

You can either use synchronized identity or federated identity between your on-premises organization and Office 365. With synchronized identity, you manage your users on-premises, and they are authenticated by Azure AD when they use the same password in the cloud as on-premises. This is the most common directory synchronization scenario. Pass-through authentication or Federated identity, allows you to manage your users on-premises and they are authenticated by your on-premises directory. Federated identity requires additional configuration and enables your users to only sign in once. For details, read [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/article/06a189e7-5ec6-4af2-94bf-a22ea225a7a9).
  
## Want to upgrade from Windows Azure Active Directory sync (DirSync) to Azure Active Directory Connect?

If you are currently using DirSync and want to upgrade, head over to [azure.com](https://azure.com) for [upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).
  
## Prerequisites for Azure AD Connect

You get a free subscription to Azure AD with your Office 365 subscription. When you set up directory synchronization, you will install Azure Active Directory Connect on one of your on-premises servers.
  
For Office 365 you will need to:
  
- Verify your on-premises domain (the procedure will guide you through this).
    
- Have [Assign admin roles in Office 365 for business](https://support.office.com/article/EAC4D046-1AFD-4F1A-85FC-8219C79E1504) permissions for your Office 365 tenant and on-premises Active Directory. 
    
For your on-premises server on which you install Azure AD Connect you will need the following software:
  
|**Server OS**|**Other software**|
|:-----|:-----|
|Windows Server 2012 R2  <br/> |PowerShell is installed by default, no action is required.  <br/> Net 4.5.1 and later releases are offered through Windows Update. Make sure you have installed the latest updates to Windows Server in the Control Panel.  <br/> |
|Windows Server 2008 R2 with Service Pack 1 (SP1) or Windows Server 2012  <br/> |The latest version of PowerShell is available in Windows Management Framework 4.0. Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br/> .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br/> |
|Windows Server 2008  <br/> |The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br/> .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br/> |
   
> [!NOTE]
> If you're using Azure Active Directory DirSync, the maximum number of distribution group members that you can synchronize from your on-premises Active Directory to Azure Active Directory is 15,000. For Azure AD Connect, that number is 50,000. 
  
To more carefully review hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect, read [Prerequisites for Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=716896).
  
You can also review the Azure AD Connect [version release history](https://go.microsoft.com/fwlink/p/?LinkId=733238) to see what is included and fixed in each release. 
  
 **To set up directory synchronization**
  
1. Sign in to the Office 365 admin center and choose **Users** > **Active Users** on the left navigation. 
    
2. In the Office 365 admin center, on the **Active users** page, choose ** More ** > **Directory synchronization**.
    ![In the More menu, choose Directory synchronization](../media/dc6669e5-c01b-471e-9cdf-04f5d44e1c4b.png)
  
3. On the ** Is directory sync right for you? ** page, the two first choices of **1-10**, and **11-50** result in "Based on the size of your organization, we recommend that you create and manage users in the cloud. Using directory synchronization will make your setup more complex. Go to Active users to add your users." 
    
    You can still, however, continue setting up directory synchronization by choosing **Continue here** on the bottom of the page. 
    
    If you select the two latter choices, **51-250** or **251 or greater**, the synchronization setup will recommend directory synchronization. Choose **Next** to continue. 
    ![Choose NExt to continue setting up directory synchronization](../media/359a1eb9-99ae-4b5b-a413-4de53037cceb.png)
  
4. On the **Sync your local directory with the cloud**, read the information, and if you want more information, choose the learn more link that goes to: [Prepare to provision users through directory synchronization to Office 365](https://support.office.com/article/01920974-9e6f-4331-a370-13aea4e82b3e), and then choose **Next**. 
    
5. On the **Let's check your directory** page, review the requirements for automatically checking your directory. If you meet the requirements, choose **Next** > **Start scan**. If you can't meet the requirements you can still continue by choosing **continue manually**.
    ![Choose Next or continue manually on the Let's check your directory page](../media/af4a6bd5-13aa-4bfa-9751-4464a32ca8db.png)
  
6. If you select to scan your directories, choose **Start scan** on the **Evaluating directory synchronization setup** page. 
    
    Follow the instructions to download and run the scan.
    
7. Once the scan is complete, return to the setup wizard, and choose **Next** to see your scan results. 
    
8. Verify your domains as instructed on the **Verify Ownership of your domains** page. For detailed instructions, see [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
    > [!IMPORTANT]
    > After you have added a TXT record to verify you own your domain, do not go to the next step of adding users in the domains wizard. The directory synchronization will add users for you. 
  
    Return to the **Office 365 Setup** page and choose **Refresh**
    ![After you verify your domains, choose Refresh](../media/9b5fb593-5ff7-49f0-80d0-18e36d39d669.png)
  
9. On the **Your domains are ready** page, choose **Next**.
    
10. On the **Clean up your environment** page, optionally follow the instructions to download IDFix to check your Active Directory. Choose **Next** to continue. 
    
11. On the ** Run Azure Active Directory Connect ** page, choose **Download** to install Azure AD Connect wizard. 
    
    > [!NOTE]
    > At this point you will be in the Azure AD Connect wizard. Make sure you leave the directory synchronization wizard page you were last on open in your browser, so you can return to it after the Azure AD Connect steps are done. 
  
    After Azure AD Connect wizard has installed it will automatically open. You can also open it from your desktop, the default install site. Follow the wizard instructions depending on your scenario:
    
  - For directory synchronization with password hash synchronization, use [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).
    
  - For multiple forests, pass-through authentication, federated identity and SSO options, use [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).
    
    Select **Customize** on the **Express Settings** page to use these options. 
    
12. After the Azure AD Connect wizard is done, return to the **Office 365 Setup** wizard, and follow the instructions on the **Make sure sync worked as expected page**. Choose **Next** to continue. 
    
13. Read the instructions on the ** Activate users ** page and then choose **Next**.
    
14. Choose **Finish** on the **You're all setup** page. 
    
 **Assign licences to synchronized users**
  
- After you have synchronized your users to Office 365, they are created but you need to assign licenses to them so they can use Office 365 features, such as mail. For instructions, see [Assign licenses to users in Office 365 for business](../billing/assign-licenses-to-users.md).
    
 **Finish setting up domains**
  
- Follow the steps in [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23) to finish setting up your domains. 
    
||
|:-----|
|![The short icon for LinkedIn Learning.](../media/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **New to Office 365?**         Discover free video courses for [Office 365 admins and IT pros](68cc9b95-0bdc-491e-a81f-ee70b3ec63c5.md), brought to you by LinkedIn Learning. |
   
## See Also

[View directory synchronization status in Office 365](https://support.office.com/article/18be3b98-34ae-47be-9337-ab6c3fb372ac)
  
[Fixing problems with directory synchronization for Office 365](https://support.office.com/article/79c43023-5a47-45ae-8068-d8a26eee6bc2)
  
[Turn off directory synchronization for Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)
  


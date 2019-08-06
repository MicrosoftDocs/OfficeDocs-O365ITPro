---
title: "Office 365 Customer Lockbox Requests"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 36f9cdd1-e64c-421b-a7e4-4a54d16440a2
description: "Learn about Customer Lockbox requests that allow you to control how a Microsoft support engineer can access your data when you run into an issue."
---

# Customer Lockbox in Office 365

> [!NOTE]
> This article provides deployment and configuration guidance for a feature that is currently available only for organizations that have a Microsoft 365 E5 or Office 365 E5 subscription, or that have an Information Protection and Compliance or Advanced Compliance add-on subscription.

Customer Lockbox ensures that no one at Microsoft can access customer content to perform a service operation without the customer’s explicit approval. Customer Lockbox brings the customer into the approval workflow for requests to access their content.

Occasionally, Microsoft engineers are involved during the support process to troubleshoot and fix customer reported issues. In most cases, issues are fixed through extensive telemetry and debugging tools that Microsoft has in place for its services. However, there may be cases that require a Microsoft engineer to access customer content to determine the root cause and fix the issue. Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow. This gives organizations the option to approve or deny these requests, which gives them direct control of whether or not a Microsoft engineer can access their data.

### Customer Lockbox overview video

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business. To recommend support for other Office 365 services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).

## Customer Lockbox workflow

The following steps outline the typical workflow when a Customer Lockbox request is initiated by a Microsoft engineer:

1. Someone at an organization has an issue with their Office 365 mailbox.

2. After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.

3. A support engineer reviews the service request and determines a need to access customer’s Exchange Online content to repair the issue.

4. The support engineer logs into the Customer Lockbox request tool and makes a data access request by specifying the customer's tenant name, service request number, and the estimated duration for which access to the data is needed.

5. After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the customer's organization an email notification about the pending access request from Microsoft.

    ![Example of a Customer Lockbox email notification](../media/CustomerLockbox1.png)

   > [!NOTE]
   > Anyone who is assigned the [Customer Lockbox access approver](../add-users/about-admin-roles.md) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.

7. The approver signs in to the Microsoft 365 admin center and approves the request. Note that this step triggers the creation of an audit record that can be retrieved by searching the Office 365 audit log. For more information, see the [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests) section.

   If the customer rejects the request or the request isn’t approved within 12 hours (at which time the request expires), no access is granted to the Microsoft engineer.

   > [!IMPORTANT]
   > We don't include any links in the Customer Lockbox email notification that requires you to sign in to Office 365.

8. After the customer approves the request, the Microsoft engineer receives the approval message, logs into Exchange Online, and fixes the customer's issue. Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked. 
 
  > [!NOTE]
> All actions performed by a Microsoft engineer are logged in the Office 365 audit log. You can search for and review these audit record and can be searched for and reviewed.

## Turn Customer Lockbox requests on or off

An Office 365 administrator can turn on Customer Lockbox controls in the Microsoft 365 admin center. When Customer Lockbox is turned on, Microsoft is required to obtain an organization’s approval prior to accessing any of their content.

> [!NOTE]
> To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.

1. In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.


2. On the **Customer Lockbox** tile, select **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## Approve or deny a Customer Lockbox request

> [!NOTE]
> To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.

1.  Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.

2.  Select **Support > Customer Lockbox Requests**.


    A list of Customer Lockbox requests are displayed.

    ![List of Customer Lockbox requests](../media/CustomerLockbox6.png)

3.  Select a Customer Lockbox request, and then select **Approve** or **Deny**.
    
    ![Approve or deny Customer Lockbox requests](../media/CustomerLockbox7.png)

    A confirmation message about the approval of the Customer Lockbox request is displayed.

    ![Approve or deny Customer Lockbox requests](../media/CustomerLockbox8.png)

## Auditing Customer Lockbox requests 

Audit records that correspond to the Customer Lockbox requests are logged in the Office 365 audit log and can be accessed by using the [Audit log search tool](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance) in the Office 365 Security & Compliance Center. Actions related to a customer accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are logged in the Office 365 audit log. You can search for and review these audit records.

> [!NOTE]
> You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. For more information, see [Search the audit log in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).

### Search the audit log for activity related to Customer Lockbox requests

Here's how to create an audit log search query to return audit records related to Customer Lockbox:

1. Go to [https://protection.office.com](https://protection.office.com).
  
2. Sign in to Office 365 using your work or school account.

3. In the left pane of the Security & Compliance Center, select **Search & investigation** > **Audit log search**.
    
    The **Audit log search** page is displayed. 
    
    ![Audit log search page](../media/auditlogsearch1.png)
  
4. Configure the following search criteria:
    
    a. **Activities** - Leave this field blank so that the search returns audit records for all activities. This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.
    
    b. **Start date** and **End date** - Select a date and time range to display the events that occurred within that period.

    c. **Users** - Leave this field blank.
    
    d. **File, folder, or site** - Leave this field blank.
    
5. Select **Search** to run the search using your search criteria. 
    
    The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.

6. Select **Filter results** on the search results page, and do one of the following things:

   - To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.
   
   - To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**. Note that the action performed by the engineer is displayed int the **Activity** column.

      ![Filter on "Microsoft Operator" to display audit records](../media/CustomerLockbox10.png)

7. In the list of results, select an audit record to display it.

### Audit record for a Customer Lockbox access request

When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the Office 365 audit log. This record contains the following information. 

| Audit record property| Description|
|:---------- |:----------|
| Date       | The date and time when the Customer Lockbox request was approved or denied.
| IP address | The IP address of the machine the approver used to approve or deny a request. |
| User       | The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.            |
| Activity   | Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.                                |
| Item       | The Guid of the Customer Lockbox request                             |

The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request. If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.

![Audit record for an approved Customer Lockbox request](../media/CustomerLockbox9.png)

> [!TIP]
> To display more detailed information in an audit record, select **More information**.

### Audit record for an action performed by a Microsoft engineer

As previously explained, the actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log. These records contain the following information.

| Audit record property| Description|
|:---------- |:----------|
| Date       | Date time when the action was performed. Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.              |
| IP address | The IP Address of the machine Microsoft engineer used. |
| User       | Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.                                  |
| Activity   | Name of the activity performed by the Microsoft engineer.|
| Item       | \<empty\>                                             |


## Frequently asked questions

#### Which Office 365 services does Customer Lockbox apply to?

Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.

#### Is Customer Lockbox available to all Office 365 customers?

Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription. Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.

#### What is customer content?

Customer content is the data created by users of Office 365 services and applications. Examples of customer content include:

  - Email body or email attachments

  - SharePoint site contents

  - Information in the body of a SharePoint file

  - Skype for Business presentation file body

  - Instant messages (IM) or voice conversations

  - Customer generated blob or structured storage data (for example, SQL Containers)

  - Customer-owned security information (for example, certificates, encryption keys, and passwords)

  - Inferences, and all subsequent inferences, if customer content remains

For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/en-US/business/office-365-trust-center-privacy/).

#### Who is notified when there is a request to access my content?

Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified. These are also the same users who can approve for Customer Lockbox requests.

#### Who can approve or reject these requests in my organization?

Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests. Customers control these role assignments in their organizations.

#### How do I opt-in to Customer Lockbox?

A global administrator can enable and configure Customer Lockbox in the admin center.

#### If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?

After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets. Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Office 365 Security & Compliance Center.

#### How do I know that Microsoft follows the approval process?

You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.

Additionally, Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports). For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).

#### Can Microsoft modify the list of approvers for my tenant? If not, how is it prevented from happening?

Only a global administrator in your organization can specify who can approve Customer Lockbox requests. That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request. Membership of the Global administrator group in Azure Active Directory is solely managed by your organization.

#### What if I need more information about a content access request to approve it?

Each Customer Lockbox request contains an Office 365 service request number. You can contact Microsoft Support and reference this service number to get more information about the request.

#### When a Customer Lockbox request is approved, how long are the permissions valid?

Currently, the maximum period for the access permissions that are granted to the Microsoft engineer is 4 hours. The Microsoft engineer can also request a shorter period.

#### How can I get a history of all Customer Lockbox requests?

All Customer Lockbox requests can be viewed in the Microsoft 365 admin center.

#### How do I correlate the content access requests with the related audit logs?

The Compliance Center Activity Feed will contain log activities of Customer Lockbox. Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.

#### What happens when a customer doesn't respond to a Customer Lockbox request?

Customer Lockbox requests have a default duration of 12 hours. If you don't respond to a request within 12 hour, the request expires and can't be acted on.

#### What does Microsoft when a customer rejects a Customer Lockbox request?

If a customer rejects a Customer Lockbox request, no access to customer content will occur. If a user in your organization is experiencing a service issue that required Microsoft to access customer content to resolve the issue (although such circumstances are rare) then the service issue might persist, and Microsoft would inform the user about this.

#### Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?

No. Microsoft takes third-party requests for customer data very seriously. As a cloud service provider, we always advocate for the privacy of customer data. In the event we get a subpoena, we always attempt to redirect the third party to the customer to obtain the information. (Please read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). We periodically publish [detailed information](https://www.microsoft.com/en-us/corporate-responsibility/lerr) about the law enforcement requests that we do receive.

Also, see the [Microsoft Trust Center](https://www.microsoft.com/en-us/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.

#### How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?

Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems. Office 365 operates with the principles of least privilege and just-in-time access. Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis. If permission is granted, it is for a limited duration. 

Office 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service. An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted. That second person can't be the requestor and must be designated to approve access to customer content. Only if the request is approved does the operator acquire temporary access to customer content. After the elevation period expires, the access is revoked by Lockbox.

Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about our general security practices.

#### Under what circumstances do Microsoft engineers need access to my content?

The most common scenario where Microsoft engineers may need to access customer content is when the customer makes a support request that requires access for troubleshooting. A foundational principle of Office 365 is that we should be able to operate our service without Microsoft personnel having access to customer content, and nearly all service operations performed by Microsoft are fully automated and the human involvement is highly controlled and abstracted away from customer content. What we aspire to achieve for Office 365 is that we never have access to customer content to support the service until the customer approves a specific request that allows Microsoft personnel such access. The ability to offer Customer Lockbox reflects our engineering progress.

#### I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?

Customer Lockbox provides an additional layer of control by offering customers the ability to give explicit access authorization for service operations. By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox may also help customers meet certain compliance obligations such as HIPAA and FEDRAMP.

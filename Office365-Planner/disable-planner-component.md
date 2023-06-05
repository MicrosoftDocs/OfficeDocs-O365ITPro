# How to turn off the Planner component for your organization

## What is the Planner component?
The Planner component allows users to create, view, and edit Planner plans as a Loop component in the same way that they can view and edit plans in the Planner web app. It is available in the Loop app and in Microsoft apps that support Loop, for example, in Outlook, Word, and Teams.
In the Loop app for example, users can paste the URL for a plan into a Loop page and it will render Planner UX inline in that page so that they can view and edit that plan. Users can also insert a Planner component from the component insertion menu, which will create a new [lightweight plan](https://support.microsoft.com/en-us/office/about-plans-that-aren-t-in-groups-3208332f-14db-408d-ba2a-58eea26b19d5).

> [!NOTE]
> The Planner component is a new feature that may not be available in every Microsoft app that supports Loop yet.

## How do I turn off the Planner component for my organization?
The Planner component can be disabled via the View and edit Planner plans with the Planner Loop component cloud policy setting. This policy setting controls whether users can create and view Planner plans as a Loop component in the Loop app and in Microsoft apps that support Loop for example, in Outlook, Word, and Teams. See [Overview of Cloud Policy service for Microsoft 365](/deployoffice/admincenter/overview-cloud-policy) for steps to configure cloud policies.

## How do I turn off the Planner component for specific users in my organization?
To turn off the Planner component for specific users in your organization, you can scope the policy setting in [How do I turn off the Planner component for my organization?](#how-do-i-turn-off-the-planner-component-for-my-organization) to a new or existing Microsoft 365 group that defines the users in your organization that the policy will apply to. You can learn how to create a Microsoft 365 group by visiting [Create a Microsoft 365 group](/microsoft-365/admin/create-groups/create-groups). If you prefer, you can also create other types of groups to use with Cloud Policy. See [learn more about creating groups in the Microsoft 365 admin center](/microsoft-365/admin/email/create-edit-or-delete-a-security-group) or [learn more about creating dynamic groups in AzureAD](/azure/active-directory/external-identities/use-dynamic-groups).
The Planner component is also only available to users that have a Planner license. To control which users have Planner licenses, follow the instructions in [How to use Office 365 PowerShell to manage Microsoft Planner licenses](/office365/troubleshoot/licensing/how-to-use-office-365-powershell-to-manage-microsoft-planner-licenses).

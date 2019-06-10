---
title: "What's new in the Microsoft 365 admin center?"
ms.author: anfowler
author: anfowler
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.custom: Core_O365Admin_Migration
ms.collection:
  - M365-subscription-management
search.appverid:
  - MET150
  - MOE150
  - FRP150
ms.assetid: 739574d7-2c5b-4911-a549-f56ecc7d3b48
description: "The Microsoft 365 admin center - learn about the features that were added this month."
f1_keyword: MACDashWhatsNew
---

# What's new in the Microsoft 365 admin center

We're continuously adding new features to [the Microsoft 365 admin center](microsoft-365-admin-center-preview.md), fixing issues we learn about, and making changes based on your feedback. Take a look below to see what's available for you today.

> [!TIP]
> Interested in what we're currently working on and plan to release soon? Check out [What's next for the Microsoft 365 admin center](microsoft-365-whats-next.md). 

## May 2019

### May's featured fix - Case sensitivity
Now when you search for shared mailboxes, contacts, resources, and mailbox permissions, your search terms don't have to be case-sensitive. 

**User and group management**<br>
This month, we updated **Block user**, **Reset password**, **Contacts** list view, **Groups** list view, and the **Groups** details pages to the new admin center style. With the new **Groups** list view, you get richer data about your groups, quick actions in the command bar, and you can customize the way you see your data -- and the groups list remembers how you want to see your data. 

**Recommendations**<br>
You might see a new recommendation pop-up in your admin center - we just added 5 new ones. Of course, you'll only see recommendations if we think it will benefit your organization. But don't wait until we show you the recommendation - you can add it from the card library.
- **Password expiry** - We recommend that passwords get set to **Never expire**. And if your org has a different setting, you might just see this recommendation. 
- **Too many global admins** - Because having too many global admins is a security threat, if you have more than 4 global admins, you'll see this recommendation. We suggest giving users only the access they need to get their job done.
- **Intune device protection** - If your licenses include Intune and we detect that you either haven't finished setting up Intune or enrolled your devices, we'll recommend that you create an Intune policy to protect your organization's files when users access them from their mobile devices.
- **Get monthly Office feature updates** - We've gotten feedback from our very small customers that when they get monthly Office feature updates, their users are  happier. So, if you're a very small business and you're currently get your Office feature updates every six months, you'll see this recommendation.

**Settings** <br>
As for settings, there have been quite a few changes. Mostly, just updating the existing settings to the new admin center style. As we're moving forward and add new settings that you've never seen before, we'll start mentioning them here. 

## April 2019

Things are looking great for the admin center. We've been reading your feedback and suggestions, answering most of them, and really taking all you have to say to heart. Of course, we're still doing the work to make sure everything is up to parity with the old admin center. And please remember - as we roll out new features, you might not get it right away.

### Featured feature - Add users

For April, we're featuring the **Add user** wizard that walks you through...wait for it...adding users. It's a step-by-step to add the user's basic info like email and display name, assigning a license and a role, adding their contact information, and then reviewing the user's account before you commit. **Why did we make this change?** We heard your feedback that you didn't like the nearly infinite scroll to add users in the previous experience.
<br> ![Screen capture of the Add user wizard.](media/MAC-AddUserWizard.png) <br>

There are two ways you can check it out: <br>

1. From the **Home** page, select **Add user** from the **User management** card. The wizard opens right there, so you don't have to navigate from any work you're doing on the **Home** page.
2. Go to **Users** > **Active users**, and then select **Add user** from the command bar.
<br><br>
We've made a few more changes to **user management**, here's a quick list:
- The **Manage roles** pane has been updated to the new style and is accessible. We've also updated the **Block user** and **Delete user** panes to the new style.
- **Manage product licenses** changed position in the command bar.
- Changing a user's photo is now easier. In **Active users** select a user, and then **Change photo** under their picture.

### But wait! There's more...
- There's a new setup banner on the **Home** page that you'll see if you haven't finished the set up steps, like adding a domain, adding users, and downloading the Office apps.
- The **Group** list and details pane have been updated to the new style. Go to **Groups** > **Groups** to view the changes. 
    - Speaking of groups, we've also added a **Microsoft Teams** tab to the groups details pane where you can turn any Office 365 group into a Team. To "teamify" a group select any Office 365 group from the list, select the **Microsoft Teams** tab, and then **Create Team**. If the group is already a Team, you'll get a link to manage it from the **Teams admin center**.
    - Finally, you can add the **Teams status** to the **groups** list. On the column header, select **Choose columns** > **Teams status** > **Save**.
- **New limited admin roles** - We've release some new admin roles so that you can give users only the access they need.
    -  **Kaizala admin**: Users in this role have permission to perform all management tasks within Microsoft Kaizala, including create and manage users in Kaizala directory, manage Kaizala groups, manage action cards and connectors, and create service requests.
    - **Search admin**: Users in this role have full access to all Microsoft Search management features in the Microsoft 365 admin center. Search admins can delegate the Search admin and Search editor roles to users, and create and manage content, like bookmarks, Q&A items, and locations. Additionally, these users can view the message center, monitor service health, and create service requests.
    - **Search editor**: Users in this role can create, manage, and delete content for Microsoft Search in the Microsoft 365 admin center, including bookmarks, Q&A items, and locations.
- There's a bonanza of **Billing** changes this month...
    - You can now update the CVV for existing credit cards without having to delete it and add it again. You can update the CVV by going to **Bills** > **Payment methods**.
    - We've made it easier to locate your **Invoices** and understand any billing issues your account may be having. And now you can see your Bills in the web browser instead of having to download the PDF. Go to **Bills** > **Invoices**.
    - On the **Products & services** page, we now aggregate your subscription information if you've got multiple subscriptions of the same type.

## March 2019 - We've officially released the admin center!

Well, if you missed the exciting news, we've officially release the new and improved Microsoft 365 admin center! Here's the blog post where we announced it: [The new Microsoft 365 admin center available today](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870). For March, we'll rely on the blog post for you to check out the features released - plus, you can also read the post for the features that are getting released in the near future, which we're not allowed to do in core content.
<br> ![Screen capture of the home page of the Microsoft 365 admin center.](media/M365AC-HomePage.png) <br>
We do have one change to the **Billing & subscriptions** area that we'd like to mention. I mean, y'all didn't think we were done with improving it, did you? Because we're not! In fact, this month we added added the ability to manage your partner relationships to **Billing** > **Billing accounts**. From here you can review your partner relationships across Advisor, CSP, and Indirect resellers. You can also accept new partner relationship requests, including delegated admin permissions.

As always, your feedback is important to us, so keep it coming! On any page in the admin center, you can give feedback by selecting **Give feedback** in the bottom-right, next to **Need help?**

## February 2019 - Billing & Subscriptions Edition

This month, we're going to focus on all the improvements we've made to the areas affectionately referred to as "Billing and subscriptions". In the past, you probably didn't refer to those things affectionately, but we think you will now...

- **Payment methods** - We heard your feedback that updating your payment method was difficult and we've made a lot of changes around it. Go to **Billing** > **Payment methods**. You can easily see your payment methods, like your Visa card, and which subscription it is associated with. In your list of payment methods, select the **More** menu (3 little dots next to the expiration date), and then select **View subscriptions**. You can also edit and delete your payment methods using the **More** menu.
- **Billing account** - Targeted release customers will see the new Billing account page first and then we'll roll it out to world-wide. When it's available for you, go to **Billing** > **Billing account**. What can you do on the new billing account page? I'm glad you asked:
  - Update the address and other contact information in your organizational profile directly from this page. You don't have to go to **Settings** > **Organization profile**, unless you want to.
  - And we're making life easier for Direct or Volume licensing customers, you can accept and review customer agreements from **Billing accounts**. You can also connect with other orgs allowing you to link the orgs together to share licenses and resources.
- We've also done a few smaller enhancements and bug fixes:
  - Reactivate a subscription with an Invoice payment
  - Edit the service usage address for your subscriptions
  - And on the Inventory details page, we've added some notification enhancements, we link you to the actual page where you can do the work, and there are more actions on the inventory details card. Go to **Billing** > **Bills** > **View details** on any invoice.

## January 2019 - Happy New Year!

- Still adding in **Services & add-ins** - We've updated more of the **Settings > Services & add-ins** pages. Try Integrated Apps or Reports to see the latest.
- **Searching for improvements?** Look no further than the **Search** box in the command bar. It's been updated to let you search for tasks. For example, try "password reset" or "add a user".

### Featured Feedback Fix - Licenses and apps

We re-combined **Licenses and apps** in the user details pane based on your feedback. We initially separated the two features to provide space for the details of all license and all app possibilities. We heard from you that separating licenses and apps into two panes added confusion. We listened, and brought licenses and apps back together into one tab. Now you can make sure that an app is turned off in all licenses assigned to a user in one pane. Milk and cookies. Licenses and apps. We get it now.

Check it out: **Users > Active users > Edit** or **Add user > Licenses and Apps**.

## December 2018

- **Services & add-ins** - In October we updated **Settings** \> **Services & add-ins** with our new design style, but all of the settings pages were still in the classic style. This month, we've started updating the actual settings to the new design. Check out **Bookings** to see the new look.
- **User management** - Manage username, alias, primary email address.
- We've added two Home cards to the library. You can read their full descriptions in the library.
  - **Intune Device enrollment**
  - **Domains**
- **Recommendations** - You might see a new recommendation pop-up in your admin center. Of course, you'll only see recommendations if we think it will benefit your organization. But don't wait until we show you the recommendation - you can add it from the card library.
  - **Protect sensitive info** - We recommend creating a data loss prevention (DLP) policy to detect when items containing sensitive info are shared with people outside your organization.

## November 2018

- The Search box is back! And we moved it slightly. It's still at the top of the Home page, but it's now on the right-side of the page near the **Add card** button. <br> ![Screen capture explaining that the search box is located in the upper right-side of the Home page.](media/M365PreviewSearchBox.png)

- We've added cards for the dashboard. Just go to the admin center and select **Add card** to see the new cards:
  - **Office 365 Active users report** - Monitor the usage of the Office 365 services you've purchased.
  - **Office 365 software** - Install or deploy Office 365 ProPlus software and see how many licensed users have activated it.
  - **Azure Active Directory** - Gives you quick access to common Azure AD tasks like self-serve password resets, customizing sign-in, and adding apps.
- The **Export users** quick task has been added to command bar on the Active users page. ![Screen capture showing Export users on the command bar next to Refresh.](media/M365PreviewExportUsersQT.png)
- Purchase services has additional enhancements for November. And they are ALL good! To get there, go to Billing > Purchase services. <br>![Screen capture showing purchase services page with 3 new enhancements.](media/M365PreviewBillingPurchasServices.png)
  > 1.  At the top of the page, you can pivot between Business and Education plans. That will help you find what you're looking for.
  > 2.  We added a search box so you don't have to scroll endlessly to find what you're looking for.
  > 3.  Finally, we logically sorted the plans you can purchase into sections that you can expand and collapse. Don't need purchase any of the **Office apps and services**? Collapse that section and focus on Microsoft 365 plans.

## October 2018

- There's a new way to buy subscriptions in the Microsoft 365 admin center. Go to **Purchase services** to see the completely redesigned shopping experience that makes it easy to search, compare plans, and other great new features that helps make purchasing a subscription easier. <br/>![Purchase services plan comparison in Microsoft 365 admin center preview](media/0ad5acf1-8ffc-44bf-aac2-c21269910e65.png)

- The **Services and add-ins** page has been updated to the new look and feel, but everything else works exactly the same. Of course, you should check out the command bar to see what new things you can do, like filtering and changing the list to compact view. In the navigation pane, go to **Settings** \> **Services &amp; add-ins** to check it out. <br/>![Settings and add-ins page in Microsoft 365 admin center preview](media/af9a3ed3-bfe6-438b-b4b5-2ca4164f8e3f.png)

## September 2018

- **Home improvements** The Home page has been completely re-done and we can't wait for you to try it out and see what you think. This is your personal Home page and you won't affect the Home pages of other admins in your organization. <br/>![Screen capture: Microsoft 365 Admin Center Preview Home Page.](media/d1a497f1-30e6-4c1a-9bb2-d4d7895906da.png)

  - You can add, remove, and move home page cards around the Home page. Click **+ Add card** in the top right corner to see which cards are available in the card library, and then drag them anywhere on the Home page. Don't like where it landed? Click and drag it to where you want it. You don't even have to save any more.

  - Take organization to the next level by grouping cards into sections. We've created two default sections for you: **Basics** and **Devices and updates.** Very soon, you'll be able to add, remove, and rename sections to design a Home page that works for you.

  - Most of the cards are informative and actionable, which means that you'll be provided with just-in-time information to help you do your daily tasks faster and smarter.

  - The navigation pane has been re-organized and you can customize it for your quick tasks. Just select **Edit** from the bottom of the navigation pane to start customizing. <br/>![Microsoft 365 Admin Center Preview navigation pane](media/7d5568cc-9ce8-40b2-aa87-e777fcd455e3.png)

- **Billing** You'll probably notice some of the biggest changes to the Microsoft 365 admin center in the Billing section. You can manage subscriptions and apps you've bought from Microsoft or another vendor, including new experiences for inventory management, order history, payment methods, and invoicing.

  - Subscription management has been redesigned to give you a new inventory management experience for more product types including apps, software, and add-ins. It's now called **Products &amp; services** to better reflect the support for new product types being added. You can now choose to have a card or table view of the products and services, and you can search and filter to quickly find what you're looking for. <br/>![Products and services in Microsoft 365 admin center preview](media/f1bba7dc-2034-4a53-b4ad-b7fbef3fb442.png)

  - It's now easier than ever to assign a product license to your users. Select your purchased product and then you can assign the product. You can also see which users have already been assigned a particular product. <br/>![Product details from Billing in Microsoft 365 admin center preview](media/82422685-e1b7-4f3f-aea8-1819df9d9311.png)

  - **Switch plans** is now called ** Upgrades ** and finally the subscription upgrades happen behind the scenes so you don't have to watch the upgrade complete. Lastly, there is no longer a license limitation on upgrades.

- **User management** We've made a lot of changes to user management to help you get your work done faster. We've updated the ** Active users ** page and the user's details pane. Here's some of the more awesome changes:

  - There's a new design and new layout to the **Active users** page. Don't like the way the list looks? Select **Change view** (next to **Filter**) and you can change the list from **Normal list** to **Compact list**. Compact list is especially helpful if you've got a lot of users in your organization. <br/>![Active users page in preview](media/4dd9f1c9-ef23-4194-9ff8-5206ba2930f8.png)

  - The command bar (where **Search** lives) is dynamic and the list of actions will change depending on the number of users you've selected: no users, one user, or multiple users. You'll also see how many users you have selected next to **Search**. <br/>![Microsoft 365 preview Active users command bar.](media/9576bd19-31a5-4e59-a8dd-0663a833def0.png)

  - You can perform quick tasks like resetting passwords for single or multiple users directly from the list view.

  - The User's details and settings are now organized by the following tabs: **Account**, **Devices**, **Licenses**, **Apps**, **Mail**, and **OneDrive**. Previously, many of these settings were located across multiple screens. <br/>![Users detail pane in the admin center preview.](media/60c6b9d3-d62f-4b8d-97db-41ff247b1bf0.png)<br/>

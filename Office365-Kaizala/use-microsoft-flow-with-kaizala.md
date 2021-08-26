---
title: Integrate your workflow in Kaizala using Microsoft Flow
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 8/21/2018
audience: Admin
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 883343d0-6b16-4725-a23d-bc69fb264356
description: Learn how to use Microsoft Flow to help users automate their workflow and improve their productivity by allowing Kaizala to integrate with other services seamlessly.
---

# Integrate your workflow in Kaizala using Microsoft Flow

Microsoft Flow automates business process by providing a platform to integrate one service with other services. These services are the ones, which are registered on Microsoft flow as Connectors. [Learn more about Microsoft Flow](https://go.microsoft.com/fwlink/?LinkID=858639). Microsoft Kaizala is now available as a Connector on Microsoft Flow. This helps a user to automate their workflow and improve their productivity by allowing Kaizala to integrate with other services seamlessly. Below are some examples of how Microsoft Flow allows users to automate their workflows across services:
  
- A pharmaceutical sales manager, wants to send product listing info in his sales team group on Kaizala, whenever he receives an email from the regional sales office.
    
- A Teams admin would like to save all attachments sent in a Kaizala Group to the Team's SharePoint site.
    
- A shop owner wants to receive an email for each sales response he gets on his surveys, sent to his customer group on Kaizala.
    
- An organization admin wants to send an announcement to a employee in the organization, whenever a new employee joins a particular organization group
    
## Create a Flow using Kaizala Trigger

What you need before you can run these steps:
  
- A Kaizala admin account, an account on flow.microsoft.com and your Office 365 username and password.
    
 **Receive an email in Outlook, whenever someone responds to a survey**
  
1. In flow.microsoft.com, select **My flows** in the top navigation bar, and then select **Create from blank**.
    
2. Click on **Search hundreds of connectors and triggers**.
    
3. On the **Search all connectors and triggers** page, type **Kaizala**, and then select **Microsoft Kaizala - When someone responds to a survey**.
    
    ![Type Kaizala, and then select Microsoft Kaizala - When someone responds to a survey.](media/d4abbccc-e5f4-4a3f-811c-81faf7297178.png)
  
4. If you haven't already connected your Kaizala account to Microsoft Flow, select **Sign in to Kaizala**, and enter your Kaizala admin username and password.
    
5. On the Group page, select the group in which the survey has been posted.
    
    ![Select a group.](media/d8f4889c-8f23-45c8-b1b5-73521081a66d.png)
  
Now you can specify what action you want to take:
  
- Select **New step**, and then select **Add an action**.
    
- On the **Search all connectors and actions** page, type **send email**, and then select **Office 365 Outlook - Send an email**If you're prompted, sign in with your Office 365 global admin account.
    
    ![Select action: Office 365 Outlook - Send an email.](media/f8938e56-64d0-4827-9528-88239881f430.png)
  
- On the **Send an email** page, type your email address in the **To** field and select your name from the list. 
    
    ![Select your email from the list.](media/bd08b595-94e8-4eac-90b8-f69b478e122a.png)
  
- In the **Subject** field, type **New Response from**, press the spacebar.
    
    ![Choose a subject.](media/c5220e01-83d0-48f0-8ed1-1d547f236347.png)
  
- Select **Responder Name** from the list of tokens, to add a placeholder for it. 
    
- In the **Body** field, click **Response Title token** to add a placeholder for it. 8. You can add more tokens, other content, or both to the body of the email. 
    
- At the top of the screen, name your flow, and then select **Create flow**. Select **Done** to update the list of your flows. 
    
- Post a response in the survey that you created in the selected group. Within a minute, an email message notifies you of the new survey.
    
## Create a Flow using Kaizala as Action

What you need before you can run these steps:
  
- A Kaizala admin account, an account on flow.microsoft.com and your Office 365 username and password.
    
 **Send a message on Kaizala group, whenever a tweet is posted for a particular hashtag**
  
1. In flow.microsoft.com, select **My flows** in the top navigation bar, and then select **Create from blank**.
    
2. Click on **Search hundreds of connectors and triggers**.
    
3. On the **Search all connectors and triggers** page, type **Twitter**, and then select **Twitter - When a new tweet is posted**.
    
    ![Choose Twitter.](media/bf649578-c9d6-4f3b-a7a9-533df93793db.png)
  
4. If you haven't already connected your Twitter account to Microsoft Flow, select **Sign in to Twitter**, and enter your Twitter username and password.
    
5. In the **Search text** field, type the keyword you want. 
    
    ![Type in your keyword that you want.](media/25641493-767a-4e3f-9eff-de5f8d066b8b.png)
  
Now you can specify what action you want to take:
  
1. Select **New step**, and then select **Add an action**.
    
2. On the **Search all connectors and actions** page, type **Kaizala**, and then select **Microsoft Kaizala - Send a message**If you're prompted, sign in with your Office 365 global admin account.
    
3. On the **Send text message to a group** page, enter the group name and the message that you want to send. 
    
    ![Enter the group name and the message that you want to send.](media/a25d776a-b3e1-48b3-81f0-c7bffbafd53d.png)
  
4. At the top of the screen, name your flow, and then select **Create flow**. Select **Done** to update the list of your flows. 
    
5. Send a tweet with the keyword that you indicated. Within a minute, a message notifies you of the new tweet in the selected Kaizala group.
    


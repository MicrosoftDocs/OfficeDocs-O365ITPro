---
title: "Kaizala Connectors"
ms.author: kwekua
author: kwekua
manager: scotv
ms.date: 6/12/2017
ms.audience: ITPro
ms.topic: article
ms.service: Kaizala
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 223791c8-718d-4669-8c5e-a76804ae1ddd
description: "Kaizala Connector allows developers to integrate an organization's systems and processes with Kaizala using REST based APIs. For example, you can:"
---

# Kaizala Connectors

Kaizala Connector allows developers to integrate an organization's systems and processes with Kaizala using REST based APIs. For example, you can:
  
- automate group creation
    
- group membership management
    
- post messages
    
Kaizala Connectors provide actions on the following entities:
  
- messages
    
-  instant messages 
    
- surveys and polls
    
- groups
    
## Create Kaizala Connector

To create a new Kaizala Connector:
  
- Navigate to **Connectors** on the left navigation bar and click **New Connector** on the top right of the page. 
    
    ![Screenshot: Create a Kaizala connector](media/fd2b88b1-3260-4392-81b9-d2b8e1ba40db.png)
  
- On the New Connector page, enter a **Connector Name** and a short description for the connector and click or tap **Create**.
    
    ![Screenshot: Sample Kaizala connector for marketing group](media/083806aa-81fe-45d7-bf7a-62de5232d7c9.png)
  
Connector Id and Connector Secret are attributes that are used with group specific generated refresh token to make REST API calls in specific Kaizala groups. You can also view these details from Connector details in the Kaizala admin portal.
  
## View Kaizala Connectors

To view Kaizala Connectors:
  
1. Navigate to **Connectors** on the left navigation bar. 
    
2. By default, connectors created by logged in user are shown. To see all the Connectors in the organization, select **All Connectors** from the drop-down menu list. 
    
    ![Screenshot: View Kaizala connectors](media/3e8f9ebe-2003-487f-a759-3cf17e876cec.png)
  
## Activate or deactivate Kaizala Connector

Deactivating a Kaizala Connector means that the connector won't be available for generating tokens for any new groups. The connector will continue working for existing groups for which the token was generated. A connector can be removed from a group without reactivating it, however, once removed, the token can't be generated for the removed group, unless the it is activated again. To activate or deactivate a connector:
  


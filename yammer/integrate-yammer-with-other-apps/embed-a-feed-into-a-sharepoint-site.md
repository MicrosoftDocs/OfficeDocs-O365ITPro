---
title: "Include a Yammer feed in a SharePoint page"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.service: yammer
ms.custom: Adm_Yammer
ms.collection: SPO_Content
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 4817d2fa-50f6-4f25-88a0-a312745768d4
description: "You can add a Yammer feed to a modern or classic SharePoint site page."
---

# Include a Yammer feed in a SharePoint page

To include a Yammer feed in a SharePoint page, your organization should have an active Yammer network (for example: http&#58;//www&#46;yammer&#46;com/contoso&#46;com). 

- For SharePoint Online, you can use the Yammer Conversations web part so that page viewers can engage in the conversation without leaving SharePoint.  The Yammer Conversations web part has the latest Yammer experiences including the ability to start a conversation with any type of post (Questions, Polls, Praise) and mark best answers directly from SharePoint. You can also use the Yammer Highlights web part to display recent conversations. However, the Highlights web part does not have all the latest Yammer experiences. 

- For SharePoint Server 2019 modern pages, you can use the Yammer Highlights web part (Classic mode) to add a group, user, topic, or Yammer home feed.

- For SharePoint Servers 2013 and 2016 and for classic pages in SharePoint Server 2019, you can use Yammer Embed within a script editor web part to add a group feed, user feed, topic feed, Yammer home feed, or an open graph object feed that adds a discussion about an object such as web page. 
  
## Add a Yammer feed to a page in SharePoint Online

>[!NOTE]
> The Yammer Conversations and Highlights web parts only work when the SharePoint site uses the original domain name, for example contoso.onmicrosoft.com, and are not supported when the SharePoint site uses a vanity domain name.

For instructions for how to use the Yammer Conversations or Yammer Highlights web part, see [Use a Yammer web part in a SharePoint Online page](https://support.office.com/article/a53cfa0c-3d09-42c8-a286-1038a81c59da). 

These web parts inherit the page theme, and are usable from mobile devices. 

## Add a Yammer feed to a modern page in SharePoint Server 2019

1. Go to Yammer in a browser, and go to the Yammer page you want to put in SharePoint: a group, person, topic, or the Yammer home page. Copy the URL. 

2. In SharePoint, go to the page you want to put the Yammer feed on, and click **Edit**.

3. Click + to add a new web part. 

4. Select the Yammer web part.

5. In the Yammer box on the right, paste the URL you copied in step 1 into the **Web address** box.

6. To change the display size, select an option in **Display size**. 

7. To publish your page, click **Publish**.

## Add a Yammer feed to a classic page in SharePoint Servers 2013, 2016, and 2019 
<a name="AddFeed"> </a>

There are three basic steps:

1. Add a script editor web part to your SharePoint page.

2. Copy and edit a simple script that identifies the type of feed you want and the Yammer network you are using.
    
3. Paste the script into the web part and publish your SharePoint page. 

When a Yammer feed is added using this method, the feed can't be viewed when using a mobile browser or if third-party cookies aren't enabled. For more information about browser support when using a Yammer feed in a script editor web part, see [Yammer Embed requirements](https://developer.yammer.com/docs/requirements).
    
### Step 1: Set up the web part 

1. In your SharePoint site, choose **Edit**.
    
2. On the ribbon, choose **Insert** \> **Web Part** and in the **Categories** list, select **Media and Content** \> **Script Editor**. 

3. In **Add part to:**, select where you want to add the web part, and then choose **Add**.   
    
4. Locate your new script editor web part, and choose **Edit Snippet**.
    
5. Paste the script you copied from Yammer into the script editor web part.
    
6. Choose **Insert**.
    
7. Save and publish the SharePoint page. You should see the Yammer Group conversation on the SharePoint page.

### Step 2: Copy and edit the script to use

The following procedures describe how to add a group feed, my feed, or page feed. For information about other feed types, see [Yammer Embed](https://go.microsoft.com/fwlink/?LinkID=524147). You can also use the Yammer Embed configuration tool to create the script to use. See [Add the Yammer Embed widget to a SharePoint page](https://go.microsoft.com/fwlink/?LinkID=525587) for how to use the configuration tool. 
  
 **Prepare the script for a group feed**
  
1. In Yammer, go to the group that you want to embed. Locate the **Access Options** section and select **Embed this group in your site**.
    
    ![Access options for Yammer group](../media/a0bdb091-2d21-4041-adaf-bb66da668c64.png)
  
2. Copy the script from the window.
   
     **Prepare the script for a my feed**
   
    1. Edit the following script to use your Yammer network instead of contoso.com, and then paste it into the script editor web part.
    
  ```
  <div id="embedded-my-feed" style="height:400px;width:500px;"></div> 
      <script type="text/javascript" src="https://c64.assets-yammer.com/assets/platform_embed.js"></script>
      <script 'type="text/javascript"> yam.connect.embedFeed({  
                container: '#embedded-my-feed',
                network: 'contoso.com'  });
      </script>
  
  ```

        > [!NOTE]
        > You can also change the height and width parameters to the height and width you prefer. 

     **Prepare the script for a page feed**
  
    1. Go to the page that you want to embed. Copy the URL to the page.
    
    2. Edit the following script to use your Yammer network instead of contoso.com and to use the URL to the page that you want to discuss.
    
  ```
  <div id="embedded-feed" style="height:400px;width:500px;"></div> 
  <script type="text/javascript" src="https://assets.yammer.com/assets/platform_embed.js"></script> 
  <script type="text/javascript"> yam.connect.embedFeed({
           container: "#embedded-feed", 
           network: "contoso.com", 
           feedType: "open-graph", 
           objectProperties: { url: "https://www.contoso.com/sample_page" , type: "page" } }); 
  </script>
  
  ```

 > [!NOTE]
 > You can also change the height and width parameters to the height and width you prefer. 

    This example shows an open graph feed for a web page, but you can create feeds for other open-graph objects. The list of valid object types is at [Schema \> Supported Object Types](https://go.microsoft.com/fwlink/?LinkId=525586). If you are interested in using the Yammer Embed widget to add Yammer feeds to your SharePoint pages, see [Add the Yammer Embed widget to a SharePoint page](https://go.microsoft.com/fwlink/?LinkId=525587).
    
### Step 3: Paste the script in, and publish the SharePoint page. 

- On the SharePoint page, paste in the script, and then click **Publish**.
    
   >[!NOTE]
>For the Highlights (Classic mode) and the Yammer embed script experiences, when you add a Yammer My Feed/Home feed to a SharePoint page, you'll see slightly different messages than the ones included in the Home feed available in Yammer web, desktop, or mobile. On the SharePoint page, users will see messages from all threads in groups they are a member of and all threads in the All Company group. In Yammer web, desktop, and mobile, users can select Discovery, All, or Following feeds, but these aren't available in SharePoint pages. The My Feed/Home feed type is closest to the All feed but doesn't include public posts in public groups the user doesn't belong to.  

 
>Yammer does not have to be the social collaboration tool for SharePoint in order to embed a Yammer feed, but if you want to make Yammer the primary social experience for SharePoint, see [Integrate Yammer with on-premises SharePoint environments](https://docs.microsoft.com/sharepoint/administration/integrate-yammer-with-on-premises-sharepoint-server-environments). 

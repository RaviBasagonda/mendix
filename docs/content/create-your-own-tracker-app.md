---
title: "Create your own Tracker app in a browser using Mendix Studio"
#category: "Apps"
#parent: "Mendix"
#menu_order: 10
#description: "Describes how to create an app in a browser using Mendix Studio."
#tags: ["studio", "apps", "create app", "how to"]
#If moving or renaming this doc file, implement a temporary redirect and let the respective team know they should update the URL in the product. See Mapping to Products for more details.
---

## 1 Introduction

This how-to explains how you can create your own Tracker app in a browser using Mendix Studio. The Tracker app can be used for keeping track of everything from
office supplies to warehouse stock.

This how-to assumes the following use case:

* You want to keep a track of parts that you use in your workshop to repair and maintain customer bikes 
* You have a warehouse where you keep the parts in a specific location allocated for each part
* You want to add a new part and edit the part details
* You want to control the stock

**This how-to will teach you how to do the following:**

* Create a Tracker app using an app template and start editing in Mendix Studio (see section [3](https://github.com/RaviBasagonda/mendix/blob/main/docs/content/create-your-own-tracker-app.md#3-creating-a-tracker-app-and-editing-in-mendix-studio))
* Create and configure an action card on the home page to open the parts list
* Create and configure a page to display the parts list with part attributes
* Create a new entity and add part attributes such as part name, code, stock, location, etc. This entity with part attributes acts as a data source for the pages you create.
* Create and configure buttons, pages, and microflows to add a new part, edit stock, and delete a part from the parts list
* Create functionalities such as search, sort, and filter for better user experience
* Publish the Tracker app

## 2 Prerequisites

Before starting this how-to, make sure you have completed the following prerequisites:

* Have a Mendix account. If you do not have a Mendix account, go to [Mendix.com](https://www.mendix.com/) and click **Start for free** to create an account.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/2/start-for-free.gif?raw=true)

## 3 Creating a Tracker App and Start Editing in Mendix Studio

To create and edit a Tracker app, follow these steps:

1. Sign in to your Mendix account.
2. Click **Create App**.
3. Scroll down to locate the **Tracker** app template, hover over the **Tracker** app template, and click **Select Template** > **Select This Template**.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/3/select-tracker-template.gif?raw=true)

5. Choose a name, background color, an icon for your app, and click **Create App**.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/3/choose-name-create-app.gif?raw=true)

Once the app is created, you will be directed to the Buzz space where you can share your app and start discussions related to your app.

6. Click **Edit in Studio**.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/3/edit-in-studio.gif)

Now the Home page of Tracker app opens in Mendix Studio for editing.

## 4 Creating and Configuring an Action Card on the Home Page

The user interface and user interaction elements of a page in your app can be created using **Widgets** and **Building Blocks** (set of widgets). Go to the **Toolbox** tab to access Widgets and Building Blocks and go to the **Properties** tab to configure a funtionality or an appearance of a widget.

For more information, refer [Pages](https://docs.mendix.com/studio/page-editor) and [Widgets](https://docs.mendix.com/studio/page-editor-widgets).

### 4.1 Creating an Action Card

To create an action card, follow these steps:

1. Go to the **Toolbox** tab and search for *cards*.
2. Choose an action card:
   * In the **Cards** section, click and grab the **Card Action** card, and drag and drop it at the bottom of the Home page.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/create-action-card.gif?raw=true)

### 4.2 Configuring an Action Card

To configure an action card, follow these steps:

1. Choose an icon:
   * Click the icon in the action card, go to the **Properties** tab > **General** section > **Icon**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/select-icon-action-card.gif?raw=true)
   
2. Choose a caption:
   * Click the caption in action card, go to the **Properties** tab > **General** section > **Caption**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-caption-action-card.gif?raw=true)
   
3. Choose an event:
   * Click the action card, go to the **Properties** tab > **Events** section > **On Click Action** and choose **Page**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-event.gif?raw=true)
   
4. Configure the event:
   * In the **Events** section, click the **Page** field.
   * In the **Select Page** window, click **New page**.
   * In the **Create new page** window, create a new page titled *Parts* and choose a **Layout**.
   * In the left pane, choose **Lists** > **List Default**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/configure-event.gif?raw=true)

## 4 Read More

* {Link 1}
* {Link2} – {an explanation when necessary especially if this is a third-party link}

{Make sure this section contains a bulleted list only with explanations where necessary. Do not just repeat cross-references you used throughout the document, but list useful supplementary links here.}

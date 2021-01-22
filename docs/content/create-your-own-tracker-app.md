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

* Create a Tracker app and start editing in Mendix Studio (see section [3](https://github.com/RaviBasagonda/mendix/blob/main/docs/content/create-your-own-tracker-app.md#3-creating-a-tracker-app-and-editing-in-mendix-studio))
* Configure an action card on the Home page to open the parts list
* Create a new page for displaying the parts list (see section [4](https://github.com/RaviBasagonda/mendix/blob/main/docs/content/create-your-own-tracker-app.md#4-configuring-an-action-card-and-creating-a-new-page-for-parts-list))
* Configure a new page
* Create an entity and add part attributes. This entity with part attributes acts as a data source for the pages you create.
* Create and configure buttons, pages, and microflows to add a new part, edit stock, and delete a part from the parts list
* Create features such as search, sort, and filter for better user experience
* Resolve errors, preview, and publish the Tracker app

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

Once the app is created, you will be directed to the app Buzz space, where you can share your app and start discussions related to your app.

6. Click **Edit in Studio**. The *Home* page of Tracker app opens in Mendix Studio for editing.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/3/edit-in-studio.gif)

## 4 Configuring an Action Card and Creating a New Page for the Parts List

The User Interface (UI) and user interaction elements of a page in your app can be configured using **Widgets** and **Building Blocks** (set of widgets). Go to the **Toolbox** tab to access the **Widgets** and **Building Blocks** and go to the **Properties** tab to configure an event or appearance of a widget. To get yourself familiarize with pages and widgets in Mendix Studio, refer [Pages](https://docs.mendix.com/studio/page-editor) and [Widgets](https://docs.mendix.com/studio/page-editor-widgets).

### 4.1 Configuring an Action Card on the Home Page

To configure an action card, follow these steps:

1. Choose an action card:
   * Go to the **Toolbox** tab, search for *cards*, and drag and drop the **Card Action** card at the bottom of the *Home* page.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/create-action-card.gif?raw=true)

3. Choose an icon for the action card:
   * Click the icon in the action card and go to the **Properties** tab > **General** section > **Icon**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/select-icon-action-card.gif?raw=true)
   
4. Choose a caption for the action card:
   * Click the caption in action card and go to the **Properties** tab > **General** section > **Caption**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-caption-action-card.gif?raw=true)
   
5. Choose an event for the click action:
   * Click the action card, go to the **Properties** tab > **Events** section > **On Click Action** field, and choose **Page**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-event.gif?raw=true)
   
   Choosing the **Page** event will set an event to open the *Parts* page you will create and select in the next step. 
   
### 4.2 Creating the Parts Page for Parts List

The Mendix Studio has ready-made page templates for creating app pages such as dashboards, forms, lists, etc. You can use a page template and configure it accoording to your needs and design.

To create the *Parts* page, follow these steps:

1. In the **Events** section, click the **Page** field to select a page.
2. In the **Select Page** window, click **New Page**.
3. In the **Create new page** window, create a new page titled *Parts*, and choose a **Layout**.
4. In the left pane, choose **Lists** > **List Default**. A new page titled *Parts* will be created.
   
## 5 Configuring the Parts Page UI and User Interaction Elements

### 5.1 Configuring the Parts Page UI

To configure the *Parts* page UI, follow these steps:

1. Open the *Parts* page (refer [Pages](https://docs.mendix.com/studio/page-editor)).
2. Delete unnecessary UI elements:
   * Click an UI element and press <kbd>Delete</kbd> or click **Delete**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/delete-elements.gif?raw=true)
   
3. Set the width of page layout, if necessary:
   * Click the **Layout Grid** and choose **Full Width** or **Fixed Width**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/adjust-width-layout-grid.gif?raw=true)
   
4. Edit texts or button captions, if necessary:
   * Double-click a text or button caption to edit it.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/edit-texts-button-captions.gif?raw=true)
   
5. Add or delete rows or columns for rearranging UI elements, if necessary:
   * Click an UI element and go to the breadcrumb bar displayed at the left bottom corner.
   * Click **Row** or **Column** to access the **Add Row** and **Add Column** buttons.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/add-rows-columns.gif?raw=true)
   
6. Rearrange the **New** button and configure the spacing or alignment, if necessary:
   * Drag and drop the **New** button inside a column next to the title.
   * Go to the **Properties** tab > **Design** section to configure the spacing or alignment.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/rearrange-button.gif?raw=true)

7. Add UI elements for deleting, searching, sorting, and filtering parts from the parts list:
   * Copy and paste an existing button to create the delete button and go to the **Properties** tab to configure the design, appearance, and spacing.
   * Add a column below the page title, go to the **Toolbox** tab, search for *search* widget, and drag and drop the **Text box search** widget inside the column.
   * Add a column below the search box, go to the **Toolbox** tab, search for *sort* widget, and drag and drop the **Drop down sort** widget inside the column.
   * Add a column right to the sort box, go to the **Toolbox** tab, search for *filter* widget, and drag and drop the **Drop down filter** widget inside the column.
   
6. Add a back button at the top left corner to go back to your app *Home* page:
   * Copy and paste an existing button, change the caption as *Back*, drag and drop it inside the row at top left corner, and go to the **Properties** tab to configure the design, appearance, and spacing.
   
The configured *Parts* page may look similar to the following UI page:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/parts-page.png?raw=true)
   
### 5.2 Configuring the User Interaction Elements

The user interaction elements such as new, edit, delete, search, sort, and filter in your app will not work without action events and a data source to interact with and feed data to the *Parts* page. The data source for a page can be created by creating an entity with attributes in the **Domain Models** module in the Mendix Studio. To get yourself familiarize with domain models, entity, and attributes, refer [Domain Model](https://docs.mendix.com/studio/domain-models).

#### 5.2.1 Creating the Parts Entity and Attributes

To create the *Parts* entity and attributes, follow these steps:

1. Go to the **Domain Models** window in Mendix Studio: 
   * Click the **Domain Models** icon in the left menu bar and select **AssetManager**.
   
2. Create an entity named *Parts*:
   * Go to the **Toolbox** tab, drag and drop **Entity** inside the main window, and name it **Parts**.

3. Create and configure attributes:
   * Click **New attribute** to create the following part attributes: *Name*, *Code*, *Stock*, *SafetyStock*, *OptimumStock*, *Location*, and *Notes*.
   
   {{% alert type="info" %}} The name of an attribute should start with a letter and can only contain letters, digits, and underscores. {{% /alert %}}
   
   * Click an attribute and go to the **Properties** tab to configure the attribute properties.
   
4. Ensure that the *Parts* entity is persistable (refer [Persistability](https://docs.mendix.com/refguide/persistability)): 
   * Click at the top of **Parts** entity, go to the **Properties** tab, and make sure the **Persistable** switch is turned on.
   
The created *Parts* entity may look similar to the following entity:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/parts-entity.png?raw=true)

#### 5.2.2 Configuring the Action Events for User Interaction

## 4 Read More

* {Link 1}
* {Link2} – {an explanation when necessary especially if this is a third-party link}

{Make sure this section contains a bulleted list only with explanations where necessary. Do not just repeat cross-references you used throughout the document, but list useful supplementary links here.}

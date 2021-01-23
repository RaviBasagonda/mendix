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
3. Scroll down to locate the *Tracker* app template, hover the cursor over it , and click **Select Template** > **Select This Template**.
5. Choose a name, background color, an icon for your app, and click **Create App**. Once the app is created, the app *Buzz* space will open.
6. In the app *Buzz* space, click **Edit in Studio**. The *Home* page of Tracker app will open in Mendix Studio for editing.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/3/edit-in-studio.gif)

## 4 Configuring an Action Card and Creating a New Page for the Parts List

You can configure the User Interface (UI) and user interaction elements of a page in your app using **Widgets** and **Building Blocks** (set of widgets). Go to the **Toolbox** tab to access the **Widgets** and **Building Blocks** and go to the **Properties** tab to configure an event or appearance of a widget. To get yourself familiarize with *Pages* and *Widgets* in the Mendix Studio, refer [Pages](https://docs.mendix.com/studio-how-to/pages) and [Widgets](https://docs.mendix.com/studio/page-editor-widgets).

### 4.1 Configuring an Action Card on the Home Page

To configure an action card, follow these steps:

1. Choose an action card:
   * Go to the **Toolbox** tab > search for *cards* > drag and drop the **Card Action** card at the bottom of the *Home* page.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/create-action-card.gif?raw=true)

3. Choose an icon for the action card:
   * Click the icon in the action card and go to the **Properties** tab > **General** section > **Icon**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/select-icon-action-card.gif?raw=true)
   
4. Choose a caption for the action card:
   * Click the caption in action card and go to the **Properties** tab > **General** section > **Caption**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-caption-action-card.gif?raw=true)
   
5. Choose an event for the click action:
   * Click the action card, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Page**. Choosing the **Page** event will set an event to open the *Parts* page you will create and select in the next step.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-event.gif?raw=true) 
   
### 4.2 Creating a Page for the Parts List

The Mendix Studio has ready-made page templates for creating app pages such as dashboards, forms, lists, etc. You can use a page template and configure it accoording to your needs and design.

To create a page for displaying the parts list, follow these steps:

1. In the **Events** section, go to **Page** > click **Select page** to select a page.
2. In the **Select Page** pop-up window, click **New Page**.
3. In the **Create new page** pop-up window, create a new page titled *Parts*, and choose a **Layout**.
4. In the left pane, choose **Lists** > **List Default**, and click **Create**. A new page titled *Parts* will be created.
   
## 5 Configuring UI Elements of a Page

To configure the UI elements of a page, follow these steps:

1. Go to the **Pages** window in Mendix Studio:
   * Click the **Pages** icon in the left menu bar and select **Parts**.

2. Delete unnecessary UI elements:
   * Click an UI element and press <kbd>Delete</kbd> or click **Delete**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/delete-elements.gif?raw=true)
   
3. Set the width of page layout, if necessary:
   * Click the **Layout Grid**, go to the **Properties** tab > **General** section > choose **Full Width** or **Fixed Width**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/adjust-width-layout-grid.gif?raw=true)
   
4. Edit texts or button captions, if necessary:
   * Double-click a text or button caption to edit it.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/edit-texts-button-captions.gif?raw=true)
   
5. Add or delete rows or columns for rearranging UI elements, if necessary:<br/>

   a. Click an UI element and go to the breadcrumb bar displayed at the left bottom corner.<br/>
   
   b. Click **Row** or **Column** to access the **Add Row** and **Add Column** buttons.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/add-rows-columns.gif?raw=true)
   
6. Rearrange a button and configure the spacing or alignment, if necessary:<br/>

   a. Drag and drop the **New** button inside a column next to the page title.<br/>
   
   b. Go to the **Properties** tab > **Design** section to configure the spacing or alignment.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/rearrange-button.gif?raw=true)

7. Add UI elements for deleting, searching, sorting, and filtering parts from the parts list:<br/>

   a. Copy and paste an existing button, rename it as *Delete*, and go to the **Properties** tab to configure the design, appearance, and spacing.<br/>
   
   b. Add a column below the page title, go to the **Toolbox** tab > search for *search* widget > drag and drop the **Text box search** widget inside the column.<br/>
   
   c. Add a column below the search box, go to the **Toolbox** tab > search for *sort* widge > drag and drop the **Drop down sort** widget inside the column.<br/>
   
   d. Add a column right to the sort box, go to the **Toolbox** tab > search for *filter* widget > drag and drop the **Drop down filter** widget inside the column.
   
8. Add a back button for going back to the app *Home* page:<br/>

   a. Copy and paste an existing button and rename it as *Back*.<br/>
   
   b. Drag and drop it inside the row at top left corner.<br/>
   
   c. Go to the **Properties** tab to configure the design, appearance, and spacing.
   
The configured page titled *Parts* may look similar to the following UI page:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/parts-page.png?raw=true)
   
## 6 Configuring the User Interaction Elements of a Page

The user interaction elements such as new, edit, delete, search, sort, and filter in your app will not respond without action events and a data source to interact with and feed data to a page. The data source for a page can be created by creating an entity with attributes in the *Domain Models* window in the Mendix Studio. To get yourself familiarize with *Domain Models*, *Entity*, and *Attributes*, refer [Domain Model](https://docs.mendix.com/studio/domain-models).

### 6.1 Creating an Entity and Attributes

To create an entity and attributes, follow these steps:

1. Go to the **Domain Models** window in Mendix Studio:
   * Click the **Domain Models** icon in the left menu bar and select **AssetManager**.
   
2. Create an entity named *Parts*:
   * Go to the **Toolbox** tab > drag and drop **Entity** inside the main window, and name it **Parts**.

3. Create and configure attributes:

   a. Click **New attribute** to create the following part attributes: *Name*, *Code*, *Stock*, *SafetyStock*, *OptimumStock*, *Location*, and *Notes*.
   
   {{% alert type="info" %}}
   The name of an attribute should start with a letter and can only contain letters, digits, and underscores.
   {{% /alert %}}
   
   b. Click an attribute and go to the **Properties** tab to configure the properties.
   
4. Ensure that the *Parts* entity is persistable (refer [Persistability](https://docs.mendix.com/refguide/persistability)):
   * Click at the top of **Parts** entity box, go to the **Properties** tab, and make sure the **Persistable** switch is turned on.
   
The created entity named *Parts* may look similar to the following entity:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/parts-entity.png?raw=true)

### 6.2 Configuring the Action Events for User Interaction

#### 6.2.1 Configuring an Event to Add a New Part to the Parts List:

To configure an event to add a new part to the parts list, follow these steps:

1. Set an event:<br/>

   a. Click the **New** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Page**.<br/>
   
   b. In the **Events** section, turn the **Create Object** switch on. This event sets an action to create and add a new object (part) to the parts list.

2. Choose an entity for the parts data and create a page to open and fill the part details:<br/>

   a. In the **Events** section, go to **Entity** > click **Select entity** > choose **Parts**.<br/>
   
   c. Go to **Page** > click **Select page** to select a page.<br/>
   
   d. In the **Select Page** pop-up window, click **New Page**.<br/>
   
   e. In the **Create new page** pop-up window, create a new page titled *Part details*, and choose **PopupLayout** from the **Layout** drop-down list.<br/>
   
   f. Ensure that the checkbox *Pre-fill page contents based on the Parts entity* is selected. This will pre-fill the page contents with part attributes you have created in the *Parts* entity.<br/>
   
   f. Choose **Form Horizontal** and click **Create**. A new pop-up page (form) titled *Part details* will be created.

3. Configure the contents inside the *Part details* page:<br/>

   a. Ensure that the data source for contents inside the page is set as **Context**:<br/>
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/part-details-page-data-source.gif?raw=true)
   
   b. Set the **Name** text box as *Required* to make the part name attribute as necessary to add a part to the parts list:<br/>
   
      * Click the **Name** text box, go to the **Properties** tab > **Input Validation** section > **Validation Type** > choose **Required**.<br/>
      
   c. Configure other properties such as design, appearance, spacing, and alignment, if necessary.
   
4. Ensure that event for the **Cancel** button is set to cancel the changes made to the page while adding or editing a part details:<br/>

   a. Go to the **Properties** tab > **Events** section > **On Click Action** > choose **More**.<br/>
   
   b. Go to **Action** > choose **Cancel Changes** from the drop-down list.
      
5. Configure the **Save** button to display a save confirmation message:<br/>

   a. Click the **Save** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Microflow**.<br/>
   
   c. In the **Events** section, go to **Microflow** > click **Select microflow**.<br/>
   
   d. In the **Select Microflow** pop-up window, click **New Microflow**.<br/>
   
   e. In the **Create new microflow** pop-up window, create a new microflow named *AddEditPart* and click **Create**. The *AddEditPart* microflow will open in the **Microflows** window in Mendix Studio.
   
#### 6.2.2 Configuring a Microflow

Your app will not function without logic and data activities. The logical events such as start, end, decision, merge, and activities such as create, change, retrieve can be created by creating visualized flow diagrams called *Microflows* in the Mendix Studio. To get yourself familiarize with *Microflows*, refer [Microflows](https://docs.mendix.com/studio-how-to/microflows).

{{% alert type="info" %}}
The primary objective of creating this microflow is to change (edit) the part details and display the *Part saved successfully* confirmation message to the user. As this microflow contains the save confirmation message, it can also be used as event to display the save confirmation message while adding a new part to the parts list. 
{{% /alert %}}

To configure a microflow, follow these steps:

1. Go to the **Microflows** window in Mendix Studio:
   * Click the **Microflows** icon in the left menu bar and select **AddEditPart**.
   
2. Create and configure a change object activity for editing and saving the part details:<br/>

   a. Go to the **Toolbox** tab > **Object Activities** section > drag and drop the **Change Object** activity in microflow between the start (green dot) and end (red dot) events.<br/>
   
   b. In the microflow diagram, click **Change object** and go to the **Properties** tab > **Data Source** section > **Object** > drop-down **Select object** > choose **Parts**.<br/>
   
   c. In the **Data Source** section, go to **Change Members** > click **Add New Value**.<br/>
   
   d. In the **Change value** pop-up window, select an attribute to be changed, and click **Add**. <br/>
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/microflow-add-new-value.gif?raw=true)<br/>
   
   e. Repeat the steps *c* and *d* till you add all the attributes you may want to change while editing the part details.<br/>
   
   f. Go to the **Properties** tab > **Behavior** section > **Commit** and make sure to choose **Yes**, and turn the **Refresh in Client** switch on. This behavior sets an event to commit and display the changes in parts list.

3. Create a close page activity for closing the page after saving the changes:
   * Go to the **Toolbox** tab > **Client Activities** section > drag and drop the **Close Page** activity in microflow after the **Change object** activity.
   
4. Create and configure a show message activity for displaying the save confirmation message:<br/>

   a. Go to the **Toolbox** tab > **Client Activities** section > drag and drop the **Show Message** activity in microflow after the **Close Page** activity.<br/>
   
   b. In the microflow diagram, click **Show Message** and go to the **Properties** tab > **Data Source** section > **Template** > enter *Part saved successfully* and turn the **Blocking** switch on. This microflow sets an event to display the save confirmation message and block the user to *OK* the message before interacting with other user interaction element.

The configured microflow may look similar to the following microflow:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/microflow.png?raw=true)
   
   
## 4 Read More

* {Link 1}
* {Link2} – {an explanation when necessary especially if this is a third-party link}

{Make sure this section contains a bulleted list only with explanations where necessary. Do not just repeat cross-references you used throughout the document, but list useful supplementary links here.}

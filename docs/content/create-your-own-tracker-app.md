---
title: "Create your own Tracker app using Mendix Studio"
category: "Apps"
parent: "Mendix"
menu_order: 10
description: "Describes how to create an app in a browser using Mendix Studio."
tags: ["studio", "apps", "create tracker app", "how to"]
#If moving or renaming this doc file, implement a temporary redirect and let the respective team know they should update the URL in the product. See Mapping to Products for more details.
---

## 1 Introduction

This how-to explains how you can create your own Tracker app using Mendix Studio. The Tracker app can be used for keeping track of everything from
office supplies to warehouse stock.

This how-to assumes the following business use case:

* You want to keep a track of parts that you use in your workshop to repair and maintain customer bikes 
* You have a warehouse where you keep the parts in a specific location allocated for each part
* You want to add a new part and edit the stock and part details
* You want to control the parts stock via an app

**This how-to will teach you how to do the following:**

* Create the Tracker app and start editing in Mendix Studio
* Configure the app *Home* page to open the parts list
* Create new *Parts* page to display the parts list
* Configure the user interface (UI) of *Parts* page 
* Configure the user interaction elements of *Parts* page
  * Create an entity and add attributes. This entity with attributes acts as a data source for the pages and events you create.
  * Create and configure buttons, pages, and microflows to add a new part, edit stock, and delete a part from the parts list
  * Create features such as search, sort, and filter to control the parts stock
* Fix an error in your app

## 2 Prerequisites

Before starting this how-to, make sure that you have completed the following prerequisites:

* Have a Mendix account. If you do not have a Mendix account, go to [Mendix.com](https://www.mendix.com/) and click **Start for free** to create an account.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/2/start-for-free.gif?raw=true)

## 3 Creating the Tracker App and Start Editing in Mendix Studio

To create and edit the Tracker app, follow these steps:

1. Sign in to your Mendix account.
2. Click **Create App**.
3. Scroll down to locate the *Tracker* app template, hover the cursor over it , and click **Select Template** > **Select This Template**.
5. Enter the name *Tracker*, choose a background color, an icon for your app, and click **Create App**. Once the app is created, the app *Buzz* space will open.
6. In the app *Buzz* space, click **Edit in Studio**. The *Home* page of Tracker app will open in Mendix Studio for editing.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/3/edit-in-studio.gif)

## 4 Configuring the Home Page and Creating the Parts Page

You can configure the user interface (UI) and user interaction elements of a page in your app using **Widgets** and **Building Blocks** (set of widgets). Go to the **Toolbox** tab to access the **Widgets** and **Building Blocks** and go to the **Properties** tab to configure an event or appearance of a widget. To get yourself familiarize with *Pages* and *Widgets* in Mendix Studio, refer [Pages](https://docs.mendix.com/studio-how-to/pages) and [Widgets](https://docs.mendix.com/studio/page-editor-widgets).

To configure the *Home* page and create the *Parts* page, follow these steps:

1. In the *Home* page, create an action card:
   * Go to the **Toolbox** tab > search for *cards* > drag and drop the **Card Action** card at the bottom of the *Home* page.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/create-action-card.gif?raw=true)

3. Choose an icon for the action card:
   * Select the icon in the action card and go to the **Properties** tab > **General** section > **Icon**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/select-icon-action-card.gif?raw=true)
   
4. Choose a caption for the action card:
   * Select the **Open Page** caption in the action card and go to the **Properties** tab > **General** section > **Caption** > enter *Parts*.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-caption-action-card.gif?raw=true)
   
5. Choose an event for the click action:
   * Select the action card, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Page**. This event sets an action to open the *Parts* page that you will create in the next step.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/4/4.2/choose-event.gif?raw=true)

6. Create the *Parts* page:<br/>

   a. In the **Events** section, go to **Page** > click **Select page**.<br/>
   
   b. In the **Select Page** pop-up window, click **New Page**.<br/>
   
   c. In the **Create new page** pop-up window, do the following:
      * **Title**  - enter *Parts*
      * **Layout** - choose **Atlas_Default**
      * In the left pane, choose **Lists** > **List Default**
      * Click **Create**
   
## 5 Configuring the UI of Parts Page

To configure the UI of *Parts* page, follow these steps:

1. Open the *Parts* page:
   * Click the **Pages** icon in the left menu bar and select **Parts**.

2. Delete unnecessary UI elements:
   * Select an UI element and press <kbd>Delete</kbd> or click **Delete**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/delete-elements.gif?raw=true)
   
3. Set the width of page layout, if necessary:
   * Select the **Layout Grid**, go to the **Properties** tab > **General** section > choose **Full Width** or **Fixed Width**.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/adjust-width-layout-grid.gif?raw=true)
   
4. Edit texts or button captions, if necessary:
   * Double-click a text or button caption to edit it.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/edit-texts-button-captions.gif?raw=true)
   
5. Add or delete rows or columns for rearranging the UI elements, if necessary:<br/>

   a. Select an UI element and go to the breadcrumb bar displayed at the left bottom corner.<br/>
   
   b. Click **Row** or **Column** to access the **Add Row** and **Add Column** buttons.<br/>
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/add-rows-columns.gif?raw=true)
   
6. Rearrange buttons and configure the spacing or alignment, if necessary:<br/>

   a. Drag and drop the **New** button inside a column next to the page title.<br/>
   
   b. Go to the **Properties** tab > **Design** section to configure the spacing or alignment.
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/rearrange-button.gif?raw=true)

7. Create user interaction elements for deleting, searching, sorting, and filtering parts from the parts list:<br/>

   a. Copy and paste an existing button, rename it as *Delete*, and go to the **Properties** tab to configure the design, appearance, and spacing.<br/>
   
   b. Add a column below the page title, go to the **Toolbox** tab > search for *search* widget > drag and drop the **Text box search** widget inside the column.<br/>
   
   c. Add a column below the search box, go to the **Toolbox** tab > search for *sort* widge > drag and drop the **Drop down sort** widget inside the column.<br/>
   
   d. Add a column right to the sort box, go to the **Toolbox** tab > search for *filter* widget > drag and drop the **Drop down filter** widget inside the column.
   
8. Create a back button for going back to the *Home* page:<br/>

   a. Copy and paste an existing button and rename it as *Back*.<br/>
   
   b. Drag and drop it inside the row at top left corner and configure the design, appearance, and spacing, if necessary.<br/>
   
The configured UI of *Parts* page may look similar to the following UI page:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/parts-page.png?raw=true)
   
## 6 Configuring the User Interaction Elements of Parts Page

The user interaction elements such as new, edit, delete, search, sort, and filter in your app will not respond without action events and a data source to interact with and feed data to a page. The data source for a page can be created by creating an entity with attributes in the *Domain Models* window in Mendix Studio. To get yourself familiarize with *Domain Models*, *Entity*, and *Attributes*, refer [Domain Model](https://docs.mendix.com/studio/domain-models).

### 6.1 Creating and Configuring an Entity and Attributes

To create an entity and attributes, follow these steps:

1. Go to the **Domain Models** window in Mendix Studio:
   * Click the **Domain Models** icon in the left menu bar and select **AssetManager**.
   
2. Create an entity named *Parts*:
   * Go to the **Toolbox** tab > drag and drop **Entity** inside the main window, name it **Parts**.

3. Create and configure attributes:

   a. Select the **Parts** entity, click **New attribute**, and create the following part attributes: *Name*, *Code*, *Stock*, *SafetyStock*, *OptimumStock*, *Location*, and *Notes*.
   
   {{% alert type="info" %}}
   The name of an attribute should start with a letter and can only contain letters, digits, and underscores.
   {{% /alert %}}
   
   b. Select an attribute and go to the **Properties** tab to configure the properties.
   
4. Ensure that the *Parts* entity is persistable (refer [Persistability](https://docs.mendix.com/refguide/persistability)):
   * Click at the top of **Parts** entity box, go to the **Properties** tab, and make sure the **Persistable** switch is turned on.
   
The created entity named *Parts* may look similar to the following entity:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/5/parts-entity.png?raw=true)

### 6.2 Configuring the New Button

To configure the *New* button for adding a new part to the parts list, follow these steps:

1. Set an event to open a page and create a new part in the part database:<br/>

   a. Click the **New** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Page**.<br/>
   
   b. In the **Events** section, turn the **Create Object** switch on. This event sets an action to create and add a new object (part) to the parts list.

2. Choose an entity for sourcing the parts data:<br/>

   a. In the **Events** section, go to **Entity** > click **Select entity**.<br/>
   
   b. In the **Select Entity** pop-up window, choose the **Parts** entity.

3. Create a page to open and fill the part details:<br/>
   
   a. In the **Events** section, go to **Page** > click **Select page**.<br/>
   
   b. In the **Select Page** pop-up window, click **New Page**.<br/>
   
   c. In the **Create new page** pop-up window, do the following:
      * **Title**  - enter *Part details*
      * **Layout** - choose **PopupLayout**
      * Ensure that the checkbox *Pre-fill page contents based on the Parts entity* is selected. This will pre-fill the page contents with part attributes that you have created in the *Parts* entity.
      * **Forms** - choose **Form Horizontal**
      * Click **Create**

4. Configure the user interaction elements inside the *Part details* page:<br/>

   a. Ensure that the data source for contents inside the page is set to **Context**:<br/>
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/part-details-page-data-source.gif?raw=true)<br/>
   
   b. Set the **Name** text box as *Required* to make the part name as necessary to add a part to the parts list:<br/>
   
      * Select the **Name** text box, go to the **Properties** tab > **Input Validation** section > **Validation Type** > choose **Required**.<br/>
      
   c. Configure other properties such as design, appearance, spacing, and alignment, if necessary.
   
5. Ensure that event for the **Cancel** button is set to cancel the changes made to the page while adding or editing a part detail:<br/>

   a. Go to the **Properties** tab > **Events** section > **On Click Action** > choose **More**.<br/>
   
   b. In the **Events** section, go to **Action** > choose **Cancel Changes** from the drop-down list.
      
6. Configure the **Save** button to display a save confirmation message:<br/>

   a. Click the **Save** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Microflow**.<br/>
   
   b. In the **Events** section, go to **Microflow** > click **Select microflow**.<br/>
   
   c. In the **Select Microflow** pop-up window, click **New Microflow**.<br/>
   
   d. In the **Create new microflow** pop-up window, do the following:
      * **Name** - enter *AddEditPart*
      * Click **Create**
   
### 6.3 Configuring a Microflow

Your app will not function without logic and data activities. The logical events such as start, end, decision, merge, and activities such as create, change, retrieve can be created by creating visualized flow diagrams called *Microflows* in the Mendix Studio. To get yourself familiarize with *Microflows*, refer [Microflows](https://docs.mendix.com/studio-how-to/microflows).

{{% alert type="info" %}}
The primary objective of creating this microflow is to change (edit) the part details and display the *Part saved successfully* confirmation message. As this microflow contains a save confirmation message, it can also be used as event to display the save confirmation message while adding a new part to the parts list. 
{{% /alert %}}

To configure the *AddEditPart* microflow, follow these steps:

1. Open the *AddEditPart* microflow:
   * Click the **Microflows** icon in the left menu bar and select **AddEditPart**.
   
2. Create and configure a change object activity for editing and saving the part details:<br/>

   a. Go to the **Toolbox** tab > **Object Activities** section > drag and drop the **Change Object** activity to the microflow between the start (green dot) and end (red dot) events.<br/>
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/add-change-object-in-microflow.gif?raw=true)<br/>
   
   b. In the microflow diagram, select the **Change object** activity and go to the **Properties** tab > **Data Source** section > **Object** > drop-down **Select object** > choose **Parts**.<br/>
   
   c. In the **Data Source** section, go to **Change Members** > click **Add New Value**.<br/>
   
   d. In the **Change value** pop-up window, select an attribute to be changed, and click **Add**. <br/>
   
   ![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/microflow-add-new-value.gif?raw=true)<br/>
   
   e. Repeat steps from c to d till you add all the attributes you may want to change while editing the part details.<br/>
   
   f. Go to the **Properties** tab > **Behavior** section > **Commit** and make sure to choose **Yes**, and turn the **Refresh in Client** switch on. This behavior sets an event to commit and display the changes in parts list.

3. Create a close page activity for closing the *Part details* page after saving the changes:
   * Go to the **Toolbox** tab > **Client Activities** section > drag and drop the **Close Page** activity to the microflow after the **Change object** activity.
   
4. Create and configure a show message activity for displaying a save confirmation message:<br/>

   a. Go to the **Toolbox** tab > **Client Activities** section > drag and drop the **Show Message** activity to the microflow after the **Close Page** activity.<br/>
   
   b. In the microflow diagram, select the **Show Message** activity and go to the **Properties** tab > **Data Source** section > **Template** > enter *Part saved successfully* and turn the **Blocking** switch on. This microflow sets an event to display the save confirmation message and block you from interacting with other user interaction elements on the *Parts* page.

The configured microflow may look similar to the following microflow. To understand more about the parameters and events displayed in the following microflow, refer [Microflows](https://docs.mendix.com/studio/microflows):

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/microflow.png?raw=true)

### 6.4 Configuring the Edit Button

To configure the *Edit* button for opening the *Part details* page and editing, follow these steps:

1. Click the **Edit** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Page**.<br/>

{{% alert type="warning" %}}
In the **Events** section, do not turn the **Create Object** switch on and select the *Parts* entity. This event will set an action to create and add a new object (part) to the parts list, rather than changing the existing part detail you may edit from the parts list.
{{% /alert %}}<br/>

2. In the **Events** section, go to **Page** > click **Select page**.<br/>

3. In the **Select Page** pop-up window, choose the **Part details** page.<br/>

### 6.5 Configuring the Delete Button

To configure the *Delete* button for deleting a part from the parts list, follow these steps:

1. Click the **Delete** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **More**.<br/>

2. In the **Events** section, go to **Action** > choose **Delete Object** from the drop-down list. This event sets an action to display a dialogue box prompting you to confirm the delete action.

### 6.6 Configuring the Search Feature

To configure the search feature for searching a part from the parts list, follow these steps:

1. Choose an entity:<br/>

   a. Select the search box, go to the **Properties** tab > **General** section > **List View With Entity** > click **Select entity**.<br/>
   
   b. In the **Select Entity** pop-up window, choose the **Parts** entity.
   
2. Choose the part attribute that you want to search using the searh box:<br/>

   a. Go to the **Properties** tab > **General** section > **Search Attributes** > click **Add**.<br/>
   
   b. In the **Add Object Property** pop-up window, click **Select attribute**.<br/>
   
   c. In the **Select Attribute** pop-up window, choose **Name** and click **Select**.

3. Choose a placeholder to hint that the part name can be used for searching:
   * Go to the **Properties** tab > **General** section > **Placeholder** > enter *Search part*.
   
### 6.7 Configuring the Sort Feature

To configure the sort feature for sorting parts list, follow these steps:

1. Choose an entity:<br/>

   a. Select the sort box, go to the **Properties** tab > **General** section > **List View With Entity** > click **Select entity**.<br/>
   
   b. In the **Select Entity** pop-up window, choose the **Parts** entity.
   
2. Choose the sort options that you want to add to the sort drop-down list:<br/>

   a. Go to the **Properties** tab > **General** section > **Sort Options** > click **Add**.<br/>
   
   b. In the **Add Object Property** pop-up window, do the following: 
      * **Caption** - enter *Sort by name*
      * **Attribute** - choose **Name**
      * **Sort Order** - choose **Ascending**
      * **Default Selected** - turn the switch on
      * Click **Done**
   
   c. Repeat step a and in the **Add Object Property** pop-up window, do the following:
      * **Caption** - enter *Sort by stock*
      * **Attribute** - choose **Stock**
      * **Sort Order** - choose **Ascending**
      * Click **Done**

### 6.8 Configuring the Filter Feature

To configure the filter feature for filtering parts from the list, follow these steps:

1. Choose an entity:<br/>

   a. Select the filter box, go to the **Properties** tab > **General** section > **List View With Entity** > click **Select entity**.<br/>
   
   b. In the **Select Entity** pop-up window, choose **Parts**.
   
2. Choose the filter options that you want to add to the filter drop-down list:<br/>

   a. Go to the **Properties** tab > **General** section > **Filter Options** > click **Add**.<br/>
   
   b. In the **Add Object Property** pop-up window, do the following: 
      * **Caption** - enter *Filter none*
      * **Filter** - choose **None**
      * **Selected by Default** - turn the switch on
      * Click **Done**
   
   c. Repeat step a and in the **Add Object Property** pop-up window, do the following:
      * **Caption** - enter *Filter empty stock*
      * **Filter** - choose **XPath**
      * **Attribute** - choose **Stock**
      * **XPath Constraint** - add condition where attribute value of **Stock** is equal to **0**.
      * Click **Done**
      
   d. Repeat step a and in the **Add Object Property** pop-up window, do the following:
      * **Caption** - enter *Filter stock reached safety stock*
      * **Filter** - choose **XPath**
      * **Attribute** - choose **Stock**
      * **XPath Constraint** - add condition where attribute value of **Stock** is less than or equal to attribute value of **SafetyStock**.
      * Click **Done**
      
### 6.9 Configuring the Contents of Parts List

To configure the contents of parts list for displaying the part attributes, follow these steps:

1. In the parts list, select the **Name** text, go to the **Properties** tab > **General** section > **Content** > delete the *Name* text > click **Add attribute**.<br/>
   
2. In the **Select Attribute** pop-up window, choose the **Name** attribute.<br/>
   
3. Repeat steps from 1 to 2 and choose the **Stock** attribute.<br/>

### 6.10 Configuring the Back Button

To configure the back button for going back to the *Home* page, follow these steps:

1. Click the **Back** button, go to the **Properties** tab > **Events** section > **On Click Action** > choose **Page** > click **Select page**.<br/>
   
2. In the **Select Page** pop-up window, choose the **Home** page.<br/>

Now the configured *Parts* page may look similar to the following UI page:

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/6/parts-page-complete.png?raw=true)

## 7 Fixing an Error Message

You cannot preview and publish your app without fixing the error messages. If your app has errors, the Mendix Studio displays the number of errors in the red colored **Checks** button located in the header bar at top right corner.

To fix an error message, follow these steps:

1. In Mendix Studio, go to the header bar and click **Checks**. The error messages displays in the bottom pane.

![](https://github.com/RaviBasagonda/mendix/blob/main/docs/images/7/error-messages.gif?raw=true)

2. Read the error message, identify the document and element to understand the error.

3. Click the error message to locate it.

Now that all the UI pages, user interaction elements are configured, and the error messages have been fixed, your [Tracker](https://tw1020-sandbox.mxapps.io/index.html) app is ready for previewing and publishing.

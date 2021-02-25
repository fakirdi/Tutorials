---
title: Create an SAP Fiori Elements Application
description: Instead of using the preview mode in ABAP Development Tools you will now create an SAP Fiori elements application based on the RAP backend service (the ABAP RESTful Application Programming Model) created in the previous chapters.
auto_validation: true
time: 20
tags: [products>sap-fiori-elements, products>sap-fiori-tools, tutorial>beginner, products>sap-fiori, products>sap-business-application-studio, products>sap-business-technology-platform]
primary_tag: products>sap-fiori
---

## Prerequisites
- You need a trial account on SAP Cloud Platform. If you don't have one, follow the instructions in: [Get a Free Trial Account on SAP Cloud Platform](hcp-create-trial-account).
- Ensure that you have started SAP Business Application Studio in your SAP Cloud Platform trial account. For detailed instructions: [Set Up SAP Business Application Studio for Development](appstudio-onboarding).
- Ensure that you have finished all steps in previous tutorial: [Refine the Object Page with Additional Annotations](fiori-tools-rap-modify-object-page).

## Details
### You will learn
  - How to set up SAP Business Application Studio for SAP Fiori elements application development
  - How to create a project connecting to the service needed for generating your sample application
  - How to modify application to get Flexible Column Layout and to activate Initial Load of data

For more information about the SAP ABAP RESTful Application Programming Model, refer to the documentation pages of [Get to Know the ABAP RESTful Application Programming Model](abap-environment-restful-programming-model).

---

[ACCORDION-BEGIN [Step 1: ](Create development space)]

1. On the SAP Business Application Studio start page, click **Create Dev Space**.

    !![Start the Dev Space](create-dev-space.png)

2. On the following page, enter a name for your new development space and choose the application type **SAP Cloud Business Application** from the list.

    Click **Create Dev Space**.

    !![Start the Dev Space](create-dev-space-BAS.png)

    Your development space is now ready to use. Wait until the status has changed from **STARTING** to **RUNNING**. After the initial creation this is done automatically.

    !![Start the Dev Space](create-dev-space-starting.png)

    >In case your development space was stopped, you can restart it by clicking the start button (for example after a longer idle time).

3. Open the development space by clicking on its name.

    !![Start the Dev Space](open-dev-space.png)

    &nbsp;

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 2: ](Create an SAP Fiori elements application based on the generated RAP service)]

After start of your development space you will see the SAP Business Application Studio. You will now create an SAP Fiori elements application based on the RAP backend service (the ABAP RESTful Application Programming Model) created in the previous chapters.

1. Start the Application Generator.

    Once the **Welcome** page is shown, click **Start from template**.

    !![Select link "Create project from template"](select-create-project.png)

2. Select the tile **SAP Fiori elements application** and click **Next**.

    !![Choose tile "SAP Fiori elements application"](choose-tile-sap-fiori-elements.png)

3. On the page **New Project From Template**, select the tile **List Report Object Page** and click **Next**.

    !![Choose tile "List Report Object Page"](choose-tile-list-report.png)


4. Now you connect the application template with your OData service. The OData service you use for this example was already prepared during the previous tutorial:  [Prepare the RAP service to be used for the application](fiori-tools-rap-prepare-service)

    Select the data source for the project. Since you use the backend RAP service, choose **Connect to an SAP System** from the dropdown field **Data source**.

    Navigate to the **System** selection dropdown field and choose **ABAP trial system SCP** (as shown in the screenshot).

    Choose the **Service** name of your ODATA service having your **unique suffix**.

    When finished, click **Next**.

    !![Select service related parameters](enter-service-parameters.png)

    Select **The organization and space in Cloud Foundry** have not been set.

    >Note: If you get an error indicating that your ABAP environment cannot be found, it could be that **the organization and space** in Cloud Foundry have not been set. Please click on the footer bar and follow the instructions (the entry fields for selection the Organization and Space appear at the top of the screen)

    a. Set your Cloud Foundry endpoint.

    b. Enter the same **e-mail address** you set in your trial instance and press enter.

    c. Enter your **password** and press enter.

    d. Select your **global account** and press enter.

    e. Select **dev** as your space and press enter.

    f. Check your result. Now your organization and space have been set.

    !![Select service related parameters](set-organization-and-space.png)


5. For your application you need to choose the main entity set from the OData service. Objects of this type will be displayed in the list report.

    In your application, start with `Travel`. Choose it as a **Main entity** from the dropdown field.

    Your application will have detailed booking information in a sub-object page. Therefore you need to choose `_Booking` in **Navigation entity** dropdown field .

    When finished, click **Next**.

    !![Choose main entity set](choose-main-entity-set.png)


6. Maintain specific attributes of the application project as follows:

    >Be sure to choose the **Module name** having your unique suffix, because it is referenced in the sample code.


    !![Provide project attributes](provide-project-attributes.png)


    After completion, click **Finish**. The new SAP Fiori elements application is now created from the template using the service and the configurations you provided in this step.


7. Open in a new workspace

    You will now see a popup asking whether you want to open the project in a new workspace. Simply close it by clicking the  **Open in new Workspace**.

    !![Choose in popup Open new workspace](choose-popup-open-new-workspace.png)

    You will now see a new folder **Travel with unique suffix** and content inside.


    !![Review the generated artifacts](review-artifacts.png)

    &nbsp;


[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 3: ](Start the application)]

    Your SAP Fiori elements application needs a server to run. This server is provided by the command line client and development toolkit for the SAP Cloud Application Programming Model. The setup for using the server was done in the previous tutorial [Prepare Your Development Environment](fiori-tools-cap-prepare-dev-env).

1. Open a **New Terminal** in your SAP Business Application Studio.

    !![Start a new Terminal](open-new-terminal.png)

2. Start the server and the application.

    Ensure that your terminal prompt shows **workspace name** having your unique suffix.

    Then type `npm start` in the console and press the **Enter** key to start the server and the application.


    !![Start server and application via npm install in terminal](start-server.png)

3. After start of a server the list report application will come up a new browser window.

    The application starts with an empty list. You can click **Go** to load data.
    The list report table will then show the data from the sample service.

    !![Click go on list report to see data](click-go-on-list-report.png)

4. You can also navigate to the **object page**.

    !![Navigate to the object page](navigate-to-object-page.png)


5. On the object page you will see the **detailed information** of selected business trip.

    !![Object page with detailed info](see-object-page-with-info.png)

    &nbsp;


[DONE]
[ACCORDION-END]



[ACCORDION-BEGIN [Step 4: ](Activate Flexible Column Layout)]

    Now we could modify our application in SAP Business Application Studio. For example we can enable the flexible column layout in the page map.

  Flexible Column Layout allows to have the List Report and the Object Page open at the same time without the need to switch the UI when changing the selection of items in the List Report.

1. In the SAP Business Application Studio do the **right-click on folder with application** in explorer.


    !![Right-click on webapp folder](right-click-on-webapp.png)

2. In popover click on **Show Page Map**.

    !![Popover with Show Page Map entry](show-page-map.png)

3. The Page Map shows the page structure of the app.

    Apart from page structure and page specific configurations you can also change **Layout Settings** and switch on the flexible column layout.

    In the **Global Page Settings** select **Flexible Column Layout**.

    !![The Page Map with page map and layout settings](switch-on-flexible-layout.png)

4. Select additional Layout settings

    You can configure the default layout for the case of two and three columns.

    Select **Mid-Expanded** option for both cases and click **Apply**.

    !![Select mid-expand as layout for two and three colums case](select-layout.png)

5. **Refresh** the already shown application preview in your browser window and click the **Go** button.

    !![Click go on list report after refresh](refresh-app-and-click-go.png)

6. Click on one of the items in the list report to open the object page.

    !![Select one of the list report items in table](click-on-list-report-item.png)


7. The list report and object page are now shown in the flexible column layout.

    !![List report and object page shown on one page](list-report-and-objectpage-on-onepage.png)

8. When you **click on another row** in the list report the object page will update accordingly.

    !![Object page update on another item selection](select-another-item-in-listreport.png)

    &nbsp;


[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Activate Initial Loading of data)]

    You can configure your application in a way that the data is automatically loaded in the List Report when the application is started without the need of pressing the Go button.

1. Again, open the page map by right-clicking on the **folder with application** in explorer and choose **Show Page Map**.

    !![Select show page map on right click on webapp folder](select-another-item-in-listreport.png)

2. In the page map you will see the **List Report**. Click on **Configure Page** icon.

    !![Configure Page icon on list report block](click-configure-page-icon.png)

3. The **Page Editor** will come up. Click on **table**.

    !![Click on table in page editor](click-on-table-in-page-editor.png)

4. In the **Properties of table** open the drop-down list of field **Initial Load** and select **True**.

    !![Select true for initial load in drop down field](select-initial-load.png)

5. Restart your application and see the result of this settings.

    **Restart** your application via **npm start** in the console of SAP Business Application Studio.

    The application will be started, and the data will be **loaded automatically** without the need of pressing the Go button.

    !![Restart the app and see the initial load of data](restart-app-and-see-initial-load.png)

    &nbsp;



[VALIDATE_1]
[ACCORDION-END]



---

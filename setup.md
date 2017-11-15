---
layout: page
title: Watson Data Platform
tagline: Developer Starter Kits
description: Simple projects that get you started
---
# Watson Data Platform Starter Kit
## Hello Data!

The following steps are prerequisites before using the starter kit applicaiton. Performing them will also give you an understanding of how the WDP experiences represent the structures you will be using the APIs to interact with.

The assumption is that you do not have any previously deployed elements of Watson Data Platform. If you or your organization has already provisioned Watson Data Platform services and you have access to active projects and data sources, you may be able to use this starter kit application without these prerequisite steps. 



1. <a href="#stepone">Prepare your data sources</a>
2. <a href="#steptwo">Provision the WDP experiences</a>
3. <a href="#stepthree">Create a project</a>
4. <a href="#stepfour">Add your data sources to the project</a>


<p>&nbsp;</p>
<a name="stepone"></a>

**Step 1: Prepare your data sources**

1. Cloudant:

    Create an empty database in the new instance created in your starter kit project
    1. From the service list in your starter kit project, select **Open Dashboard** from the **Actions** menu of the **Cloudant NoSQL DB** entry
    2. From the next page select the Launch action to open the Cloudant web console.
    3. In the new browser window, click the *Databases* tab in the left navigation, and create a database using a name or your choosing.

2. Db2 Warehouse on Cloud

    This database does not require additional setup after the starter kit created the instance for you. If you wish, you can manage it from the service list in your starter kit project. 
    1. Select **Open Dashboard** from the **Actions** menu of the **DB2 Warehouse on Cloud** entry.
    2. From the next page select the Launch action to open the Cloudant web console.


3. Local data file

    Download the following file to your local machine: <a href='https://raw.githubusercontent.com/ibm-watson-data-lab/wdp-skit-cookbook/master/SETUP/sample_csv_file.csv' download>sample\_csv\_file.csv</a>.

<p>&nbsp;</p>
<a name="steptwo"></a>

**Step 2: Provision the WDP experiences**

1. Data Science Experience

    If you already have access, log on before continuing.
    1. Sign up for [Data Science Experience](http://datascience.ibm.com/)


2. Add Data Catalog

    From Data Science Experience you can add additional applicaitons. Data Catalog is one of these
    1. Click the avatar icon in the upper-right corner ( it displays your initials by default )
    2. From the menu, select **Add Other Apps** and add **Data Catalog**. If this entry does not appear, you already have it deployed.

<p>&nbsp;</p>
<a name="stepthree"></a>

**Step 3: Create a project**
    
From the Data Science Experience application

1. Open the projects view by selecting **View All Projects** from the **Projects** menu at the top of the page.
2. Create a new project named **data access demo**:
    - Associate a Spark service instance.
    
        If you do not already have a Spark instance to associate with the new project, create one:
        1. Click "Create a new IBM Analytics for Spark instance" (this will take you to a new window.)
        2. After the new Spark instance is created, close the new window, and click "Reload" in the project creation window.
        3. From the drop-down menu, select the new Spark instance you just provisioned.

    - Associate an instance of **Cloud Object Storage** ( Currently Beta )
        **Warning:** The storage type must be "Cloud Object Storage (Beta)", not "Object Storage (Swift API)".
        
        If you do not already have an instance of Cloud Object Storage (Beta) to associate with the new project, create one:
        1. Click "Create a new instance" (this will take you to a new window.)
        2. After the new Cloud Object Storage (Beta) instance is created, close the new window, and click "Reload" in the project creation window.
        3. From the drop-down menu, select the new Cloud Object Storage (Beta) instance you just provisioned.

<p>&nbsp;</p>
<a name="stepfour"></a>

**Step 4: Add your data sources to the project**

In this step you will populate the project with the data needed to use this starter kit:

1. Create a connection to Cloudant:
    1. From the *data access demo* project page, select the **Assets** tab.
    2. Choose **Connection** from the **Add to project** menu.
    3. In the *New connection* page, select the Cloudant service instance you provisioned.

2. Create a connection to DB2 Warehouse on Cloud:
    1. From the *data access demo* project page, select the **Assets** tab.
    2. Choose **Connection** from the **Add to project** menu.
    3. Select the Db2 Warehouse on Cloud service instance you provisioned.

3. Upload a local data file
    1. From the *data access demo* project page, select the **Assets** tab.
    2. Choose **Data asset** from the **Add to project** menu.
    3. If it was not already open the **Files** panel on the right side of the screen will open.
    4. Use browse or drag-and-drop to add the .csv file you downloaded earlier to the project.

<p>&nbsp;</p>
You should now see three data assets in your project and can now explore them using the starter kit application:


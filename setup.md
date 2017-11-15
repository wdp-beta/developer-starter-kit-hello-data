Complete the following steps before working with this starter kit

1. <a href="#stepone">Log in to Data Science Experience</a>
2. <a href="#steptwo">Add Data Catalog</a>
3. <a href="#stepthree">Set up databases</a>
4. <a href="#stepfour">Create a project</a>
5. <a href="#stepfive">Add database connections to the project</a>
6. <a href="#stepsix">Add a data file to the project</a>
<p>&nbsp;</p>

<a name="stepone"></a>
***

**Step 1: Log in to Data Science Experience**

1. Click here to log in (or sign up): [Data Science Experience](http://datascience.ibm.com/analytics)
<p>&nbsp;</p>
<a name="steptwo"></a>

***

**Step 2: Add Data Catalog**
1. Click the avator icon in the upper-right corner (it displays your initials by default.)
2. From the menu, select **Add Other Apps** and then add Data Catalog:
    1. On the Data Catalog card, click "Try it for free".
    2. Scroll down to select the Beta and then click **Create**.
    3. Change the name from the default, if you want to, and then click **Confirm**.
<p>&nbsp;</p>
<a name="stepthree"></a>

***

**Step 3: Set up databases**

1. Provision an IBM Cloudant NoSQL DB service instance:

    (If you already have an instance in IBM Cloud, skip this step.)
    1. Open the services page by choosing **Services** from the **Data Services** menu at the top of the page.
    2. Click IBM Cloudant NoSQL DB.
    3. Scroll down to to select the "Lite" plan and then click **Create**.

2. Create an empty Cloudant database:

    1. Open the Cloudant service page by choosing **Manage on IBM Cloud** from the **Actions** menu (or **Manage on Bluemix** - IBM Cloud was formerly named Bluemix.)
    2. Launch the Cloudant web console.
    3. In the new browser window, click the *Databases* tab in the left navigation, and create a database using any new name.
    4. Close the Cloudant web console.

3. Provision a Db2 Warehouse on Cloud service instance:

    (If you already have an instance in IBM Cloud, skip this step.)
    
    1. Open the services page by choosing **Services** from the **Data Services** menu at the top of the page.
    2. Click Db2 Warehouse on Cloud.
    3. Scroll down to to select the "Entry" plan and then click **Create**.

    **Note:** The Entry plan shows a monthly cost in the confirmation modal, but the Entry plan is free if you use less than 1GB of storage, which you will be for this starter kit.
<p>&nbsp;</p>
<a name="stepfour"></a>

***

**Step 4: Create a project**

1. Open the projects view by selecting **View All Projects** from the **Projects** menu at the top of the page.
2. Create a new project named **data access demo**:
    - Associate a Spark service instance.
    
        If you do not already have a Spark instance to associate with the new project, create one:
        1. Click "Create a new IBM Analytics for Spark instance" (this will take you to a new window.)
        2. After the new Spark instance is created, close the new window, and click "Reload" in the project creation window.
        3. From the drop-down menu, select the new Spark instance you just provisioned.

    - Associate an instance of **Cloud Object Storage (Beta)**.
    
        **Warning:** The storage type must be "Cloud Object Storage (Beta)", not "Object Storage (Swift API)".
        
        If you do not already have an instance of Cloud Object Storage (Beta) to associate with the new project, create one:
        1. Click "Create a new instance" (this will take you to a new window.)
        2. After the new Cloud Object Storage (Beta) instance is created, close the new window, and click "Reload" in the project creation window.
        3. From the drop-down menu, select the new Cloud Object Storage (Beta) instance you just provisioned.
<p>&nbsp;</p>
<a name="stepfive"></a>

***

**Step 5: Add database connections to the project**

1. On the *data access demo* project page, select the **Assets** tab.
2. Create a connection to your Cloudant database:
    1. Choose **Connection** from the **Add to project** menu.
    2. In the *New connection* page, select the Cloudant service instance you provisioned.
3. Create a connection to your Db2 Warehoues on Cloud database:
    1. Choose **Connection** from the **Add to project** menu.
    2. Select the Db2 Warehouse on Cloud service instance you provisioned.
<p>&nbsp;</p>
<a name="stepsix"></a>

***

**Step 6: Add a data file to the project**

1. Download the following file to your local machine: <a href='https://raw.githubusercontent.com/ibm-watson-data-lab/wdp-skit-cookbook/master/SETUP/sample_csv_file.csv' download>sample\_csv\_file.csv</a>.

    (Alternatively, you could use any .csv file you already have.)

2. The file upload panel is a dark blue panel on the right side of the screen.  Sometimes this panel is opened by default.  If the panel is not already open, open it by selecting **Data asset** from the **Add to project** menu at the top of the page.
3. Add the .csv file to the project.

You should now see three data assets in your project:
- The .csv file
- A connection to your Cloudant database
- A connection to your Db2 Warehouse on Cloud database

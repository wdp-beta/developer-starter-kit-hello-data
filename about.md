***
 TODO: 
  * replace all stage1 URLs with public URLs
***

# About the Hello Data! application

The Starter Kit application illustrates how to navigate the project and asset structure, collect data asset information and then shows how to use that information to access a NoSQL database (IBM Cloudant), a relational database (DB2 Warehouse on Cloud) and a data file stored on the Cloud (IBM Cloud Object Storage.)

It comprises of two components:
 * A simple HTML/Javascript web UI that collects user input and communicates with the back-end.
 * A [Express web framework for Node.js](http://expressjs.com/) -based back-end. The back-end leverages an unofficial purpose-build shallow warpper library to communicate with the Watson Data Platform API and three sample data source implementations for IBM Cloudant, IBM Db2 Warehouse on Cloud and IBM Cloud Object Storage.

![overview](img/skit_app_structure.png)


## Implementation overview

**Note**: Throughout this document you will find references to source code files, such as `/server/lib/client.js`. The specified location is relative to the directory where you extracted the downloaded source code or the github repository into which the starter code was pushed by the devops pipeline.


### Hello Data! back-end 

To keep things simple, the back-end (`/server/routers/hello-data.js`) provides three state-less endpoints for the web UI:
 * list Watson Data Platform projects
 * list Watson Data Platform project assets
 * access Watson Data Platform data assets

Each endpoint invokes one or more Watson Data Platform APIs using the wrapper library described in a later section.

#### Accessing the Watson Data Platform API 

(TODO links)
Each API endpoint requires an API token, which you [mint by calling an authorization endpoint](https://www.ibm.com), providing an API key. API tokens expire after 3600 seconds.

 > Note: At the time of writing the authentication API returns HTTP status code `400 (Bad Request)` and not `403 (Forbidden)` if an invalid API key was provided.
 
Endpoints return only information that is visible to the specified API key. The Swagger specification for all endpoints can be found [here](http://www.ibm.com).

#### Listing Watson Data Platform projects

To list projects, call the [`GET /v2/projects`](https://apsx-api.stage1.ng.bluemix.net/v2/projects/docs/swagger/#/Projects/getProjects) endpoint. The JSON response contains for each project two pieces of key information: the project name (`entity.name`) and a unique internal project id (`metadata.guid`). Most API endpoints that operate in the context of a project (such as the project API or the asset API) require this project id as an input. Just like all other list-ing endpoints, the project list endpoint supports pagination and filtering. (TODO links to appropriate topic)

> For illustrative purposes, the Hello Data! web UI displays the raw JSON response.

#### Listing Watson Data Platform project assets 

TODO

#### Accessing Watson Data Platform data assets 

TODO

### Shallow Watson Data Platform API Wrapper
The Watson Data Platform provides a [REST API](https://developer.ibm.com/api/view/id-1084:title-Watson_Data_Platform_Core_Services) that applications can use consume its services. This application utilizes a purpose build shallow wrapper library (`/server/lib/client.js`) to communicate with this API. Once an official Node.js SDK is released this wrapper library is obsolete.

The wrapper library encapsulates the HTTP request/response processing (including authentication) but does not contain any business logic.

### IBM Cloudant data access

Access to Cloudant is implemented in `/server/lib/data_access_helpers/cloudant_data_access_sample.js`. The sample code leverages the official [cloudant](https://www.npmjs.com/package/cloudant) library but you have [a couple of alternatives](https://medium.com/ibm-watson-data-lab/choosing-a-cloudant-library-d14c06f3d714), depending on your exact needs. The code uses the data assets' connection credentials to connect to the Cloudant service instance and counts the number of databases in that instance.

### IBM Db2 Warehouse on Cloud data access

Access to IBM Db2 Warehouse on Cloud is implemented in `/server/lib/data_access_helpers/db2wh_data_access_sample.js`. The sample code uses the official [ibm_db](https://www.npmjs.com/package/ibm_db) library. The code uses the data assets' connection credentials to connect to the database instance and counts the number of user tables.

### IBM Cloud Object storage data access

Access to IBM Cloud Object Storage is implemented in `/server/lib/data_access_helpers/cos_data_access_sample.js`. The sample code uses the official [ibm-cos-sdk](https://www.npmjs.com/package/ibm-cos-sdk) library. The code uses the data assets' resource information to download  the content and determine its size.


## Deployment
To deploy this Watson Data Platform Starter Kit follow the instructions on [the Watson Data Platform Starter Kit page](https://dev-console.stage1.bluemix.net/developer/dataplatform/starter-kits)

The Starter Kit and its instuctions will help you set up a Watson Data Platform project if you do not have one, configure instances of Cloudant and DB2 Warehouse on Cloud and run the node.js application either in the IBM cloud with continuous delivery enabled or locally on your workstation. 

### Debugging 
After the application has been deployed to yor target environment you can optionally enable debugging to learn more about the interactions between the modules and the [Watson Data Platform API](https://wdp-api-registry.mybluemix.net/api-explorer/) and the data services.
 * Hello Data web page: debug output is always written to the browser console.
 * Backend modules: to enable debug output for all modules set environment variable `DEBUG` to `hello-data:*`
   * hello-data router: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:router`
   * hello-data Cloudant data access: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:cloudant_sample`
   * hello-data Db2 Warehouse on Cloud data access: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:db2wh_sample`
   * hello-data IBM Cloud Object Storage data access: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:cos_sample`

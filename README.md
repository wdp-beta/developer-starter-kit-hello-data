---
title: 
layout: 
---

# Watson Data Platform - "Hello Data!" starter kit

This Node.js starter kit application illustrates how to collect data asset information from a Watson Data Platform project and how to access a Cloudant database, a DB2 Warehouse on Cloud database and a data file that's stored in IBM Cloud Object Storage using that information.

![overview](img/skit_overview.png)

## Deployment
To deploy this Watson Data Platform Starter Kit follow the instructions on [the Watson Data Platform Starter Kit page](https://dev-console.stage1.bluemix.net/developer/dataplatform/starter-kits)

### Debugging 
After the application has been deployed to yor target environment you can optionally enable debugging to learn more about the interactions between the modules and the [Watson Data Platform API](https://wdp-api-registry.mybluemix.net/api-explorer/) and the data services.
 * Hello Data web page: debug output is always written to the browser console.
 * Backend modules: to enable debug output for all modules set environment variable `DEBUG` to `hello-data:*`
   * hello-data router: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:router`
   * hello-data Cloudant data access: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:cloudant_sample`
   * hello-data Db2 Warehouse on Cloud data access: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:db2wh_sample`
   * hello-data IBM Cloud Object Storage data access: to enable debug output only for this module set environment variable `DEBUG` to `hello-data:cos_sample`
  

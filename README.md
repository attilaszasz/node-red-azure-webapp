# Node Red Azure Web App Wrapper
A webapp wrapper for running node-red in an Azure Web App.

This a fork of Juan Manuel Servera's **node-red-azure-webapp**  
Notable changes:
- Node Red updated to version 2.x
- Added monitoring via Application Insights

## How to set up

Deploy to Azure with this button:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fattilaszasz%2Fnode-red-azure-webapp%2Fmaster%2Fwebapp.json" target="_blank"><img src="http://azuredeploy.net/deploybutton.png"/></a>

The deployment will create a new serverfarm website application insight. The website will be configured with the application insight Instrumentation Key.

**Note**: The `Microsoft.Web/sites/sourcecontrols` deployment step takes a really long time as it performs an `npm install`  

> This project currently uses a workaround to avoid a small problem caused with `child_process.execFile`: it uses a fake npm.cmd that points to the real one.

## Usage

Wait until everything is deployed before opening the website during the deployment a script is executed to download this repo and install all the needed modules. If you see this screen just wait about 30 seconds to let the Node-RED app start:

![Not Started Site](./_images/notstarted.png)

**Figure 3** Not Started Site

You can see the live log in the Azure Portal in the *Log stream* tab:

![Application logs stream](./_images/logstream.png)

**Figure 4** Application logs stream

## Packages
It comes with dashboard preinstalled:

* Dashboard (create an awesome ui and see it in https://yoursite/ui )

Recommended packages to install:

node-red-contrib-azure-blob-storage-aleph  
node-red-contrib-cosmos-db  
node-red-contrib-azure-sql  
node-red-contrib-azure-table-storage-aleph  
node-red-contrib-mssql-plus  
node-red-contrib-azure-service-bus-topic  
node-red-contrib-azure-service-bus-queue  
node-red-contrib-cognitive-services  
node-red-dashboard  
node-red-node-swagger  
node-red-node-email  
node-red-contrib-actionflows  
node-red-node-rbe  
node-red-contrib-bigtimer  
node-red-contrib-counter  
node-red-contrib-influxdb  
node-red-contrib-persistent-fsm  
node-red-contrib-postgresql  
node-red-node-mysql  
node-red-node-twilio  
node-red-contrib-sendgrid  
node-red-node-sqlite  
node-red-node-mongodb  
node-red-contrib-redis  

## Securing your deployment

To secure this deployment and add an admin password edit the `settings.js` file.

## Version History

* v0.0.1
  * First test with basic nodes
* v0.0.2
  * Deploy to Azure Button
  * Add cognitive services
* v0.0.3
  * Update Node-Red version to 0.18.4
* v1.0.0
  * Update Nodejs to 8.9.4
  * Make Nodejs version configurable
  * Add Swagger Node
* v2.0.0-beta
  * Update Nodejs to 12
  * Update Node-red to 1.0.6
  * Update azureiothubnode to 0.5.2
  * Update cognitive-services 0.5.5
  * Update dashboard 2.21.0
  * Update node-swagger 0.1.9
  
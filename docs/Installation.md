# Installation

- [Installation](#installation)
  - [Configure PLC Connection](#plc-connection)
    - [Option 1: OPC UA Connector](#option1)
    - [Option 2: SIMATIC S7+ Connector](#option2)
  - [Import OPC UA Model](#model-import)
    - [Connect your Industrial Edge App Publisher](#connect-your-industrial-edge-app-publisher)
    - [Upload  App using the Industrial Edge App Publisher](#upload--app-using-the-industrial-edge-app-publisher)
  - [Deploying of App](#deploying-of-app)
    - [Configuring application](#configuring-application)
    - [Add additional installation steps here, if required](#add-additional-installation-steps-here-if-required)
      - [Additional steps](#additional-steps)
  
## Configure PLC Connection

To read data from the PLC and provide the data we will use two options, OPC UA Connector and SIMATIC S7+ Connector.

### Option 1: OPC UA Connector

OPC UA Connector reads data from PLC OPC UA Server and sends data to the IE Databus where the IIH app will collect it.

In order to build this infrastructure we need the following connectors and apps:

- IE Databus
- OPC UA Connector
- IIH Registry Service
- IIH Core
- IIH Configurator

#### Configure the IE Databus

In your IEM open the IE Databus and launch the configurator.

Add a user with this topic: "ie/#"

[Databus Topic](docs/graphics/databus_topic.png)

Deploy the configuration.

[Databus Deploy](docs/graphics/databus_deploy.png)

#### Configure the OPC UA Connector

In your IEM open the OPC UA Connector and launch the configurator.

Add a new data source:

[OPCUA DataSource](docs/graphics/opcua_datasource.png)

Add needed tags.

[OPCUA Tags](docs/graphics/opcua_tags.png)

Edit the settings. Username ad password should be the same as configured in IE Databus configuration.

[OPCUA Settings](docs/graphics/opcua_settings.png)

Deploy and start the project.

#### IIH Registry Service

This app needs to be installed on the IED and it allows to the IIH to discover which connectors are sending data through the databus.

#### IIH Core

This app collects data from the different connectors.

#### Configure the IIH Configurator

This apps allows the configuration of the IIH.

In your IED clik IIH Configurator to open it.

Go to the settings tab and add the Databus credentials for subscribing and publishing topics.

[IIH Databus_SubCred](docs/graphics/iih_databus_sub_credentials.png)
[IIH Databus_PubCred](docs/graphics/iih_databus_pub_credentials.png)

### Option 2

SIMATIC S7+ Connector reads data from PLC and then IIH app will collect it.

In order to build this infrastructure we need the following connectors and apps:

- SIMATIC S7+ Import Converter
- SIMATIC S7+ Connector
- IIH Core
- IIH Configurator


## Upload  App to the Industrial Edge Managment

Please find below a short description how to publish your application in your IEM.

For more detailed information please see the section for [uploading apps to the IEM](https://github.com/industrial-edge/upload-app-to-iem).

### Connect your Industrial Edge App Publisher

- Connect your Industrial Edge App Publisher to your docker engine
- Connect your Industrial Edge App Publisher to your Industrial Edge Managment System

### Upload  App using the Industrial Edge App Publisher

- Create a new application using the Industrial Publisher
- Add a app new version
- Import the [docker-compose](../docker-compose.yml) file using the **Import YAML** button
- The warning `Build (sevices >> scanner-service) is not supported` can be ignored
- **Start Upload** to transfer the app to Industrial Edge Managment
- Further information about using the Industrial Edge App Publisher can be found in the [IE Hub](https://iehub.eu1.edge.siemens.cloud/documents/appPublisher/en/start.html)

## Deploying of App

### Configuring application

If your app needs additional configuration you can add further description here, e.g. [param.json](../cfg-data/param.json)

```json
{
    "Parameter1": "Siemens AG",
    "Parameter2": "edge",
    "Parameter3": "edge"
}
```

Add description of the configuration here:

### Add additional installation steps here, if required

#### Additional steps

Add description here

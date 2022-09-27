# Installation

- [Installation](#installation)
  - [Configure PLC Connection](#configure-plc-connection)
    - [Option 1: OPC UA Connector](#option1)
    - [Option 2: SIMATIC S7+ Connector](#option2)
  - [Import OPC UA Model](#import-opc-ua-model)
    - [Import a Companion Specification](#import-companion-spec)
    - [Import the OPC UA model](#import_opcua_model)
  - [Mapping tags](#mapping-tags)
    - [Option 1: SIMATIC S7+ Connector Mapping](#mapping-option1)
    - [Option 2: OPC UA Connector Mapping](#mapping-option2)
  
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

Add a user with this topic: <br> `"ie/#"` <br> 

![Databus Topic](graphics/databus_topic.png)

**Deploy** the configuration.

![Databus Deploy](graphics/databus_deploy.png)

#### Configure the OPC UA Connector

In your IEM open the OPC UA Connector and launch the configurator.

Add a new data source:

![OPCUA DataSource](graphics/opcua_datasource.png)

Add needed tags.

![OPCUA Tags](graphics/opcua_tags.png)

Edit the settings. Username and password should be the same as configured in IE Databus configuration.

![OPCUA Settings](graphics/opcua_settings.png)

**Deploy** and **start** the project.

#### IIH Registry Service

This app needs to be installed on the IED and it allows to the IIH to discover which connectors are sending data to the databus.

#### IIH Core

This app collects data from the different connectors.

#### Configure the IIH Configurator

This apps allows the configuration of the IIH.

In your IED click IIH Configurator to open it.

Go to the settings tab and add the Databus credentials for subscribing and publishing topics.

![IIH Databus_SubCred](graphics/iih_databus_sub_credentials.png)
![IIH Databus_PubCred](graphics/iih_databus_pub_credentials.png)

### Option 2: SIMATIC S7+ Connector

SIMATIC S7+ Connector reads data from PLC and then IIH app will collect it. We need to export tags from TIA Portal Project using SIMATIC SCADA Export:

![SimaticScadaExport](graphics/simatic_scada_export.png)

A file **Export.zip** is created.

In order to build this infrastructure we need to have installed the following connectors and apps:

- SIMATIC S7+ Import Converter
- SIMATIC S7+ Connector
- IIH Core
- IIH Configurator

#### Configure IIH Configurator

SIMATIC S7+ Import Converter converts the export file to Connectivity Suite Configuration

In your IED click IIH Configurator to open it.

Go to **Aggregate Data -> Connector Configuration** and to Connectivity Suite Connectors tab and click inside the box.

![S7Conf1](graphics/iih_s7_conf1.png)

Add the tags importing the Export.zip file from TIA Portal.

![S7Conf2](graphics/iih_s7_conf2.png)
![S7Conf3](graphics/iih_s7_conf3.png)

It's necessary to edit the data source and add the **PLC IP address**.

![S7Conf4](graphics/iih_s7_conf4.png)
![S7Conf5](graphics/iih_s7_conf5.png)

Select all the tags needed, choose the Adquisition Cycle, the Access Mode and the **Apply**.

![S7Conf6](graphics/iih_s7_conf6.png)

Import and deploy them.

![S7Conf7](graphics/iih_s7_conf7.png)
![S7Conf8](graphics/iih_s7_conf8.png)

![S7Conf9](graphics/iih_s7_conf9.png)

## Import OPC UA Model

OPC UA protocol allows companies or organizations to standardize their data for an OPC UA information model. It's possible to generate standardized interfaces for the OPC UA servers, so OPC UA clients only need to know the information defined in that standard and not taking into account information not relevant.

This standardized interface is called companion specification. There are already many organizations or groups of companies which have already standardized some OPC UA information models for some industries, but a user can also create their own companion specifications.

In this example there was a user-defined companion specification for the filling bottle machine created and then a model based on this companion specification using Siemens OPC UA modeling Editor (SiOME). 

Further information about using SiOME can be found in the [SIOME](https://support.industry.siemens.com/cs/es/en/view/109755133)

From SiOME two nodesets were exported, one for the companion specification and other one for the instance model. The files you can find here:

- [TankNodeset.xml](../src/TankNodeset.xml)
- [TankModelNodeset.xml](../src/TankNodeset.xml)

### Import a Companion Specification

Go to IIH Configurator.

In Organize Data -> Mapping & Transformation select **Create Model**. Then select **Add Model**.

![IIH_CreateModel](graphics/iih_create_model.png)
![IIH_AddModel](graphics/iih_addmodel.png)

Add a companion specification .xml file. The file used in the example is called TankNodeset.xml

![IIH_LoadCompanionSpec](graphics/iih_load_comp_spec.png)

Load the TankNodeset.xml and select the namespace for the companion specification:

![IIH_LoadTankCompanion](graphics/iih_load_tanknodeset.png)
![IIH_CompSpec_Namespace](graphics/iih_namespace_comp_spec.png)

### Import the OPC UA model

The model is an instance of the standardized information that is defined in the companion specification.

Add the model.

![IIH_AddInstance](graphics/iih_addmodel_instance.png)

Load the TankModelNodeset.xml

![IIH_LoadInstance](graphics/iih_load_instance.png)

Select the namespace for that model.

![IIH_LoadTankModel](graphics/iih_load_model_nodeset.png)
![IIH_model_Namespace](graphics/iih_select_model_namespace.png)

![IIH_model](graphics/iih_information_model.png)

## Mapping tags

### Option 1: SIMATIC S7+ Connector Mapping

Select **Assigned to OPC UA** and the namespace for the model. 
Select **Connectivity Suite** as a data source and **SIMATIC S7+ Connector** as the connecotr.
Drag and drop tags from the connector into the model window.

![IIH_s7mapping](graphics/iih_s7_mapping.png)

**Deploy**

![IIH_s7mapping_deploy](graphics/iih_s7_mapping_deploy.png)

### Option 2: OPC UA Connector Mapping

Select **Assigned to OPC UA** and the namespace for the model. 
Select **Databus** as a data source and **opcua** as the connecotr.
Drag and drop tags from the connector into the model window.

![IIH_opcuamapping](graphics/iih_opcua_mapping.png)

**Deploy**



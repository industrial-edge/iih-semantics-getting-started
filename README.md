# Industrial Information Hub (IIH Semantics) Getting Started
This repository contains the source files to build the Industrial Information Hub Getting Started example.

- [Industrial Information Hub (IIH Semantics) Getting Started](#industrial-information-hub-iih-semantics-getting-started)
  - [Description](#description)
    - [Overview](#overview)
    - [General Task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [TIA Project](#tia-project)
  - [Configuration Steps](#configuration-steps)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [License and Legal Information](#license-and-legal-information)

## Description
### Overview
This application example describes the implementation and usage of the IIH as a central integration layer. It is shown how data can be read from PLCs and mapped on a data model. This model then can be accessed by external applications via different APIs or OPC UA.

![Overview](docs/graphics/overview.png)

### General Task
The main goal of the task is to read some relevant data from the PLC and have it accessible to other applications with a standardized information model using OPC UA companion specifications. The IIH maps data from the PLC to those models and makes data accessible via an OPC UA Server.
To read data from the PLC two options are demonstrated: 
1. OPC UA Connector (Databus)
2. SIMATIC S7+ Connector (Connectivity Suite)     

## Requirements
### Prerequisites
- Access to an Industrial Edge Management System (IEM)
- Onboarded Industrial Edge Device (IED) on IEM
- Installed Configurators for Databus and OPC UA Connector (Common Connector Configurator)
- Installed Apps:
  - Common Configurator
  - Common Import Converter 
  - Databus
  - IIH Semantics 
  - OPC UA Connector
  - Registry Service
  - SIMATIC S7+ Connector
- IED is connected to PLCs
- OPC UA model created with SiOME using a Companion Specification

### Used components
TIA and PLC:
- TIA Portal V16
- PLC: CPU 1511 FW 2.8.3
- SIMATIC SCADA Export V16
- Siemens OPC UA modeling Editor (SiOME) V2.5.12
- UA Expert 1.6.3
  
Industrial Edge:
- Industrial Edge Management App V1.13.10
- Databus Configurator V2.2.0
- Common Connector Configurator V1.9.0-11
- Industrial Edge Virtual Device V1.12.0.3-a
- Common Configurator V1.8.0
- Common Import Converter V2.0.0-1
- Databus V2.2.0
- IIH Semantics V1.8.0
- OPC UA Connector V2.0.0-1
- Registry Service V1.8.0-4
- SIMATIC S7+ Connector V1.2.0-2

### TIA Project
The application example is based on the filling bottles example:
- [Tank application](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application)

## Configuration Steps
- [Configure PLCs with TIA Portal](docs/Installation.md#configure-plcs-with-tia-portal)
- [Configure PLC Connections](docs/Installation.md#configure-plc-connections)
- [Import OPC UA Model](docs/Installation.md#import-opc-ua-model)
- [Mapping Tags](docs/Installation.md#mapping-tags)
- [Creating Asset Model](docs/Installation.md#creating-asset-model)

## Usage
Once the application is successfully deployed, data from the filling bottle machine is accessible via OPC UA to external OPC UA clients.

It is possible to check that using the UA Expert:

1. Connect to port `62520` of your IED to reach the IIH OPC UA Server.  
![UA Expert Server Configuration](docs/graphics/uaexpert_server.png)

2. Authenticate with default username `iihcore` and password `iihcore`.   
![UA Expert Server Auth](docs/graphics/uaexpert_auth_settings.png)

3. Browse the OPC UA Server Model and display data.   
![UA Expert Browse](docs/graphics/uaexpert_browse.png)

## Documentation
You can find further documentation and help in the following links:

- [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
- [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
- [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
- [Industrial Edge GitHub page](https://github.com/industrial-edge)
- [OPC UA Online Reference](https://reference.opcfoundation.org/)
- [UA_NodeSet](https://github.com/OPCFoundation/UA-Nodeset)
- [SiOME](https://support.industry.siemens.com/cs/es/en/view/109755133)

## Contribution
Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## License and Legal Information
Please read the [Legal information](LICENSE.md).


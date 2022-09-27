# Industrial Information Hub (IIH) Getting Started

This repository contains the source files to build the Industrial Information Hub Getting Started example.

- [Industrial Information Hub Getting Started](#IIH-getting-started)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [TIA Project](#tia-project)
  - [Configuration steps](#configuration-steps)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [License and Legal Information](#license-and-legal-information)
## Description

### Overview

This application example describes the implementation and usage of the IIH for reading data from a PLC and sharing the data to external applications using OPC UA models. 

![Overview](docs/graphics/overview.png)

### General Task
The main goal of the task is to read some relevant data from the PLC and have it accessible to other applications with a standarized model of information using OPC UA Companion Specifications. IIH maps data from PLC to those models and makes data accessible via an OPC UA Server.
To read data from PLC two options are used: OPC UA Connector (Databus) and SIMATIC S7+ Connector. In this example it is explained how to get the data from those connectors to the IIH.


## Requirements

### Prerequisites

* Access to an Industrial Edge Management System (IEM)
* Onboarded Industrial Edge Device on IEM
* Installed System Configurators for IE Databus and OPC UA Connector
* Installed System Apps IE Databus and OPC UA Connector
* Installed Apps SIMATIC S7+ Connector
* Installed Apps SIMATIC S7+ Import Converter
* Installed Apps IIH Core
* Installed Apps IIH Configurator
* Installed Apps IIH Registry Service
* Edge device is connected to PLC
* TIA portal project loaded on PLC (e.g. for filling application) with OPC UA Server activated
* OPC UA model created with SiOME using a Companion Specifiction

### Used components

* Industrial Edge Management App V1.8.5
  * IE Databus V1.7.1
  * IE Databus Configurator V1.7.8
  * OPC UA Connector V1.8.0
  * Common Connector Configurator V1.8.0
  * SIMATIC S7+ Connector V1.1.0
  * SIMATIC S7+ Import Converter V1.1.0
  * IIH Core V1.4.0
  * IIH Configurator V1.4.0
  * IIH Registry Service V1.4.0
* Industrial Edge Virtual Device V1.5.0.5-e
* TIA Portal V17
* SIMATIC SCADA Export V17
* PLC: CPU 1513-1 PN FW 2.8
* Siemens OPC UA modeling Editor (SiOME) V2.5.12
* UA Expert 1.5.1

### TIA Project
The application example is based on the filling bottles example:
- [Tank application](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application)

## Configuration Steps

* [Configure PLC Connection](docs/Installation.md#plc-connection)
* [Import OPC UA Model in IIH](docs/Installation.md#model-import)
* [Tags Mapping](docs/Installation.md#tags-mapping)

## Usage

Once the applications is successfully deployed, data from the filling bottle machine is accessible via OPC UA to external OPC UA clients.

It is possible to check it using UA Expert tool:

![UA Expert Server Configuration](docs/graphics/uaexpert_server.png)

![UA Expert Server Auth](docs/graphics/uaexpert_auth_settings.png)

![UA Expert Browse](docs/graphics/uaexpert_browse.png)

## Documentation

You can find further documentation and help in the following links

* [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
* [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
* [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
* [Industrial Edge GitHub page](https://github.com/industrial-edge)
* [OPC UA Online Reference](https://reference.opcfoundation.org/)
* [UA_NodeSet](https://github.com/OPCFoundation/UA-Nodeset)
* [SiOME](https://support.industry.siemens.com/cs/es/en/view/109755133)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you are interested in contributing via Pull Request, please check the [Contribution License Agreement](Siemens_CLA_1.1.pdf) and forward a signed copy to [industrialedge.industry@siemens.com](mailto:industrialedge.industry@siemens.com?subject=CLA%20Agreement%20Industrial-Edge).

## License and Legal Information

Please read the [Legal information](LICENSE.txt).


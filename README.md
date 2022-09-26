# Writing good how-to or tutorial

Before you start writing, read the following materials how to write good documentation (including how-tos).

* [Google Developer style guide](https://developers.google.com/style)
* [Technical writing Courses](https://developers.google.com/tech-writing)
* [Microsoft Writing Style Guide](https://docs.microsoft.com/cs-cz/style-guide/welcome/)

Then decide: Are you writing a tutorial or a how-to guide?

[Divio](https://documentation.divio.com/) explains the difference  (Note that this applies for software documentation for application developers)

* Tutorials are lessons that take the reader by the hand through a series of steps to complete a project of some kind. They are what your project needs in order to show a beginner that they can achieve something with it. https://documentation.divio.com/tutorials/
* How-to guides take the reader through the steps required to solve a real-world problem

Each have a different writing style. Tutorials must be bullet proof (no unexpected behavior) https://documentation.divio.com/how-to-guides/

Note: Try to write the tutorials and how-tos as a standalone html page, ready to be generated using Static site generator [MkDocs](https://www.mkdocs.org/). When referencing code examples or files, use the full URL of the git repository. We want to reuse these how-tos and tutorials in Documentation website.

Don't explain concepts. [It gets in a way of action](https://documentation.divio.com/how-to-guides/#don-t-explain-concepts).  

Don't use HTML tags unless working with videos. And try to avoid using videos unless absolutely necessary. Don't upload videos to Git repository.

Bellow you can find the structure of IE tow-to/tutorial

- [Writing good how-to or tutorial](#writing-good-how-to-or-tutorial)
  - [Description](#description)
    - [Overview](#overview)
    - [General Task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [License and Legal Information](#license-and-legal-information)
# IIH Getting Started

## Description

### Overview

This application example describes the implementation and usage of the IIH for reading data from a PLC and sharing the data to external application using OPC UA models. The application example is based on the filling bottles example.

### General Task

What is the general goal/task of this how-to/tutorial?

![task](docs/graphics/example_graphic.png)

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
* OPC UA model created with SIOME using a Companion Specifiction

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
* Siemens OPC UA modeling Editor (SIOME) V2.5.12

### TIA Project
The used TIA Project can be found in the src -file under the following name:

* .7z

## Configuration Steps

* [Configure PLC Connection](docs/Installation.md#plc-connection)
* [Import OPC UA Model in IIH](docs/Installation.md#model-import)
* [Tags Mapping](docs/Installation.md#tags-mapping)

## Usage

Once the applications is successfully deployed, data from the filling bottle machine is accessible via OPC UA to external OPC UA clients.

## Documentation

Add links to documentation. Either on external URL or in the doc folder. Please use always link to a file not to a directory (it doesn't work with static site generator engines).

Add these links:

You can find further documentation and help in the following links

* [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
* [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
* [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
* [Industrial Edge GitHub page](https://github.com/industrial-edge)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you are interested in contributing via Pull Request, please check the [Contribution License Agreement](Siemens_CLA_1.1.pdf) and forward a signed copy to [industrialedge.industry@siemens.com](mailto:industrialedge.industry@siemens.com?subject=CLA%20Agreement%20Industrial-Edge).

## License and Legal Information

Please read the [Legal information](LICENSE.txt).

```
TO BE DELETED: Depending on the content of your repository either choose the
- LICENSE.md (In case no Source code is included) or the
- LICENSE.txt file (Source Code is included)
```

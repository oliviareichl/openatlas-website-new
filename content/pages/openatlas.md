---
title: OpenAtlas
---

## What is OpenAtlas?

OpenAtlas is an open source database software developed especially to acquire, edit and manage research data from various fields of humanities like history, archaeology and cultural heritage as well as related scientific data (e.g. radiocarbon dating, stable isotopes and anthropological information). It provides a user interface that can be accessed via any common web-browser and allows the respective researchers to work with their data via customized forms and categories to record complex relations as simple as possible.

The software automatically maps the information to the international standard of the [CIDOC CRM](https://www.cidoc-crm.org/) and takes care of today's requirements regarding data standards, data management and aims for [FAIR](https://www.force11.org/fairprinciples) principles against the background of current standards in Digital Humanities.

## How to use OpenAtlas

OpenAtlas is not a stand-alone application but meant to be installed on a Linux web server. The code is open source (GPL2 licence) and freely available on [GitHub](https://github.com/craws/OpenAtlas). Some experience about server administration is required, for more information please take a look at the [installation notes](https://github.com/craws/OpenAtlas/blob/main/install.md#installation-notes).

::software-feature-small
---
image: /assets/images/openatlas-schema.png
ascpectVideo: true
reverse: true
shadow: true
---
### Model

The data [model](https://demo.openatlas.eu/overview/model) specifies the structure in which the information is stored within the database. The use of an ontology, for example, allows the data to be combined more easily with information from other projects and is consistent with the FAIR principles. The OpenAtlas Model is based on the international standard of [CIDOC CRM](https://www.cidoc-crm.org/), an ontology widely used within the field of humanities.

- Types can be used to adapt for specific research topics
- Reference Systems for Linked Open Data (LOD)
- Mapping spatial and temporal uncertainty
- Archaeological finds with detailed mapping
- Data integrity check functions
- Link checker to confirm [CIDOC CRM](https://www.cidoc-crm.org/) validity
::

::software-feature-small{image="/assets/images/map.jpg" ascpectVideo shadow}
### Interactive Map

Places with known location can be entered into an interactive map based on [Leaflet](https://leafletjs.com/), which features different view layers, allows for zooming, fullscreen mode, clustering, searching and much more. PostGIS is used for creating and manipulating spatial data. Therefore, it is possible to enter location as needed as multiple points, lines, areas and shapes.
::

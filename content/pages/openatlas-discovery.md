---
title: OpenAtlas Discovery
---

::text-section
---
shadow: true
image: /assets/images/openatlas-schema.png
variant: light
image-side: right
---
## Model

The data [model](https://demo.openatlas.eu/overview/model) specifies the structure in which the information is stored within the database. The use of an ontology, for example, allows the data to be combined more easily with information from other projects and is consistent with the FAIR principles. The OpenAtlas Model is based on the international standard of [CIDOC CRM](https://www.cidoc-crm.org/), an ontology widely used within the field of humanities.

- Types can be used to adapt for specific research topics
- Reference Systems for Linked Open Data (LOD)
- Mapping spatial and temporal uncertainty
- Archaeological finds with detailed mapping
- Data integrity check functions
- Link checker to confirm [CIDOC CRM](https://www.cidoc-crm.org/) validity
::

::text-section
---
shadow: true
image: /assets/images/map.jpg
variant: light
image-side: left
---
## Interactive Map

Places with known location can be entered into an interactive map based on Leaflet, which features different view layers, allows for zooming, fullscreen mode, clustering, searching and much more. PostGIS is used for creating and manipulating spatial data. Therefore, it is possible to enter location as needed as multiple points, lines, areas and shapes.
::

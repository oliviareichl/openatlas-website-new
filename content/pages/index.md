---
title: OpenAtlas
hero:
  title: Easily Manage your Research Data
  subtitle: |
    OpenAtlas is an open source database software developed especially to acquire, edit and manage research data from various fields of humanities like history, archaeology and cultural heritage as well as related scientific data. 
  buttonLinks:
    - title: GET STARTED
      link: https://github.com/craws/OpenAtlas/blob/main/install.md#installation-notes
    - title: LIVE DEMO
      link: https://demo.openatlas.eu/
    - title: MANUAL
      link: https://manual.openatlas.eu/
  newsDate: '2026-05-27'
  currentVersion: 9.3.0
  images:
    - src: /assets/images/hero_image.jpg
      alt: Hero Image
    - src: /assets/images/feature_bar.svg
      alt: Feature Bar
---

## What is OpenAtlas?

OpenAtlas is an open source database software developed especially to acquire, edit and manage research data from various fields of humanities like history, archaeology and cultural heritage as well as related scientific data (e.g. radiocarbon dating, stable isotopes and anthropological information). It provides a user interface that can be accessed via any common web-browser and allows the respective researchers to work with their data via customized forms and categories to record complex relations as simple as possible.

The software automatically maps the information to the international standard of the [CIDOC CRM](https://cidoc-crm.org/) and takes care of today's requirements regarding data standards, data management and aims for [FAIR](https://force11.org/info/the-fair-data-principles/) principles against the background of current standards in Digital Humanities.

## How to use OpenAtlas

OpenAtlas is not a stand-alone application but meant to be installed on a Linux web server. The code is open source (GPL2 licence) and freely available on [GitHub](https://github.com/craws/OpenAtlas). Some experience about server administration is required, for more information please take a look at the [installation notes](https://github.com/craws/OpenAtlas/blob/main/install.md#installation-notes).

::text-section
---
shadow: false
image: /assets/images/cooperation.png
variant: dark
buttons:
  - title: Contact Us
    link: mailto:openatlas@oeaw.ac.at
    outline: false
  - title: More Information
    link: /work-with-us
    outline: true
imageSide: right
---
## Interested in a cooperation?

Although OpenAtlas is freely available on [GitHub](https://github.com/craws/OpenAtlas), not every project has the internal resources to cover all the aspects needed for successfully using the complex software (e.g. setting up a web server and OpenAtlas itself, updates and backups, development of new features, etc.). It is therefore possible, to cooperate with the OpenAtlas team via the [ACDH](https://www.oeaw.ac.at/acdh), an institute of the [Austrian Academy of Sciences](https://www.oeaw.ac.at/), if budget is available. For current and former cooperations see: [projects](https://openatlas.eu/projects).
::

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

::logo-list
---
logos:
  - image: /assets/images/oeaw.png
    href: https://www.oeaw.ac.at/
  - image: /assets/images/acdh.png
    href: https://www.oeaw.ac.at/acdh
  - image: /assets/images/imafo.png
    href: https://www.oeaw.ac.at/imafo/
  - image: /assets/images/rhul.png
    href: https://www.royalholloway.ac.uk/
  - image: /assets/images/jgu.png
    href: https://www.uni-mainz.de/
  - image: /assets/images/nhm.jpg
    href: https://www.nhm.at/
  - image: /assets/images/lbi.jpg
    href: https://archpro.lbg.ac.at/
  - image: /assets/images/univie.svg
    href: https://www.univie.ac.at/
  - image: /assets/images/erc.png
    href: https://erc.europa.eu/homepage
  - image: /assets/images/fwf.png
    href: https://www.fwf.ac.at/
---
OpenAtlas was and is funded by several [projects](https://openatlas.eu/projects){.text-secondary.fw-bold}, grants, institutes and departments:
::

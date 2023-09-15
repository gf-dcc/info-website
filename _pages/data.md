---
title: BRCA1/2 Cancer Atlas
permalink: /data

section_id: data
layout: secondary
---

# Data

All non-image data associated with the Gray Foundation BRCA Pre-cancer Atlas projects are maintained by Sage Bionetworks. To access the catalog of links to the primary data, visit the Sage Bionetworks Data Portal, below:

<a href="https://portal-613w4c5vz-gray-foundation-dcc.vercel.app/" target="_blank" class="arrow-button">Data Portal</a>

Tissue images associated with the Gray Foundation BRCA Pre-cancer Atlas projects can be viewed online via the software [Minerva](https://github.com/labsyspharm/minerva-story/wiki) and are catalogued below.




## Data Stories
*Data Stories are narrated Minerva stories that guide readers through the complexities of a large image dataset via a series of progressive narrated waypoints*

{% assign cardList = 'cellxgene,single-cell-portal,ovarian-cancer-with-annotation-lsp15327,ovarian-cancer-with-annotation-lsp15343,osd-BRCA-WT-vs-BRCA1-associated-TNBC,brca1-associated-triple' %}

{% include cards.html list=cardList %}

## View Tissue Images
*Access the minimally processed, unannotated Level 2 images associated with the Gray Foundation BRCA Pre-cancer Atlas. Click any of the following thumbnail images for an interactive view of the full-resolution images.*

{% assign dataCards = site.data-cards
    | where_exp: "item", "item.url contains 'mehta-2020,keenan-2020, kadar-drapkin-ovarian-pilot, gray-rosenbluth-selfers-2022'"
    | where_exp: "item", "item.hide != true" %}

{% include cards.html tag='BRCA' %}

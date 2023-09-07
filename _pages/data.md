---
title: BRCA1/2 Cancer Atlas
permalink: /data

section_id: data
layout: secondary
---

# Data

The mutations that cause cancer often arise spontaneously in somatic tissues but some are heritable. Among these mutations in BRCA1 or BRCA2 (BReast CAncer gene 1&2) stand out as having relatively high prevalence and causing a substantial increase in a variety of cancers including those of the breast, ovaries, pancreas and prostate. BRCA1 and BRCA2 are involved in the repair of damaged DNA but the precise events that initiate tumor formation are not fully understood. Data associated with the Gray project is maintained by Sage Bionetworks. The following repository link houses the data.

<a href="https://portal-613w4c5vz-gray-foundation-dcc.vercel.app/explore" target="_blank" class="arrow-button">Data Portal</a>

To explore tissue images associated with these projects, Minerva stories are below.




## Data Explorations
*Data Explorations are like museum guides and exploit the digital docents in MINERVA to guide readers through the complexities of a large image dataset via a series of narrated stories and waypoints.*

{% assign cardList = 'osd-BRCA-WT-vs-BRCA1-associated-TNBC' %}

{% include cards.html list=cardList %}

## Data Overviews
*Data Overviews provide access to minimally processed Level 2 images with no annotation or quality control. Click any of the following thumbnail images for an interactive view of the full-resolution images.*

{% assign dataCards = site.data-cards
    | where_exp: "item", "item.url contains 'mehta-2020,keenan-2020'"
    | where_exp: "item", "item.hide != true" %}

{% include cards.html tag='BRCA' %}

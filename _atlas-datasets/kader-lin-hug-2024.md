---
layout: secondary
title: Atlas Dataset
section_id: publications

data:
  publication:
    title: 'Multimodal Spatial Profiling Reveals Immune Suppression and Microenvironment Remodeling in Fallopian Tube Precursors to High-Grade Serous Ovarian Carcinoma'
    authors: 'Tanjina Kader, Jia-Ren Lin, Clemens Hug, Shannon Coy, Yu-An Chen, Ino de Bruijn, Natalie Shih, Euihye Jung, Roxanne J. Pelletier, Mariana Lopez Leon, Gabriel Mingo, Dalia Khaled Omran, Jong Suk Lee, Clarence Yapp, Baby Anusha Satravada, Ritika Kundra, Yilin Xu, Sabrina Chan, Juliann B. Tefft, Jeremy Muhlich, Sarah Kim, Stefan M. Gysler, Judith Agudo, James R. Heath, Nikolaus Schultz, Charles Drescher, Peter K Sorger, Ronny Drapkin, Sandro Santagata'
    journal: 'TBD'
    description: 'High-Grade Serous Ovarian Cancer (HGSOC) originates from fallopian tube (FT) precursors. However, the molecular changes that occur as precancerous lesions progress to HGSOC are not well understood. To address this, we integrated high-plex imaging and spatial transcriptomics to analyze human tissue samples at different stages of HGSOC development, including p53 signatures, serous tubal intraepithelial carcinomas (STIC), and invasive HGSOC. Our findings reveal immune modulating mechanisms within precursor epithelium, characterized by chromosomal instability, persistent interferon (IFN) signaling, and dysregulated innate and adaptive immunity. FT precursors display elevated expression of MHC-class I, including HLA-E, and IFN-stimulated genes, typically linked to later-stage tumorigenesis. These molecular alterations coincide with progressive shifts in the tumor microenvironment, transitioning from immune surveillance in early STICs to immune suppression in advanced STICs and cancer. These insights identify potential biomarkers and therapeutic targets for HGSOC interception and clarify the molecular transitions from precancer to cancer.'
    links:
        Preprint: https://doi.org/10.1101/2024.09.25.615007
---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}


## Contents
* [Key Findings](#key-findings)
* [Data Stories](#data-stories)
* [Explore Tissue Images](#explore-tissue-images)

### Data Stories
Data Stories are data visualizations that guide readers through the complexities of a large dataset through filters, search, or narrated image waypoints.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'kader-drapkin-ovarian-pilot/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Overview'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

### Explore Tissue Images
Access the minimally processed, unannotated Level 2 images associated with this publication. Click any of the following thumbnail images for an interactive view of the full-resolution images.

{%
    assign stories = site.data-cards
    | where_exp: "item", "item.url contains 'kader-drapkin-ovarian-pilot/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'CyCIF'"
%}

{% assign dataCardArray = '' | split: '' %}
{% for s in stories %}
  {% unless s.url contains '-overview' %}
    {% assign dataCardArray = dataCardArray | push: s %}
  {% endunless %}
{% endfor %}

{% if dataCardArray.size > 0 %}
  {% include cards.html cards=dataCardArray %}
{% endif %}
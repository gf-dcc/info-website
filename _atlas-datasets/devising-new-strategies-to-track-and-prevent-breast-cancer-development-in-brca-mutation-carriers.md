---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: Devising new strategies to track and prevent breast cancer development in BRCA mutation carriers
    description: The overall goal of this project is to better understand the earliest stages of BRCA cancer development, in order to design strategies to prevent its progression to frank cancer. Dr. Joan Brugge’s laboratory studies the mechanisms of cancer initiation, progression, and drug resistance in breast, ovarian and other BRCA-related cancers. Specifically, Brugge’s team investigates tumor heterogeneity, cell-cell interactions, tumor microenvironment, cancer metabolism, drug resistance, and cell signaling using wide collection of tools, including 3D/organoid cell cultures, genetically-engineered and transplantation-based animal models, single-cell analysis, metabolomics, high-throughput microscopy, and other advanced technologies.

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

## Contents
  * [Project Overview](#project-overview)
  * [Publications](#publications)
  * [Data Stories](#data-stories)
  * [Explore Tissue Images](#explore-tissue-images)

## Project Overview
<div class="row mb-4">
  <div class="col-md-6 mb-4">
    {% include vimeo-card.html id="865802218" title="Breast Cancer Atlas with Dr. Joan Brugge" %}
  </div>
</div>

## Publications
{% comment %}
  'publicationList' should be a comma-delineated string of publication file names
{% endcomment %}
{% assign publicationList = 'luminal-breast-epithelial-cells-BRCA1-BRCA2-mutation-carriers-noncarriers-harbor-common-breast-cancer-copy-number-alterations,brca1-haploinsufficiency-promotes-early-tumor-onset-and-epigenetic-alterations-mouse-model-hereditary-breast-cancer,a-human-breast-atlas-integrating-single-cell-proteomics-and-transcriptomics' %}

{% include pub-list.html list=publicationList %}

### Data Stories
Data Stories are data visualizations that guide readers through the complexities of a large dataset through filters, search, or narrated image waypoints.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'gray-rosenbluth-selfers-2022/'"
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
    | where_exp: "item", "item.url contains 'gray-rosenbluth-selfers-2022/'"
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

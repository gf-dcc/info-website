---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: Devising new strategies to track and prevent breast cancer development in BRCA mutation carriers
    description: Dr. Joan Brugge’s laboratory studies the mechanisms of cancer initiation, progression, and drug resistance in breast, ovarian and other BRCA-related cancers. Specifically, Brugge’s team investigates tumor heterogeneity, cell-cell interactions, tumor microenvironment, cancer metabolism, drug resistance, and cell signaling using wide collection of tools, including 3D/organoid cell cultures, genetically-engineered and transplantation-based animal models, single-cell analysis, metabolomics, high-throughput microscopy, and other advanced technologies.

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

## Contents
  * [Project Overview Video](#project-overview)
  * [Team](#team)
  * [Research Questions](#research-questions)
  * [Sequencing](#sequencing)
  * [Explore Tissue Images](#explore-tissue-images)

## Project Overview

    {% include vimeo.html id="865802218" autoplay=true muted=true %}

### Team
  - Project Lead: Joan Brugge, PhD
  - Team: Aparicio, Dillon, Lin, Santagata, Garber, Venkitaraman

### Research Questions
  - How do basal and luminal breast cells contribute to BRCA-related cancers?
  - How do BRCA tumor cells evolve?
  - What are the molecular defects during tumor evolution?
  - How do we detection cancer evolution in carriers?
  - How do we intercept and eradicate tumor development?

## Sequencing

Single cell RNA sequencing data can be found on GEO: [GSE180878](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE180878).

{%
    assign stories = site.data-cards
    | where_exp: "item", "item.url contains 'gray-rosenbluth-selfers-2022/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Sequencing'"  %}

{% assign dataCardArray = '' | split: '' %}
{% for s in stories %}
  {% unless s.url contains '-overview' %}
    {% assign dataCardArray = dataCardArray | push: s %}
  {% endunless %}
{% endfor %}

{% if dataCardArray.size > 0 %}
  {% include cards.html cards=dataCardArray %}
{% endif %}

## Explore Tissue Images
**Access the minimally processed, unannotated Level 2 images associated with this publication. Click any of the following thumbnail images for an interactive view of the full-resolution images.**

{%
    assign stories = site.data-cards
    | where_exp: "item", "item.url contains 'gray-rosenbluth-selfers-2022/'"
    | where_exp: "item", "item.hide != true"
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

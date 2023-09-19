---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: Ovarian Serous Tubal Intraepithelial Carcinoma (STIC)

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

### Contents
* [Data Stories](#data-stories)
* [Explore Tissue Images](#explore-tissue-images)

## Data Stories
**Data Stories are narrated Minerva stories that guide readers through the complexities of a large image dataset via a series of progressive narrated waypoints.**

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'kadar-drapkin-ovarian-pilot/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'exploration'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

## Explore Tissue Images
**Access the minimally processed, unannotated Level 2 images associated with this publication. Click any of the following thumbnail images for an interactive view of the full-resolution images.**

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'kadar-drapkin-ovarian-pilot/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'overview'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

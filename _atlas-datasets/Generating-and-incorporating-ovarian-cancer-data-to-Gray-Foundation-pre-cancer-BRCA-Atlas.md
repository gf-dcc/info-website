---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: Investigating the origins and early diagnosis of ovarian cancer  
    description: "Ovarian cancer is more deadly on a per case basis than breast cancer and has witnessed fewer advances in treatment or diagnosis. In the US, 20,000 new diagnoses and 14,000 deaths from ovarian cancer are recorded per year; this contrasts with 240,00 new cases of breast cancer and 42,000 deaths. Like breast cancer, ovarian cancer is much more frequent in individuals who carry mutations in the BRCA1 or BRAC2 genes (an~1.2% vs 40% lifetime risk). Thus, BRCA1/2 carriers face the terrible choice of living with a high risk of cancer or undergoing surgery to remove healthy ovaries and fallopian tubes (risk-reducing salpingo-oophorectomy).

    One factor making the risk reduction decisions harder is that diagnosis of ovarian cancer is typically made late and the origins of the disease are poorly understood; this is also true of ovarian cancer in individuals who are not BRAC1/2 carriers. It has been discovered relatively recently that some epithelial ovarian cancers may arise in the fallopian tube, from a pre-cancerous lesion know as a serous tubal intraepithelial carcinoma (STIC). The goal of our project is to better characterize the biology of STICs to understand its clinical significance and develop precise criteria for diagnosing STICs in surgical samples. This is being performed using a range of genomic and spatial profiling tools that are expected to generate a data atlas as early as 2024. We expect these data to significantly impact how we treat people at risk for this terrible disease."

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

### Contents
* [Project Overview Video](#project-overview)
* [Data Stories](#data-stories)
* [Explore Tissue Images](#explore-tissue-images)

## Project Overview
<div class="col-md-6 mb-4">
  {% include vimeo-card.html id="866120650" title="Ovarian Cancer Atlas with Dr. Ronny Drapkin and Dr. Tanjina Kader" %}
</div>

## Data Stories
Data Stories are narrated Minerva stories that guide readers through the complexities of a large image dataset via a series of progressive narrated waypoints.

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
Access the minimally processed, unannotated Minerva stores of additional tissue images associated with this project. Click any of the following thumbnail images for an interactive view of the full-resolution images.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'kadar-drapkin-ovarian-pilot/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'overview'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

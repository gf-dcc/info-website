---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: "Advancing Breast Cancer Research: High-Plex Imaging and Single-Cell Profiling for Early Detection and Biomarker Discovery"
    description: "The HMS Gray team previously constructed a [comprehensive human breast atlas](https://www.graybrcaatlas.org/atlas-datasets/gray-rosenbluth-selfors-2022/) by integrating single-cell proteomics and transcriptomics, which revealed distinct epithelial subtypes linked to age, parity, and BRCA2 mutation status. A significant discovery from this work was the identification of basal-luminal (BL) alveolar cells, a hybrid cell population that expresses both basal/myoepithelial and luminal markers, demonstrating low transcriptional lineage fidelity. These cells accumulate with age, are regulated by TGFβ signaling, and exhibit gene expression profiles similar to basal-like breast cancers, suggesting a potential role in tumor initiation and progression. <br><br>

    Building on this research, the HMS team developed the Orion platform, a high-plex immunofluorescence imaging system capable of capturing same-section imaging of H&E-stained and multiplexed immunofluorescence (IF) imaging in whole-slide formats. By integrating immunofluorescence with traditional histology, we demonstrated its ability to enhance biomarker discovery for predicting disease progression. The findings underscore the promise of multimodal tissue imaging in improving diagnostic precision, prognostic accuracy, and biomarker development in oncology. <br><br>

    We are currently expanding our work by developing Orion panels to profile large cohorts of BRCA samples. The primary objective is to identify early-stage lesions using cutting-edge single-cell technology, which may pave the way for early detection strategies for BRCA-associated carcinogenesis and provide potential therapeutic insights for affected patients. In our pilot study, we successfully profiled 15 BRCA patient samples and 3 wild-type controls, using two distinct Orion panels followed by H&E histology. This dataset represents an unprecedented resource for understanding the biological and histological underpinnings of early cancer development, offering critical insights into BRCA-driven tumorigenesis."

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

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

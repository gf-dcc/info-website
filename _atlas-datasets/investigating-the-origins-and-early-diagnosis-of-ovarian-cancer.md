---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: Investigating the origins and early diagnosis of ovarian cancer  
    description: "Ovarian cancer presents a more formidable challenge per case than breast cancer, yet it has seen fewer advancements in treatment and diagnosis. In the United States, we observe approximately 20,000 new ovarian cancer diagnoses annually, which lead to 14,000 tragic deaths. This rate contrasts with breast cancer, which records around 240,000 new cases and 42,000 fatalities. Like breast cancer, ovarian cancer is more prevalent in individuals carrying mutations in the BRCA1 or BRCA2 genes (approximately 1.2% without vs. 40% with mutation). Consequently, people with a BRCA1/2 mutation face the agonizing decision of either living with an elevated ovarian cancer risk or undergoing surgery to remove their healthy ovaries and fallopian tubes, a procedure known as risk-reducing salpingo-oophorectomy.


    The decision to undergo risk reduction surgery is complicated by the fact that ovarian cancer is often diagnosed at late stages, and we have a limited understanding of its origins. However, recent insights have revealed that certain epithelial ovarian cancers may start in the fallopian tube from a pre-cancerous condition known as serous tubal intraepithelial carcinoma (STIC). Our project aims to characterize the biology of STICs, elucidate their clinical significance, and establish precise diagnostic criteria for identifying STICs in surgical samples."

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

### Contents
* [Project Overview](#project-overview)
* [Publications](#publications)
* [Data Stories](#data-stories)
* [Explore Tissue Images](#explore-tissue-images)

## Project Overview
<div class="row mb-4">
  <div class="col-md-6 mb-4">
    {% include vimeo-card.html id="866120650" title="Ovarian Cancer Atlas with Dr. Ronny Drapkin and Dr. Tanjina Kader" %}
    </div>
</div>

### Uncovering the origins of ovarian cancer
Ovarian cancer is a complex disease with diverse histological subtypes, each characterized by distinct molecular features, clinical presentations, and responses to therapy. High-Grade Serous Ovarian Cancer (HGSOC) stands out as one of the most common and aggressive subtypes, with a notably poor prognosis.

<details>
Conventionally, HGSOC was believed to originate directly from the ovaries. However, recent evidence (clinical, genetic, epigenetic, transcriptomic, and proteomic) has challenged this assumption, suggesting that the majority of HGSOCs arise from precursor lesions in the fallopian tube, specifically serous tubal intraepithelial carcinoma (STIC).
<br>
<br>
STICs are characterized by contiguous atypical epithelial cells that exhibit abnormal morphological features, including loss of polarity, nuclear pleomorphism, a high nuclear-to-cytoplasmic ratio, and increased mitotic activity. Microscopic STICs typically appear on the fallopian tube mucosa near the distal fimbriated ends, nearest to the ovaries.
<br>
<br>
Robust molecular studies, including next-generation sequencing and traditional histopathological analysis, have recently traced HGSOC mutations back to STIC lesions and features called “p53 signatures”. p53 signatures arise in the fallopian tube and are composed of secretory epithelial cells displaying intense p53 nuclear staining and harboring TP53 missense mutations. Intriguingly, p53 signatures appear morphologically identical to the adjacent non-TP53-mutated epithelium, implying that TP53 mutations alone are insufficient for transformation. These signatures preserve the epithelial layer while expanding and growing over time, leading to the development of serous tubal intraepithelial lesions (STIL), which retain some cell polarity. Ultimately, STIL is thought to progress into STIC, representing a precursor to HGSOC.
</details>

### What’s missing & how we plan to help
While previous studies have identified genetic events associated with the progression from STIC to HGSOC, such as TP53 mutations, chromosome 8q gain, and chromosome 17p loss, our understanding of the biology surrounding STIC lesions remains incomplete. A major objective of our project is to leverage patient specimens to investigate the progression from microscopic lesions in the fallopian tube to HGSOC.

<details>
To achieve this, we have assembled a substantial patient cohort, encompassing incidental p53 signatures and STIC lesions (some that exist without a concurrent carcinoma, others coexisting with HGSOC). We anticipate creating a data atlas as soon as 2024 that will include data from a range of genomic and spatial profiling tools. We expect these data to profoundly impact our approach to managing people at risk of this devastating disease.
<br>
<br>
Preliminary data from our cohort suggest that immune surveillance may break down at the precancerous stage, particularly in STIC lesions. This could contribute to tumor progression - our findings suggest that the immune system fails to recognize abnormal growth in the fallopian tube, allowing abnormal precancerous cells to persist.
<br>
<br>
Our long-term goal for this project is to extend the characterization of incidental precancers on a larger scale, offering a deeper understanding of the biology of STICs in surgical samples. Given that STICs are a well-known precursor to eventual peritoneal cancer, we intend to stratify the risk associated with STIC lesions for clinical decision-making. Additionally, our analysis of a substantial patient cohort has the potential to open avenues for preventive measures for high-risk patients in the future.
</details>
---
## Publications
{% comment %}
  'publicationList' should be a comma-delineated string of publication file names
{% endcomment %}
{% assign publicationList = 'multimodal-spatial-profiling-reveals-immune-suppression-and-microenvironment-remodeling-fallopian-tube-precursors-high-grade-serous-ovarian-carcinoma.md' %}

{% include pub-list.html list=publicationList %}
---

## Data Stories
Data Stories are narrated Minerva stories that guide readers through the complexities of a large image dataset via a series of progressive narrated waypoints.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'kader-drapkin-ovarian-pilot/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'narrated'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

## Explore Tissue Images
Access the minimally processed, unannotated Minerva stores of additional tissue images associated with this project. Click any of the following thumbnail images for an interactive view of the full-resolution images.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'kader-lin-hug-2024/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'curated'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

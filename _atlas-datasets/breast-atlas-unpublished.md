---
layout: secondary
title: Atlas Dataset
section_id: projects

data:
  publication:
    title: Identifying the Earliest Changes in Breast Tissues from BRCA Carriers Using Multi-Modal Single Cell Profiling
    description: The Gray Breast Atlas Team is using multiple cutting-edge technologies to profile normal human breast tissues at the single cell level to identify the earliest premalignant changes in breast tissues from women at high risk of developing breast cancer. This comprehensive approach makes it possible to detect rare subpopulations of cells that would otherwise be masked with bulk tissue analyses. The characterization of these rare premalignant cells will ultimately inform the development of strategies to detect and prevent the development of breast cancer.

---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

## Contents
  * [Data Overview](#data-overview)
  * [FLEX Single Cell RNA Sequencing](#flex-single-cell-rna-sequencing-of-normal-breast-tissues)
  * [3' 10X single cell RNA sequencing](#3-10x-single-cell-rna-sequencing-of-normal-breast-tissues)
  * [High-depth targeted DNA sequencing](#high-depth-targeted-dna-sequencing-of-normal-breast-tissues)
  * [Single cell DNA sequencing](#single-cell-dna-sequencing-of-normal-breast-tissues)
  * [Explore Tissue Images](#explore-tissue-images)

### Data Overview
Below are private links to data accessible by members of the Gray BRCA Atlas Team.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'breast-atlas-unpublished'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Overview'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

#### FLEX single cell RNA sequencing of normal breast tissues
[This dataset](https://singlecell.broadinstitute.org/single_cell/study/SCP2910) consists of 41 normal breast tissues from reduction mammoplasties or prophylactic mastectomies conducted at Harvard/DFCI, MGH and UPenn. The tissues were dissociated to single cells using a protocol optimized by the Brugge lab that improves yield of breast epithelial cells compared to previous protocols. The samples were sequenced by the DFCI Center for Functional Cancer Epigenetics Core using the FLEX protocol for 10X scRNAseq where cells can be fixed and stored to run in batches of 8 or 16 samples at a time. This protocol greatly improves transcript detection and cell capture rate while reducing batch effects and improving the logistics of our workflow. The resultant dataset is extremely high quality, with impressive uniformity in cluster representation across all the samples, which is not the case for existing large breast datasets published to date. Sequencing of additional samples is ongoing and this dataset will be updated in batches as more samples are completed. Our goal is to sequence 135 samples that are matched by genotype, age, parity and menopause status. This dataset currently consists of all cell types (epithelial lineages, immune cells, and stromal cells). We plan to generate a separate dataset consisting of all the epithelial cells and their subtypes. This work is ongoing.

#### 3' 10X single cell RNA sequencing of normal breast tissues  
[This dataset](https://singlecell.broadinstitute.org/single_cell/study/SCP2937) consists of 21 normal breast tissues from reduction mammoplasties or prophylactic mastectomies conducted at UPenn. The tissues were dissociated to single cells using the Nathanson lab protocol which robustly captures immune cells. The samples were sequenced by the Nathanson lab at UPenn using the Chromium 3 10X platform. Sequencing of additional samples is ongoing at UPenn.

#### High-depth targeted DNA sequencing of normal breast tissues
[This rich dataset](https://private.cbioportal.mskcc.org/) consists of 116 age-matched breast tissues from 61 women with high risk of developing breast cancer (24 BRCA1 carriers and 37 BRCA2 carriers) and 55 non-carriers from UPenn. The tissues were bulk sequenced by the Nathanson lab using a custom panel of 149 genes commonly altered in breast cancer. The list was curated from existing clinical panels and literature reviews. On average, a mean read depth of ~2300x was achieved. No samples had a mean read depth below 1000x.

#### Single cell DNA sequencing of normal breast tissues
The Brugge lab, in collaboration with the Aparicio and Shah groups, recently published [copy number alteration (CNA) landscape in normal breast tissues using single cell DNA sequencing](https://doi.org/10.1038/s41588-024-02018-9). This pioneering study analyzed the genomes of more than 48,000 individual breast cells from 28 women without cancer using single-cell DNA sequencing. This analysis identified common breast cancer-associated CNAs in rare cells of healthy women, pinpointing what could be the early genetic origins of breast cancer. These genetic alterations were detected at very low levels (in about 1-3% of breast cells) in almost all tissues and were only detected in the luminal breast epithelial cells that line lobules and ducts, not the contractile basal myoepithelial cells. This is an important finding because luminal cells are believed to be the cells of origin of all major types of breast cancer. Interestingly, the team identified breast cells with ‘extreme’ aneuploidy in women carrying BRCA1 and BRCA2 mutations. These cells may be further down the road in the cancer development process, suggesting a potential progression from normal cells to cancer-like cells in BRCA carriers. These findings can inform future efforts to devise novel, more effective prevention and monitoring strategies for those at high risk for developing breast cancer.


### Explore Tissue Images
The HMS team developed the Orion platform, a high-plex immunofluorescence imaging system capable of capturing same-section H&E-staining and multiplexed immunofluorescence (IF) imaging in whole-slide formats. In [an initial pilot study](/atlas-datasets/breast-orion-unpublished/), we successfully profiled breast tissues from 15 women with BRCA mutations and three non-carriers using two established Orion panels followed by H&E histology. This dataset represents a valuable foundation to begin to investigate the biological and histological underpinnings of early cancer development. We are currently working with the entire Gray Breast Atlas team to develop custom Orion panels of high value markers, informed by the findings from our single cell sequencing approaches, and to optimize integration of FISH probes to identify the cells with CNAs. Access the minimally processed, unannotated Level 2 Orion and H&E images. Click any of the following thumbnail images for an interactive view of the full-resolution images.

{%
    assign stories = site.data-cards
    | where_exp: "item", "item.url contains 'breast-orion-unpublished'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Orion'"
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

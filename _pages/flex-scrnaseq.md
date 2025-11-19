---
section_id: data
layout: secondary
permalink: /flex-scrnaseq/
title: FLEX Single Cell RNA Sequencing 10x
assay_instrument: "Here are some details about the assay, instruments on which the samples were run, etc."
data_access: |
  Access the data through:
  - GEO: FASTQ (Level 1) and BAM (Level 2)
  - AWS: H5 (Level 3)
  - or listed another way:
  - Level 1: FASTQ (GEO/TBD)
  - Level 2: BAM (GEO)
  - Level 3: H5 and RDS (AWS)

data_visualization: "Level 3 data can be explored on the [Broad Single Cell Portal](https://urldefense.proofpoint.com/v2/url?u=https-3A__singlecell.broadinstitute.org_single-5Fcell_study_SCP2937_gray-2Dpre-2Dcancer-2Datlas-2D3prime-2Dnew-2Dcutoff2&d=DwMCAg&c=WO-RGvefibhHBZq3fL85hQ&r=cweh-od9e4IKbwBn0LquQ1bd_4ItG3qeJdojjNJCWn4&m=rzG9BjtvHyOFzPaeLT1pYfgqZDvVmCqEMVfvVOsE6NjO_GiX_wcfnaXPHPJRGzkN&s=ci83bBuiB7y6ZeSoVd2D_y-Nx99ERSjTQF-Ukhrj6_Y&e=)"
protocol: "Link to protocol. Could also link to dissociation method protocol, etc."
samples: "60 normal breast tissue samples have currently been run and 135 samples planned."
data_generators: "This data was generated and analyzed by teams in the labs of Joan Brugge and Henry Long."
---
# FLEX Single Cell RNA Sequencing 10x

<a href="#about-the-data" class="button">About the Data</a>
<a href="#data-levels" class="button">Data Levels</a>
<a href="#data-visualization" class="button">Data Visualization</a>

This dataset consists of 60 normal breast tissues from reduction mammoplasties or prophylactic mastectomies conducted at Harvard/DFCI, MGH and UPenn. The tissues were dissociated to single cells using a protocol optimized by the Brugge lab that improves yield of breast epithelial cells compared to previous protocols. The samples were sequenced by the DFCI Center for Functional Cancer Epigenetics Core using the FLEX protocol for 10X scRNAseq where cells can be fixed and stored to run in batches of 8 or 16 samples at a time. This protocol greatly improves transcript detection and cell capture rate while reducing batch effects and improving the logistics of our workflow. The resultant dataset is extremely high quality, with impressive uniformity in cluster representation across all the samples, which is not the case for existing large breast datasets published to date.

Sequencing of additional samples is ongoing and this dataset will be updated in batches as more samples are completed. Our goal is to sequence 135 samples that are matched by genotype, age, parity and menopause status. This dataset currently consists of all cell types (epithelial lineages, immune cells, and stromal cells). We plan to generate a separate dataset consisting of all the epithelial cells and their subtypes. This work is ongoing.

## About the Data
{% include data-grid.html
   assay_instrument=page.assay_instrument
   samples=page.samples
   data_access=page.data_access
   data_visualization=page.data_visualization
   protocol=page.protocol
   data_generators=page.data_generators
%}
<br>

### Data Levels:


| Data Level  | Description | File Format | Data Access |
| ----- | -----------| --------- | --------- |
| Level 1: Raw sequences | Nucleotide sequence and quality scores | FASTQ | TBD |
| Level 2: Aligned sequences | sequencing data aligned to a reference genome | BAM | GEO |
| Level 3: Aggregated data | QC, analysis, and exploration of single-cell RNA-seq data | H5 and RDS | AWS |


<br>

## Data Visualization
Below are private links to data visualizations accessible by members of the Gray BRCA Atlas Team.
{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'breast-atlas-unpublished'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Overview'"
    | where_exp: "item", "item.tags contains 'FLEX'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

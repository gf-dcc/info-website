---
permalink: /snp-genotyping/
title: SNP Genotyping

section_id: data
layout: secondary

instrument: |
  Information Forthcoming
data_visualization: |
  Information Forthcoming

data_access: |
  Information Forthcoming
protocol: |
  GL DNA is extracted from blood. Samples are sequenced using the Illumina [Global Screening Array](https://www.illumina.com/science/consortia/human-consortia/global-screening-consortium.html).

samples: |
  The following are planned to be sequenced:
  - ~150-200 breast samples planned, with matching samples for FLEX, ATAC, and single cell RNA 3' forthcoming
data_generators: "This data was generated and analyzed by a team in the lab of Kate Nathanson."
---
# SNP Genotyping

<a href="#about-the-data" class="button">About the Data</a>
<a href="#data-levels" class="button">Data Levels</a>
<a href="#data-visualization" class="button">Data Visualization</a>

## About the Data
{% include data-grid.html
   instrument=page.instrument
   samples=page.samples
   data_access=page.data_access
   data_visualization=page.data_visualization
   protocol=page.protocol
   data_generators=page.data_generators
%}
<br>

### Data Levels:


Information forthcoming.


<br>

## Data Visualization
Below are private links to data visualizations accessible by members of the Gray BRCA Atlas Team.
{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'breast-atlas-unpublished'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Overview'"
    | where_exp: "item", "item.tags contains 'snp'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

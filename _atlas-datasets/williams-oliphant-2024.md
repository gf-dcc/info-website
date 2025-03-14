---
layout: secondary
title: Atlas Dataset
section_id: publications

data:
  publication:
    title: Luminal breast epithelial cells of BRCA1 or BRCA2 mutation carriers and noncarriers harbor common breast cancer copy number alterations
    authors: 'Williams MJ, Oliphant MUJ, Au V, Liu C, Baril C, O’Flanagan C, Lai D, Beatty S, Van Vliet M, Yiu JC, O’Connor L, Goh WL, Pollaci A, Weiner AC, Grewal D, McPherson A, Norton K, Moore M, Prabhakar V, Agarwal S, Garber JE, Dillon DA, Shah SP, Brugge JS, Aparicio S'
    journal: 'Nature Genetics. 2024 November 20; 56, 2753–2762. DOI: [10.1038/s41588-024-01988-0](https://doi.org/10.1038/s41588-024-01988-0)'
    description: The prevalence and nature of somatic copy number alterations (CNAs) in breast epithelium and their role in tumor initiation and evolution remain poorly understood. Using single-cell DNA sequencing (49,238 cells) of epithelium from BRCA1 and BRCA2 carriers or wild-type individuals, we identified recurrent CNAs (for example, 1q-gain and 7q, 10q, 16q and 22q-loss) that are present in a rare population of cells across almost all samples (n = 28). In BRCA1/BRCA2 carriers, these occur before loss of heterozygosity (LOH) of wild-type alleles. These CNAs, common in malignant tumors, are enriched in luminal cells but absent in basal myoepithelial cells. Allele-specific analysis of prevalent CNAs reveals that they arose by independent mutational events, consistent with convergent evolution. BRCA1/BRCA2 carriers contained a small percentage of cells with extreme aneuploidy, featuring loss of TP53, BRCA1/BRCA2 LOH and multiple breast cancer-associated CNAs. Our findings suggest that CNAs arising in normal luminal breast epithelium are precursors to clonally expanded tumor genomes.


---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}

<a href="https://doi.org/10.1038/s41588-024-01988-0" class="button">Publication</a>
<a href="https://ega-archive.org/studies/EGAS00001007716" class="button">EGA</a>

## Contents
* [Data Access](#data-access)

### Data Access
Access Single-Cell Whole Genome Sequencing (DLP+ scWGS) data associated with this publication.

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'williams-oliphant-2024/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'Overview'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}

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

Ovarian cancer presents a more formidable challenge per case than breast cancer, yet it has seen fewer advancements in treatment and diagnosis. Annually in the United States, we observe approximately 20,000 new ovarian cancer diagnoses, leading to 14,000 tragic deaths. This contrasts starkly with breast cancer, which records around 240,000 new cases and 42,000 fatalities. Remarkably, ovarian cancer shares a commonality with breast cancer, being more prevalent in individuals carrying mutations in the BRCA1 or BRCA2 genes, albeit with significantly varying lifetime risks (approximately 1.2% vs. 40%). Consequently, BRCA1/2 mutation carriers face the agonizing decision of either living with an elevated cancer risk or undergoing prophylactic surgery to remove healthy ovaries and fallopian tubes, a procedure known as risk-reducing salpingo-oophorectomy.

Complicating these risk-reduction decisions is the late-stage diagnosis typically associated with ovarian cancer and a limited understanding of its origins, a dilemma applicable not only to BRCA1/2 carriers but also to individuals without these mutations. Recent insights have revealed that certain epithelial ovarian cancers may actually originate in the fallopian tube, specifically from a pre-cancerous condition known as serous tubal intraepithelial carcinoma (STIC). Our project's primary aim is to comprehensively characterize the biology of STICs, elucidate their clinical significance, and establish precise diagnostic criteria for identifying STICs in surgical samples.


## The Details

Specifically, ovarian cancer is a complex disease with diverse histological subtypes, each characterized by distinct molecular features, clinical presentations, and responses to therapy. High-Grade Serous Ovarian Cancer (HGSOC) stands out as one of the most common and aggressive subtypes, with a notably poor prognosis. Conventionally, HGSOC was believed to originate directly from the ovaries. However, recent clinical, genetic, epigenetic, transcriptomic, and proteomic evidence has challenged this assumption, suggesting that the majority of HGSOCs arise from precursor lesions in the fallopian tube, specifically STICs. These microscopic STICs typically appear on the fallopian tube mucosa near the distal fimbriated ends, nearest to the ovaries. STICs are characterized by contiguous atypical epithelial cells exhibiting abnormal morphological features, including loss of polarity, nuclear pleomorphism, a high nuclear-to-cytoplasmic ratio, and increased mitotic activity. Another related fallopian tube lesion is the p53 signature, composed of benign-appearing secretory cells displaying intense p53 nuclear staining and harboring TP53 missense mutations. Intriguingly, p53 signatures appear morphologically identical to adjacent non-TP53-mutated epithelium, implying that TP53 mutations alone are insufficient for transformation. Advanced molecular studies, including next-generation sequencing, have traced HGSOC mutations back to p53 signatures and STIC lesions.  Together with robust histopathological data, HGSOC is now believed to originate from fallopian tube secretory cells harboring TP53 mutations, initially manifesting as "p53 signatures." These signatures preserve the epithelial layer while expanding and growing abruptly over time, leading to the development of serous tubal intraepithelial lesions (STIL) that retain some cell polarity. Ultimately, STIL is thought to progress into STIC, representing a precursor to HGSOC.

### Project Details
While previous studies have identified genetic events associated with the progression from STIC to HGSOC, such as TP53 mutations, chromosome 8q gain, and chromosome 17p loss, our understanding of the biology surrounding STIC lesions remains incomplete. A major objective of our project is to leverage patient specimens and investigate the progression from microscopic lesions in the fallopian tube to HGSOC. To achieve this, we have assembled a substantial patient cohort, encompassing incidental p53 signatures and STIC lesions (discovered without concurrent carcinoma) as well as STIC lesions coexisting with HGSOC. Employing a range of genomic and spatial profiling tools, we anticipate creating a data atlas by as early as 2024. We expect these data to profoundly impact our approach to managing women at risk of this devastating disease.

Preliminary data from our cohort hints at a breakdown in immune surveillance at the precancerous stage, particularly in STIC lesions, which could contribute to tumor progression. Our findings suggest that our immune system fails to recognize abnormal growth in the fallopian tube, allowing abnormal precancerous cells to persist.
Our long-term goal for this project is to extend the characterization of incidental precancers on a larger scale, offering a deeper understanding of the biology of STICs in surgical samples. STICs are well-known precursors to peritoneal cancer that emerges later in life. Our intention is to stratify the risk associated with STIC lesions for clinical decision-making. Moreover, analyzing a substantial cohort holds the promise of opening up avenues for preventive measures for high-risk patients in the future.

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

---
layout: secondary
title: Atlas Dataset
section_id: publications

data:
  publication:
    title: Sample Publication Entry
    authors: 'Author Name 1, Author Name 2, Author Name 3, Author Name 4'
    journal: 'Nature Cancer (2023). DOI: [10.1038/s43018-023-00576-1](https://doi.org/10.1038/s43018-023-00576-1)'
    description: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris erat felis, pulvinar vehicula vestibulum at, laoreet at dui. Quisque commodo, neque et fermentum auctor, ipsum nisl luctus est, auctor pretium ipsum dolor eu urna. Maecenas ultrices quis justo ut aliquet. Suspendisse luctus turpis dolor, accumsan iaculis felis lacinia vel. Duis cursus dui et ultricies porttitor. Sed convallis elementum dolor nec congue. Etiam orci nibh, pretium sed nunc quis, ultricies hendrerit massa. Nulla ante elit, vulputate nec nibh et, malesuada pulvinar dui. Integer bibendum ullamcorper magna mattis tempor.
    links:
      - Publication: https://doi.org/10.1038/s43018-023-00576-1
      - bioRxiv: https://doi.org/10.1101/2022.09.28.509927
      - Dataset: https://doi.org/10.5281/zenodo.7637655
      - Colorectal Cancer Atlas: /atlases/colorectal-cancer
---

{% assign urlParts = page.url | split: '/' %}
{% assign sectionId = urlParts[-1] %}

{% include atlas-dataset-info.html
    sectionId=sectionId
    pubData=page.data
    thumbnailDir=sectionId %}


### Key Findings:
- Quisque ac neque maximus, condimentum ex at, euismod massa. Donec eu porttitor justo, non mollis ante

- Quisque consequat ante sem, eu sollicitudin neque fermentum sit amet. In tincidunt convallis felis, id feugiat massa placerat eu

- Nulla quis turpis tempor metus viverra bibendum. Phasellus et egestas nulla, nec tempor dui

- Integer viverra odio nunc, et interdum tellus pulvinar quis. Aenean posuere dapibus orci ut gravida

{% include enlarge-image.html src='publications/High-plex-immunofluorescence-imaging-and-traditional-histology-of-the-same-tissue-section-for-discovering-image-based-biomarkers.jpg' float='center' alt='' %}

<i> **Top:** Overview of the Orion method for same-slide immunofluorescence and H&E imaging. **Bottom:** Example images of a colorectal cancer specimen from Orion, showing the multiplex immunofluorescence image (left; 5 of 18 fluorescence channels shown), the corresponding same-section H&E image (center), and the overlay of these two images (right). </i>


### Contents
* [Data Explorations](#data-explorations)
* [Data Overviews](#data-overviews)
* [Data Access](#data-access)

### Data Explorations

{%
    assign stories = site.data-cards
    | where_exp: "item", "item.url contains 'keenan-2020/'"
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

### Data Overviews

**NOTE! These Data Overviews provide access to minimally processed
Level 2 images with no annotation or quality control. Click any of the
following thumbnail images for an interactive view of the
full-resolution images.**

{%
    assign overviews = site.data-cards
    | where_exp: "item", "item.url contains 'lin-chen-campton-2023/'"
    | where_exp: "item", "item.hide != true"
    | where_exp: "item", "item.tags contains 'overview-crc'"
%}

{% if overviews.size > 0 %}
  {% include cards.html cards=overviews %}
{% endif %}


## Data access

Pellentesque varius turpis et felis consectetur feugiat. Sed quis ex vel lectus molestie fringilla at eget quam. Nam feugiat, nunc id consectetur dapibus, purus leo efficitur est, et iaculis erat ipsum quis erat.

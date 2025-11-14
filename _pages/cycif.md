---
title: CyCIF
permalink: /cycif/

section_id: data
layout: secondary

assay_instrument: "High-plex image data is collected using cyclic immunofluorescence ([CyCIF method](https://www.tissue-atlas.org/cycif-method)) on RareCyte CyteFinder (CF46) and CyteFinder II microscopes."
data_generators: "This data was generated and analyzed by the Laboratory of Systems Pharmacology at Harvard Medical School."
data_access: |
  All image data can be accessed and downloaded from AWS:
  - Level 1: rcpnl (AWS)
  - Level 2: OME-TIFF (AWS)
  - Level 3: OME-TIFF (AWS)
  - Level 4: csv (AWS)

data_visualization: "Image data can be explored in full resolution via [Minerva](https://www.minerva.im/), which can be explored below or in cBioPortal."
protocol: "View the CyCIF protocol on [protocols.io](dx.doi.org/10.17504/protocols.io.5qpvorbndv4o/v2)."
samples: "50-100 breast samples and 30-50 ovarian samples will be imaged with CyCIF."
---

# Cyclic Immunofluorescence (CyCIF) Multiplexed Imaging

We are committed to making our spatial profiling data available to the scientific community. Here you will find information describing the various imaging data types and how they are collected, analyzed, and shared.
<br>
<a href="#about-the-data" class="button">About the Data</a>
<a href="#public-access-to-primary-data" class="button">Primary Data Access</a>
<a href="#about-minerva-viewing-image-data-online" class="button">Minerva: Viewing Data Online</a>
<a href="#data-standards-for-highly-multiplexed-tissue-images" class="button">Image Data Standards</a>

## About the Data

<br>

{% include data-grid.html
   assay_instrument=page.assay_instrument
   samples=page.samples
   data_access=page.data_access
   data_visualization=page.data_visualization
   protocol=page.protocol
   data_generators=page.data_generators
%}
<br>

### CyCIF Data Levels:

CyCIF uses OME-TIFF and other [BioFormats](https://www.openmicroscopy.org/bio-formats/) file formats and follows MITI standards. See [Image Data Standards](#data-standards-for-highly-multiplexed-tissue-images), below, for more information.

| Data Level  | Description | File Format |
| ----- | -----------| --------- |
| Level 1: Raw images | Collected using cyclic immunofluorescence ([CyCIF](https://www.tissue-atlas.org/cycif-method)) | rcpnl  |
| Level 2: High-plex image data | Quality controlled images are assembled into a high-plex whole slide image using the [MCMICRO](https://mcmicro.org/) analysis pipeline | OME-TIFF or other [BioFormats](https://www.openmicroscopy.org/bio-formats/) file type. |
| Level 3: Segmentation masks | Cell segmentation identifies and separates cell, nucleus, cytoplasm and other regions  | OME-TIFF |
| Level 4: Single-cell spatial feature tables | Summarize the expression of marker intensities and morphological features for each cell | csv |

---

## PUBLIC ACCESS TO PRIMARY DATA

As there is no funding-agnostic public repository available to accept whole slide tissue image data, images and metadata are available in an Amazon Web Services (AWS) S3 bucket. For up-to-date instructions on how to download image data found on this website, please visit our access instructions on Zenodo ([DOI: 10.5281/zenodo.10223574](https://doi.org/10.5281/zenodo.10223574)). Email tissue-atlas(at)hms.harvard.edu if you have questions or experience issues.

<br>

---

## About Minerva: Viewing image data online

Accessing terabyte-size full-resolution image data is impractically burdensome for browsing a large dataset, so we have developed a specialized browsing tool, [Minerva](https://www.minerva.im/), to enable panning and zooming across large images using a standard web browser.

[Minerva](https://www.minerva.im/) is a suite of software tools for visualizing, annotating, and sharing high-plex tissue images in a browser with an accompanying [narration](https://www.nature.com/articles/s41551-021-00789-8). Minerva makes it possible to interact with large, whole-slide images without downloading any data or installing any software. Minerva can also be used to share image annotations and display additional types of data visualizations. Nearly all Harvard Tissue Atlas data are available as one of three types of Minerva-based visualizations, described below.
<br>

### Narrated Minerva Stories
{% include narrated-minerva-description.md %}
{%
    assign stories = site.data-cards
    | where_exp: "item", "item.hide != true"
%}

{% assign dataCardArray = '' | split: '' %}
{% for s in stories %}
  {% if s.tags contains 'Overview' %}
    {% assign dataCardArray = dataCardArray | push: s %}
  {% endif %}
{% endfor %}

{% if dataCardArray.size > 0 %}
  {% include cards.html cards=dataCardArray %}
{% endif %}

### Curated Minerva Stories
{% include curated-minerva-description.md %}

{%
    assign stories = site.data-cards
    | where_exp: "item", "item.hide != true"
%}

{% assign dataCardArray = '' | split: '' %}
{% for s in stories %}
  {% if s.tags contains 'curated' %}
    {% assign dataCardArray = dataCardArray | push: s %}
  {% endif %}
{% endfor %}

{% if dataCardArray.size > 0 %}
  {% include cards.html cards=dataCardArray %}
{% endif %}

### Automated Minerva Stories
Automated Minerva stories provide a single, minimally-processed ([Level 2 or 3](/data-standards#data-levels)) whole slide image with no annotation or analysis. Automated stories provide online viewing access to largely unprocessed image data. These stories can be made automatically as part of the [MCMICRO](https://mcmicro.org/) pipeline.

  <a href="/data-explorations" class="arrow-button">Explore image data</a>

<br>

---

## Data Standards for Highly Multiplexed Tissue Images
We developed a standard for multiplexed tissue imaging called [Minimum Information about highly multiplexed Tissue Imaging (MITI)](https://www.miti-consortium.org/).

### MITI Data Levels
MITI adopted the concept of Data Levels from [dbGAP](https://www.ncbi.nlm.nih.gov/gap/) to manage image data and the corresponding spatial profiles. Higher data levels are more processed. See the [MITI publication](https://pubmed.ncbi.nlm.nih.gov/35277708/) for additional details and background information.

#### Level 1: Raw Image Tiles
Whole slide imaging usually involves acquisition of ~100 to 1,000 individual image tiles, each collected from a different X and Y location.

#### Level 2: Assembled Images
Full-resolution images have undergone automated stitching, registration, illumination correction, background subtraction, intensity normalization, and have been stored in a standardized OME format.  

To achieve this, Level 1 image tiles are combined at sub-pixel accuracy into a mosaic image in a process known as [stitching](https://labsyspharm.github.io/ashlar/). When high-plex images are assembled from multiple rounds of lower-plex imaging, it is also necessary to register channels to each other across imaging cycles and to correct for any unevenness in illumination (so-called flat fielding). Stitched and registered mosaics can be as large as 50,000 x 50,000 pixels x 100 channels, requiring ~500 GB of disk space.

#### Level 3: Image Assembly and Segmentation Masks
Level 3 data represent images that have been processed with some interpretive intent. Interpretive intent may include (i) full-resolution images following quality control or artifact removal, (ii) segmentation masks computed from such images, (iii) machine-generated spatial models, and (iv) images with human or machine-generated annotations. A primary goal of the Harvard Tissue Atlas is to distribute level 3 data.

#### Level 4: Spatial Features Tables
Level 4 data comprise features derived from level 3 images, most commonly single-cell features in “spatial feature tables” that describes marker intensities, cell coordinates, and other single-cell features.

#### Level 5: Higher Level Data Representations
Level 5 data includes results computed from spatial feature tables or primary images. This can include images presented in image viewers like Minerva.

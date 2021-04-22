---
layout: default
nav_order: 1
toc: true
---
# UnMICST - Universal Models for Identifying Cells and Segmenting Tissue <br>
![](/images/unmicstbannerv2.png) <br>
<p align="center"> 
  (pronounced un-mixed)
</p>

## Introduction
Nuclei segmentation, especially for tissues, is a challenging and unsolved problem. Convolutional neural networks are particularly well-suited for this task: separating the foreground class (nuclei pixels) from the background class. UnMICST generates probability maps where the intensity at each pixel defines how confident the pixel has been correctly classified to the aforementioned classes. These maps can make downstream image binarization more accurate using tools such as s3segmenter. https://github.com/HMS-IDAC/S3segmenter. UnMICST currently uses the UNet architecture (Ronneberger et al., 2015) but Mask R-CNN and Pyramid Scene Parsing (PSP)Net are coming very soon! **The concept, models, and training data are featured here: https://www.biorxiv.org/content/10.1101/2021.04.02.438285v1 **

![](/images/probmaps.png)
The HTA CRC Atlas 1 dataset contains images and other data being used for
construction of an atlas of human colorectal cancer under the auspices of the
[Human Tumor Atlas Network](https://humantumoratlas.org/). Advanced solid
cancers are complex assemblies of tumor, immune, and stromal cells that invade
adjacent tissue and spread to distant sites. We use highly multiplexed tissue
imaging, spatial statistics, and machine learning to identify cell types and
states underlying morphological features of known diagnostic and prognostic
significance in colorectal cancer. This includes the tumor invasive margin,
where tumor, normal, and immune cells compete and were diverse immunosuppressive
environments are found.

## Contents
* [Data Overviews](#data-overviews)
* [Data Explorations](#data-explorations)
* [About Minerva](#about-minerva)


## Data overviews

**NOTE! These Data Overviews provide access to minimally processed
Level 2 images with no annotation or quality control. Click any of the
following thumbnail images for an interactive view of the
full-resolution images.**


<figure class="figure-story">
  <a href="{{ site.baseurl }}{% link stories/crc01-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc01-overview.jpg">
    <figcaption>CRC01</figcaption>
  </a>
</figure>

<div style="display: flex; flex-wrap: wrap;">

<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc02-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc02-overview.jpg">
    <figcaption>CRC02</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc03-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc03-overview.jpg">
    <figcaption>CRC03</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc04-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc04-overview.jpg">
    <figcaption>CRC04</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc05-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc05-overview.jpg">
    <figcaption>CRC05</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc06-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc06-overview.jpg">
    <figcaption>CRC06</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc07-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc07-overview.jpg">
    <figcaption>CRC07</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc08-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc08-overview.jpg">
    <figcaption>CRC08</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc09-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc09-overview.jpg">
    <figcaption>CRC09</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc10-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc10-overview.jpg">
    <figcaption>CRC10</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc11-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc11-overview.jpg">
    <figcaption>CRC11</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc12-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc12-overview.jpg">
    <figcaption>CRC12</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc13-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc13-overview.jpg">
    <figcaption>CRC13</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc14-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc14-overview.jpg">
    <figcaption>CRC14</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc15-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc15-overview.jpg">
    <figcaption>CRC15</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc16-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc16-overview.jpg">
    <figcaption>CRC16</figcaption>
  </a>
</figure></div>
<div><figure class="figure-story figure-story-grid">
  <a href="{{ site.baseurl }}{% link stories/crc17-overview.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc17-overview.jpg">
    <figcaption>CRC17</figcaption>
  </a>
</figure></div>

</div>

## Data Explorations

<figure class="figure-story">
  <a href="{{ site.baseurl }}{% link stories/crc01-introduction.md %}">
    <img src="{{ site.baseurl }}/images/thumbnail-crc01-introduction.jpg">
    <figcaption>CRC01 introduction</figcaption>
  </a>
</figure>

{::comment}
[CRC01 Z-stack <br> ![](images/thumbnail-crc01-stack.jpg){:width="400px" height="391px"}]({{ site.baseurl }}{% link stories/crc01-stack.html %})
{:/comment}

## About Minerva
### Exploring the primary image data in Lin-Wang-Sorger et al.

The images in Lin et al. (2021) comprise a ~4.5 TB dataset with some images as
large as 1 gigapixel.  We provide access to this information without restriction
(as required by the NCI Moonshot effort) but it is not in a convenient form for
reviewers or general users to explore. The open source Minerva software was
designed for the [Human Tumor Atlas Network
(HTAN)](https://humantumoratlas.org/) by the Laboratory of Systems Pharmacology
to address this problem.

Minerva enables intuitive real-time exploration of very large (gigapixel)
high-plex images in the cloud using a web browser. With Minerva, users can pan
around and magnify areas of an image and switch between channels. Minerva does
not require the installation of any software and is therefore secure; browsing
is also anonymous. Users interested in the tool are welcome to explore the
[documentation](https://github.com/labsyspharm/minerva-story/wiki), the
[software publication](https://joss.theoj.org/papers/10.21105/joss.02579), and a
description of [digital
docents](https://www.biorxiv.org/content/10.1101/2020.03.27.001834v2) in
general.

We provide two types of Minerva stories with this paper:

1. “*Data Overviews*” provide access to minimally processed Level 2 images with
   annotation and interpretation kept to a bare minimum.
2. “*Data Explorations*” are like museum guides and exploit the digital docents
   in Minerva to guide readers through the complexities of a large image dataset
   via a series of narrated stories and waypoints. Both written and audio
   narration are supported, as well as free exploration. These will be linked to
   individual figure panels in the final manuscript.

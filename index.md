---
layout: default
nav_order: 1
toc: true
---
# UnMICST - Universal Models for Identifying Cells and Segmenting Tissue <br>
![](/images/unmicstbannerv2.jpg) <br>
<p align="center"> 
  (pronounced un-mixed)
</p>

## Introduction
Nuclei segmentation, especially for tissues, is a challenging and unsolved problem. Convolutional neural networks are particularly well-suited for this task: separating the foreground class (nuclei pixels) from the background class. UnMICST generates probability maps (in the case of semantic segmentation) where the intensity at each pixel defines how confident the pixel has been correctly classified to the aforementioned classes, and bounding boxes with binary masks (instance segmentation). 
![](/images/probmaps.png)

## Contents
* [Training data and models](#downloading-training-data-and-models)
* [Data Overviews](#data-explorations)
* [About Minerva](#about-minerva)

## Downloading training data and models
We provide training data, annotations and models that can be freely downloaded here: https://www.dropbox.com/sh/3aqp83f5w1pxk0y/AABFgNRMJD2EvfSLFgCrXrBba?dl=0<br>
`/models` contains UNet, Mask RCNN and PSPNet model files. Also included are scripts to either train or run specific models where the filename indicates the training scenario. Ie. DNA_NES_Aug indicates the model has been trained with DNA, the nuclear envelope staining and real augmentation. DNA_NoAug indicates the model was only trained on the DNA channel.<br>
<br>
`/training data` contains a .rar file with the training, validation, and test data used to train the aforementioned UNet, Mask RCNN, and PSPNet models. <br>
<br>
`compiledTrainingExamples.rar` contains the raw images and annotated labels prior to splitting into tiles and into a train/validation/test split. Approximately 10,400 nuclei from 7 tissue types (normal ovary, small intestine, tonsil, and cancers of colon, brain, lung, and prostate) were manually annotated.<br>

### Parameter list
1. `--outputPath` : specify where to save the output files
2. `--channel` : specify the channel(s) to be used. For DNA only models, only one channel should be specified. For DNA_NES models, use 2 channels ie. `--channel 0 3`
3. `--scalingFactor` : an upsample or downsample factor if your pixel sizes are mismatched from the dataset.

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
### Exploring the primary image data in Yapp et al. (2021)

Yapp et al. (2021) contains a TMA core image that is over 1 GB. As part of the review process for this manuscript, we provide access to this data in the form of a Minerva story, a convenient and open source Minerva software designed for the [Human Tumor Atlas Network
(HTAN)](https://humantumoratlas.org/) by the Laboratory of Systems Pharmacology.

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

We provide a Minerva story with this paper to provide access to minimally processed Level 2 images with annotation and interpretation kept to a bare minimum.





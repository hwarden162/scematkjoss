---
title: 'SCEMATK: Single Cell Morphological Profiling in Whole Slide Images'
tags:
  - Python
  - digital pathology
  - morphological profiling
authors:
  - name: Hugh Warden
    orcid: 0000-0002-4308-7316
    affiliation: 1
  - name: Jesko Wagner
    orcid: 0000-0001-9805-7192
    affiliation: 1
  - name: Ava Khamseh
    orcid: 0000-0001-5203-2205
    corresponding: true
    affiliation: "1, 2"
affiliations:
 - name: MRC Human Genetics Unit, Institute of Genetics and Cancer, University of Edinburgh, Edinburgh, UK
   index: 1
 - name: School of Mathematics, University of Edinburgh, Edinburgh, UK
   index: 2
date: 02 February 2025
bibliography: paper.bib
---

# Summary

Digital pathology is an important field of study for fast an accurate diagnostic processes as well as for structural analysis of diseased tissue. These large high resolution images are then shared amongst pathologists and annotated, however recently it there has been a lot of work to apply machine learning to these images to perform common diagnostic and investigative work. Due to the large size of the images, this requires a lot of technical expertise and computational resources to open and analyse these images. SCEMATK (Single Cell Extraction and Morhorphological Analysis Tool-Kit) provides an efficient way to open and convert digital pathology images into a phenotypic data set of morphological features that can then have machine learning techniques applied to them that do not take images as input. Furthermore, SCEMATK focuses on the processing patches uniformly, allowing for the spatial analysis of the morphology of cells between patches to capture greater information about larger tissue structure. All of these processes can be run interactively in a Jupyter notebook, allowing for easy manipulation of images too large to fit into memory.

# Statement of Need

Due to the large size of digital pathology whole slide images (WSIs), substantial computational resources are required to load, process, and analyse these data. Existing open source tools typically do not focus primarily on the morphological profiling of these images. QuPath provides comprehensive tools for image viewing, annotation and cell detection [cite{QuPath}]. It can perform some morphological profiling however more complex analytical workflows require a steep learning curve. Other software focuses on preparing WSIs for machine learning using efficient tiling and patch extraction strategies [cite{TIAToolbox, HistomicsTK, SlideFlow, SlideTiler}]. Although some of these tools support morphological profiling, the independent processing of tiles can introduce inconsistencies when calculating spatial statistics.

SCEMATK addresses this gap by providing a unified, easily extensible interface for image preprocessing, object segmentation, and morphological profiling, implemented using lazy-loading strategies. This design enables efficient analysis on standard personal computers while remaining scalable to high-performance computing environments. In contrast to existing morphological profiling tools, SCEMATK applies image transformations consistently across the entire slide prior to feature extraction, allowing computation of spatial statistics that characterise the local distribution of phenotypes within each cell’s neighbourhood.

[incluce{image-tbd}]

SCEMATK provides these basic tools for analysing images: 

- Image Viewing: Enables the user to view a thumbnail of an image or a specify a region to view in full resolution.
- Image Normalisation: Apply a colour transform to the image to fit that of a target image, combatting batch effects that may arise from differences in staining protocols between samples.
- Stain Deconvolution: Convert the image from RGB to a new colour space showing the intensities of different stains applied to the sample, indicating different biological properties of the tissue.
- Object Segmentation: Identify nuclei of cells within an image as well as an approximation of the cell and cytoplasm.
- Morphological Profiling: Convert the masks and deconvolved image into a table of morphological properties of each cell.

SCEMATK provides an all in one easy to use interface for carrying out single cell morphological profiling on digital pathology images with limited computational resources.

# Acknowledgements

HW and JW are funded by an MRC Unit Award.

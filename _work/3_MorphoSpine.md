---
layout: work
title: "MorphoSpine"
description: "An automated image processing system for segmenting and labeling vertebrae from spinal X-ray images."
image: "https://placehold.co/1000x600/cddeff/white?text=MorphoSpine"
year: "2024"
role:
emoji: "🩻"
month_season: "December"
for: 
team: 
advisors: "Rajalida Lipikorn"
tool: 
order: "3"
display: true
---

**MorphoSpine** is an image processing project developed as part of an Image Processing course (December 2024). The goal was to design a fully automated system that can read spinal X-ray images, isolate the spine, segment individual vertebrae, and save each vertebra as a separate image file labeled by its anatomical position (e.g., C1, T2, L3), without manual adjustment between images.

## Project Overview

The system processes grayscale spinal X-ray images and removes non-spinal regions before identifying and separating individual vertebrae. A key constraint of the assignment was robustness: the program should work across multiple X-ray samples without requiring parameter tuning or code changes. This requirement guided the design toward classical, morphology-based image processing techniques rather than learning-based methods.

## Technical Approach

MorphoSpine employs a structured image processing pipeline including thresholding, morphological operations, and connected component analysis. Morphological filtering is used to suppress noise and non-bone structures while preserving the continuity of the spinal column. Connected component labeling and region property analysis are then applied to detect vertebral candidates and automatically extract bounding boxes for each vertebra. Each segmented vertebra is cropped from the original image and saved as an individual JPG file.

## What I Learned

This project strengthened my understanding of **classical computer vision and medical image processing**, particularly the use of morphological operations for structural segmentation. I learned how to design rule-based pipelines that generalize across varying image conditions, an essential skill when annotated data or deep learning approaches are not feasible.

I also gained experience in translating a high-level problem statement into a robust, end-to-end system, balancing algorithmic simplicity with practical reliability. The project reinforced the importance of designing automated solutions that are reproducible, interpretable, and suitable for real-world imaging constraints.

Overall, MorphoSpine represents my ability to apply foundational image processing techniques to a challenging biomedical task, emphasizing robustness, automation, and clarity of design.

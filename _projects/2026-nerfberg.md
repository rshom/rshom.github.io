---
permalink: /nerfberg
created: 2026-02-01
date: 2026-02-01
updated: 2026-11-08
title: NeRFBerg
published: true
abstract: >-
  Iceberg drift and deterioration models run on rough size and shape
  estimates from satellite and aerial reconnaissance. This project
  reconstructs iceberg sails in 3D from consumer drone video using neural
  radiance fields (NeRF) and compares the results against traditional
  structure from motion (SfM) and multi-view stereo (MVS) photogrammetry.
  On two icebergs in Disko Bay, Greenland, NeRF gave higher structural
  similarity, more coherent meshes, and sail volumes within 2-10% of MVS,
  using an open-source pipeline on commercial off-the-shelf hardware. The
  work is a collaboration between URI, the University of Maryland, the
  University of Bergen, and the University of Washington Applied Physics
  Laboratory.
research:
  - label: "Paper: Neural Radiance Field Applications for Geometric Reconstruction of Arctic Icebergs"
    note: "OCEANS 2026 Monterey, McKenzie et al. (DOI pending)"
  - label: "Code: Neural radiance field pipeline for iceberg reconstruction"
    url: https://github.com/lmckenzie99/Neural-Radiance-Field-Applications-for-Geometric-Reconstruction-of-Arctic-Icebergs--OCEANS-2026
    note: "GitHub, L. McKenzie et al."
  - label: "Data: Disko Bay 2025 iceberg drift tracks"
    url: https://iabp.apl.uw.edu/DiskoBay_2025.html
    note: "International Arctic Buoy Programme"
  - label: "Talk: NeRFBerg, Ocean Sciences Meeting 2026"
    note: "Glasgow, ME43A-05"
  - label: "Talk: Disko Bay Iceberg Drift and Shape Observations from a Small Vessel"
    note: "Ocean Sciences Meeting 2026, Smedsrud et al., HE33B-03"
media:
  - label: "Exhibition: Fragmented Reconstructions, with Mallory McPherson"
    url: https://web.uri.edu/gso/uncategorized/exhibition-at-uri-illuminates-art-and-science-collaboration/
    note: "The Synergy Project, Studio Blue, URI Bay Campus, 2026"
  - label: "AI-Generated Iceberg Models Could Help Sailors Navigate Arctic Waters"
    url: https://today.umd.edu/ai-generated-iceberg-models-could-help-sailors-navigate-arctic-waters
    note: "Maryland Today, 2025"
  - label: "Faculty Spotlight: AI for Ocean Science Applications"
    url: https://web.uri.edu/iacr/faculty-spotlight-russell-shomberg-gso/
    note: "URI Institute for AI and Computational Research, 2026"
images:
  - src: /assets/2026-nerfberg/fig1-reconstructions.jpg
    caption: MVS (left), drone photograph (center), and NeRF (right) for icebergs 4450746 (top) and 4450743 (bottom).
    alt: Two icebergs shown as MVS reconstruction, drone photo, and NeRF reconstruction
  - src: /assets/2026-nerfberg/fig2-preprocessing.jpg
    caption: Preprocessing for iceberg 4450746. Raw drone frame, contrast enhancement (CLAHE), and CNN segmentation mask.
    alt: Raw drone frame, enhanced frame, and segmentation mask of an iceberg
  - src: /assets/2026-nerfberg/fig3-heatmap-4450746.jpg
    caption: Per-pixel color distance between reprojected meshes and the real photo, MVS (left) and NeRF (right).
    alt: Heatmaps comparing MVS and NeRF mesh reprojections to a reference photo
---

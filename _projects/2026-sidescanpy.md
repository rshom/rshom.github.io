---
published: true
permalink: /sidescanpy
created: 2025-07-29
date: 2026-11-11
updated: 2026-11-11
title: sidescanpy
thumbnail: /assets/2026-sidescanpy/jncc_wight_barfleur.png
abstract: >-
  Sidescan sonar data is usually processed in closed software or in lab
  scripts nobody else can run, so two groups can't tell whether their images
  differ because of the seafloor or because of the processing. sidescanpy is
  an open Python package that reads EdgeTech JSF, Klein SDF, and XTF into one
  data model and records every correction it applies, so any product can be
  rebuilt from the raw files. From there it grids to GeoTIFF and builds
  COCO/YOLO training sets whose labels point back to the original pings.
research:
  - label: "Code: sidescanpy"
    url: https://github.com/rshomberg-research/sidescanpy
    note: "GitHub, MIT"
  - label: "Package: pip install sidescanpy"
    url: https://pypi.org/project/sidescanpy/
    note: "PyPI, first release 0.10.1, 2026"
  - label: "Documentation"
    url: https://rshomberg-research.github.io/sidescanpy/
    note: "guide, worked examples on public data, API reference"
  - label: "Software DOI: 10.5281/zenodo.24121873"
    url: https://doi.org/10.5281/zenodo.24121873
    note: "Zenodo"
  - label: "Announcement post"
    url: "/blog/2026/11/11/sidescanpy.html"
images:
  - src: /assets/2026-sidescanpy/correct_a_line.png
    caption: A public EdgeTech line, raw (left) and after bottom tracking, TVG, and slant-to-ground range (right). UK JNCC data, Open Government Licence.
    alt: Raw and corrected sidescan waterfalls of the same line
  - src: /assets/2026-sidescanpy/three_formats.png
    caption: The same calls on EdgeTech JSF, Benthos XTF (UK JNCC, Open Government Licence), and Klein XTF (USGS, public domain).
    alt: Three sidescan waterfalls from three different sonars
  - src: /assets/2026-sidescanpy/swath_tile_labels.png
    caption: A dual-swath tile cut for annotation, with square 0.1 m pixels and example "reef" and "contact" boxes. Each box maps back to its file, ping, side, and position. USGS Grand Bay data, public domain.
    alt: Sidescan swath tile with two red labelled bounding boxes
  - src: /assets/2026-sidescanpy/jncc_wight_barfleur.png
    caption: Wight-Barfleur Reef as a ground-range waterfall and a 1 m UTM grid. UK JNCC data, Open Government Licence.
    alt: Sidescan waterfall beside a gridded map of the same line
---

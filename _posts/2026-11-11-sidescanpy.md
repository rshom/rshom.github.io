---
published: true
layout: post
title: "sidescanpy is on PyPI"
date: 2026-11-11
categories: blog
---

[sidescanpy](https://rshomberg-research.github.io/sidescanpy/) is now public: `pip install sidescanpy`. It reads EdgeTech JSF, Klein SDF, and XTF sidescan files into one `xarray` data model, applies the standard corrections (TVG, slant-to-ground range, georeferencing) with every step and its parameters recorded, grids to GeoTIFF, and builds COCO/YOLO training sets from target catalogs. The point is that a corrected image or a training set can always be rebuilt from the raw files. It started as my own processing scripts in mid-2025. The worked examples all run on openly licensed public surveys. It is still beta (0.x), so pin the version you use. Code on [GitHub](https://github.com/rshomberg-research/sidescanpy) (MIT), cite it with [10.5281/zenodo.24121873](https://doi.org/10.5281/zenodo.24121873), and more on the [project page]({{ '/sidescanpy' | relative_url }}).

![Raw and corrected waterfall of one EdgeTech line]({{ '/assets/2026-sidescanpy/correct_a_line.png' | relative_url }})
*Raw (left) and after bottom tracking, TVG, and slant-to-ground range (right). UK JNCC data, Open Government Licence.*

![The same code on three sonars]({{ '/assets/2026-sidescanpy/three_formats.png' | relative_url }})
*Same calls, three sonars and file writers: EdgeTech JSF, Benthos XTF (UK JNCC, Open Government Licence), and Klein XTF (USGS, public domain).*

![Test images with labelled objects and detector calls]({{ '/assets/2026-sidescanpy/two_stage_test.jpg' | relative_url }})
*The target-recognition example: a YOLO detector plus a chip classifier on held-out test images. Labels in green, calls in red and cyan by class. Images from [Santos et al. 2024](https://doi.org/10.6084/m9.figshare.24574879), CC BY 4.0.*

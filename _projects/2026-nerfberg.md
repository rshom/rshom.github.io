---
permalink: /nerfberg
created: 2026-02-01
updated: 2026-11-08
title: "NeRFBerg: Iceberg Reconstruction from Drone Imagery"
published: true
---

We reconstruct iceberg sails in 3D from commercial off-the-shelf (COTS)
drone video using neural radiance fields (NeRF). The result is an
accurate 3D model of the iceberg, from which surface area and volume
can be measured without anyone setting foot on the ice.

![Survey boat beside an iceberg and a drone view of the same iceberg]({{ '/assets/2026-nerfberg/field.jpg' | relative_url }})
*Field operations in Disko Bay, Greenland, June 2025: working from a
small boat (left) and drone imagery of an iceberg (right).*

## Problem

Icebergs are a hazard to shipping and a direct measure of ice loss, but
operational practice, including the International Ice Patrol, still
classifies each iceberg by height and width alone. Ice is a homogeneous
material, so an accurate 3D shape gives volume and mass directly.
Traditional photogrammetry struggles on icebergs: the surfaces are
reflective and translucent, have few stable features, and sit against
moving water and sky.

## Approach

1. Drone video from field campaigns in Disko Bay, Greenland is split
   into frames with OpenCV, sampled at a fixed interval, and filtered
   with Canny edge detection on the ratio of ice to water.
2. A convolutional neural network (CNN) masks the ice from the
   background. It consistently outperforms manual thresholding.
3. Structure from motion (SfM) gives the camera poses. Nerfstudio
   trains the NeRF, and multi-view stereo (MVS) runs on the same frames
   for comparison.
4. A scale factor from reference measurements and Poisson surface
   reconstruction put both models in real units, enabling a direct
   comparison of surface area, volume, Chamfer distance, and Hausdorff
   distance.

![Ground truth image, dense point cloud, Poisson mesh, and neural rendering of an iceberg]({{ '/assets/2026-nerfberg/views.jpg' | relative_url }})
*One iceberg four ways: a ground truth drone image (upper left), a
dense point cloud (upper right), a Poisson mesh (lower left), and a
neural rendering (lower right).*

## Result

The NeRF reconstruction gave a more accurate geometry of the iceberg
sail than SfM/MVS across every measured quantity. The full pipeline
from drone video to measured geometry is open source.

![Photogrammetry and NeRF point clouds of the same iceberg]({{ '/assets/2026-nerfberg/pointclouds.jpg' | relative_url }})
*Point clouds of the same iceberg from photogrammetry (left) and NeRF
(right). Photogrammetry leaves holes where the ice is bright and
featureless. The NeRF fills the surface.*

## What Follows

A small drone and an open-source pipeline put iceberg measurement within
reach of any vessel in a high-traffic region such as the North
Atlantic, including citizen science observers. Next steps are a
comparison with Gaussian splatting, iceberg-specific models, keel data
from sonar for complete above- and below-water geometry, and repeat
scans to measure change over time.

![Two researchers on a small boat collecting camera data beside Antarctic icebergs]({{ '/assets/2026-nerfberg/antarctica.jpg' | relative_url }})
*Collecting simultaneous imagery and sonar of icebergs on the Antarctic
Peninsula, January 2026.*

## Art: *Fragmented Reconstructions*

The reconstructions also became art. Through The Synergy Project, a
partnership between Art League RI and URI, I worked with visual artist
Mallory McPherson on *Fragmented Reconstructions*, a piece built from
the iceberg models. It was part of the group exhibition *Environmental
Currents: Art and Science Explore our Changing World* at Studio Blue,
URI Narragansett Bay Campus, September 10 to November 18, 2026.

## Team

This project started as a URI AI Lab student project. Liam McKenzie
(first author), Matthew Barbrack, and Julianna Della Selva are URI
undergraduates. Collaborators are Isabelle Rathbun, Cy Keener, Lars H.
Smedsrud, Christopher Metzler, Ignatius Rigor, and Indrani Mandal.

## Publications and Press

- L. McKenzie, M. Barbrack, J. Della Selva, I. A. Rathbun, C. E. Keener,
  L. H. Smedsrud, C. Metzler, I. Rigor, I. Mandal, and **R. Shomberg**,
  "Neural radiance field applications for geometric reconstruction of
  Arctic icebergs," in *OCEANS 2026, Monterey*, 2026.
- R. Shomberg et al., "NeRFBerg: Neural radiance field applications for
  rendering and reconstructions of Arctic sea ice," Ocean Sciences
  Meeting, Glasgow, 2026 (talk).
- L. H. Smedsrud, C. E. Keener, R. Shomberg, et al., "Disko Bay iceberg
  drift and shape observations from a small vessel," Ocean Sciences
  Meeting, Glasgow, 2026.
- Maryland Today, [AI-Generated Iceberg Models Could Help Sailors Navigate Arctic Waters](https://today.umd.edu/ai-generated-iceberg-models-could-help-sailors-navigate-arctic-waters), October 2025
- URI Institute for AI and Computational Research, [Faculty Spotlight: AI for Ocean Science Applications](https://web.uri.edu/iacr/faculty-spotlight-russell-shomberg-gso/), March 2026

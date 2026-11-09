---
published: true
layout: post
title: "Reproducing a ghost gear detector"
date: 2026-10-01
categories: blog
---

A reproduction of the detector training in Bodine et al. (2026), "[GhostVision: Democratizing Derelict Gear Detection Using Low-Cost Sonar and Artificial Intelligence](https://doi.org/10.3390/jmse14100951)," as a baseline for my OCE495 capstone team. The method, dataset, and settings are theirs. The [code](https://github.com/rshomberg-uri/ghostgear-detector-training) is four scripts (convert, train, evaluate, visualize), written mostly with Claude. Neither YOLO model matched the paper's test scores, and my YOLOv26s scored well above theirs (mAP@50 of 0.40 against 0.07).

![YOLOv26s detections on twelve test images]({{ '/assets/2026-ghostgear/yolo26s_examples.jpg' | relative_url }})
*YOLOv26s on the test split: clean hits (top), worst misses (middle), worst false alarms (bottom). Sonar images from the [Bodine et al. dataset](https://huggingface.co/datasets/PINGEcosystem/sss-crab-pot-detection-ds), CC BY-SA 4.0; this figure carries the same license.*

![Precision, recall, and F1 versus confidence threshold]({{ '/assets/2026-ghostgear/threshold_sweep.png' | relative_url }})
*Precision, recall, and F1 against confidence cutoff. YOLOv12s peaks at 0.04, so the 0.25 default throws away many of its hits.*

![Training and validation loss and validation mAP per epoch]({{ '/assets/2026-ghostgear/training_curves.png' | relative_url }})
*Training history. Validation loss flattens within about 10 epochs.*

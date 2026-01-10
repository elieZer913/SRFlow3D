# SRFlow3D
---

## Project Overview

SRFlow3D is a high-resolution facial motion dataset designed for facial scene flow estimation.
The dataset provides dense pixel-wise annotations of optical flow, depth, and depth change, which together form a complete parameterization for recovering 3D scene flow.

All annotations are generated from a unified dynamic face model, ensuring strict geometric and motion consistency across 2D image-space motion and 3D geometric variation.
This unified generation process avoids error accumulation and inconsistency commonly introduced by multi-stage estimation or post-processing pipelines.

SRFlow3D is constructed using a dynamic 3D Gaussian representation and differentiable Flow Rasterizer rendering, which projects 3D motion and geometry onto the image plane in a pixel-wise manner.
The resulting annotations are temporally coherent and robust under complex facial expressions, subtle motions, and self-occlusions, providing reliable supervision for learning facial motion.

---

## Visualization

The following video demonstrates RGB renderings, mask, optical flow, scene flow, and depth visualizations provided by the dataset.

<video src="assets/viz.webm" width="900" controls></video>

---

## Dataset  

The SRFlow3D dataset will be publicly released soon.  
Once available, it will be downloadable from the [project page](#) under a [CC BY-NC-SA 4.0 license](https://creativecommons.org/licenses/by-nc-sa/4.0/).

The dataset is divided into `test` and `train` sets. Each set contains multiple subjects, each with the following folder structure:

```
├── SRFlow3D/
│   ├── test/
│   │   ├── camera/
│   │   │   ├── 031/
│   │   │   │   ├── spirals.json   # Camera intrinsics and extrinsics
│   │   │   │   └── clip.json      # Clip info for evaluation
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── depth/                  # Depth maps
│   │   │   ├── 031/
│   │   │   │   ├── 0000.npy
│   │   │   │   ├── 0001.npy
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── scaled_inv_depth/       # Scaled inverse depth
│   │   │   ├── 031/
│   │   │   │   ├── 0000.npy
│   │   │   │   ├── 0001.npy
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── scaled_inv_depth_CF/    # Forward scaled inverse depth change
│   │   │   ├── 031/
│   │   │   │   ├── 0000.npy
│   │   │   │   ├── 0001.npy
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── scaled_inv_depth_CB/    # Backward scaled inverse depth change
│   │   │   ├── 031/
│   │   │   │   ├── 0000.npy
│   │   │   │   ├── 0001.npy
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── flow_F/                 # Forward optical flow
│   │   │   ├── 031/
│   │   │   │   ├── 0000.flo
│   │   │   │   ├── 0001.flo
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── flow_B/                 # Backward optical flow
│   │   │   ├── 031/
│   │   │   │   ├── 0000.flo
│   │   │   │   ├── 0001.flo
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── mask/                   # Visibility masks
│   │   │   ├── 031/
│   │   │   │   ├── 0000.jpg
│   │   │   │   ├── 0001.jpg
│   │   │   │   └── ...
│   │   │   ├── 056/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   └── render/                 # Rendered RGB images
│   │       ├── 031/
│   │       │   ├── 0000.jpg
│   │       │   ├── 0001.jpg
│   │       │   └── ...
│   │       ├── 056/
│   │       │   └── ...
│   │       └── ...
│   ├── train/
│   │   ├── camera/
│   │   │   ├── 018/
│   │   │   │   ├── spirals.json
│   │   │   ├── 030/
│   │   │   │   └── ...
│   │   │   └── ...
│   │   ├── depth/
│   │   ├── scaled_inv_depth/
│   │   ├── scaled_inv_depth_CF/
│   │   ├── scaled_inv_depth_CB/
│   │   ├── flow_F/
│   │   ├── flow_B/
│   │   ├── mask/
└── └── └── render/
```

---

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

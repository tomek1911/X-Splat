# X-Splat: Gaussian Splatting for 3D Dental Volume Generation from a Single Panoramic Radiograph
[![arXiv](https://img.shields.io/badge/arXiv-2607.02099-b31b1b.svg)](https://arxiv.org/abs/2607.02099)

> **Paper under review.** Code and pretrained checkpoints will be released upon acceptance.

---

## Overview

X-Splat is a feed-forward Gaussian Splatting framework that generates CBCT-like 3D maxillofacial volumes from a single panoramic radiograph (PXR) without requiring multiple projections, paired real scans, or additional input beyond the image itself.

Generating a 3D dental volume from a single PXR is highly underdetermined: panoramic acquisition integrates 3D attenuation along curved X-ray paths into a 2D image, leaving depth-resolved anatomy unobserved. Existing implicit and generative approaches often produce oversmoothed geometry or anatomically inconsistent hallucinations. X-Splat addresses this by anchoring learnable anisotropic Gaussian primitives to the known panoramic acquisition geometry and predicting all parameters in a single feed-forward pass, constrained by physics-consistent Beer-Lambert reprojection and multi-view radiographic training supervision.

---

## Key Features

- **Ray-anchored initialization** — Gaussian primitives are placed along the X-ray paths that formed the input image, concentrating representational capacity where the input is informative
- **Single feed-forward pass** — full 3D maxillofacial volume generated from a single PXR at inference
- **Physics-consistent supervision** — Beer-Lambert reprojection and multi-view DRR consistency losses resolve depth ambiguity
- **Lightweight residual refiner** — adds dataset-level anatomical priors without overriding the geometry resolved by the Gaussians
- **Geometry-aware evaluation** — introduces segmentation-based metrics (BA-ASD, TVR, CVR, HV) for the evaluation of PXR-based generation over the full maxillofacial tissue hierarchy

---

## Code and Checkpoints

**Coming soon.** If you want to be notified, watch this repository.

---

## Citation
[![arXiv](https://img.shields.io/badge/arXiv-2607.02099-b31b1b.svg)](https://arxiv.org/abs/2607.02099)

If you find this work useful, please cite:

```bibtex
@article{xsplat2026,
  title     = {X-Splat: Gaussian Splatting for 3D Dental Volume Generation from a Single Panoramic Radiograph},
  author    = {},
  journal   = {},
  year      = {2026}
}
```

*Citation will be updated upon publication.*

---

## Dataset

Experiments use a subset of the publicly available [ToothFairy3](https://ditto.ing.unimore.it/toothfairy3/) dataset. We select scans with full maxillofacial field of view and paired segmentation labels. Training is performed exclusively on synthetic PXR-CBCT pairs simulated via Beer-Lambert projection, requiring no paired real scans.

---

## License

To be specified upon release.

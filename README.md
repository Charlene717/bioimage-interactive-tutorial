# Bioimage Analysis Interactive Tutorial

**🌐 Live demo / 線上瀏覽**: <https://charlene717.github.io/bioimage-interactive-tutorial/>

## 中文簡介

生物影像分析互動式教學。Fiji、QuPath、CellProfiler、Cellpose 與深度學習模型，雙語並陳。

## English Description



A bilingual (Traditional Chinese 中 / English) interactive tutorial covering bioimage analysis from microscopy fundamentals through deep learning segmentation, tracking, and digital pathology — built in the same style as the sister `scRNA-seq` and `Spatial Transcriptomics` tutorials in this workspace.

## 📂 Folder structure

```
Bioimage_Analysis/
├── bioimage-interactive-tutorial-main/    ← main tutorial (you are here)
│   ├── index.html                          ← hub page
│   ├── styles.css                          ← shared stylesheet
│   ├── i18n.js                             ← language toggle
│   ├── fundamentals.html                   ← Step 1
│   ├── preprocessing.html                  ← Step 2
│   ├── deconvolution.html                  ← Step 3
│   ├── registration.html                   ← Step 4
│   ├── segmentation-classic.html           ← Step 5
│   ├── segmentation-dl.html                ← Step 6
│   ├── foundation-models.html              ← Step 7
│   ├── tracking.html                       ← Step 8
│   ├── quantification.html                 ← Step 9
│   ├── 3d-multidim.html                    ← Advanced
│   ├── high-content.html                   ← Advanced
│   ├── pathology.html                      ← Advanced
│   └── tools.html                          ← Advanced
├── references/                             ← paper / doc / DB index
│   └── index.html
└── bioimage-quiz/                          ← interactive quiz module
    ├── index.html                          ← quiz UI
    ├── data.js                             ← bilingual question bank (~130 Qs)
    └── i18n.js
```

## 🚀 Running locally

The site is fully static — no build step. Just open `index.html` in a browser, or serve the folder over HTTP for cleaner relative links:

```bash
cd Bioimage_Analysis/bioimage-interactive-tutorial-main
python -m http.server 8000
# then visit http://localhost:8000/
```

Open `index.html` from the parent (`Bioimage_Analysis/`) for the hub view.

## 📚 13 topic modules

**Core analysis pipeline (Step 1–9)**

1. **Image Fundamentals** — pixels/voxels, bit depth, channels, microscopy modalities (widefield/confocal/light-sheet/super-resolution), file formats (TIFF, OME-TIFF, CZI, LIF, ND2, OME-Zarr), Bio-Formats
2. **Preprocessing & Denoising** — Gaussian/median/NLM/BM3D, rolling-ball, BaSiC flat-field, Noise2Void, Cellpose3 one-click restoration
3. **Deconvolution** — PSF concept, Richardson-Lucy, Wiener, CARE/DeepStorm DL restoration
4. **Registration & Stitching** — rigid/affine/B-spline transforms, mutual information, BigStitcher, ANTs SyN
5. **Classical Segmentation** — Otsu/Li/Triangle thresholding, morphology, distance transform, watershed, regionprops
6. **Deep Learning Segmentation** — U-Net, Cellpose 4 (Cellpose-SAM), StarDist, nnU-Net, Mesmer, Omnipose
7. **AI Foundation Models** — SAM/SAM 2, Micro-SAM, MedSAM2, CellSAM, UNI/Virchow/CONCH pathology FMs
8. **Cell / Particle Tracking** — TrackMate 7, btrack, Trackastra (transformer), Cell Tracking Challenge metrics
9. **Quantification & Features** — intensity, morphology, colocalization (Pearson/Manders/Costes), Haralick texture, PyRadiomics

**Advanced topics**

10. **3D & Multi-Dimensional Analysis** — anisotropic voxels, Cellpose 3D / StarDist 3D / PlantSeg, napari, dask out-of-core, OME-Zarr
11. **High-Content Screening** — CellProfiler 4 / Analyst, Cell Painting, JUMP-CP, pycytominer profile normalization
12. **Digital Pathology** — QuPath, OpenSlide/TiffSlide, Macenko stain normalization, HoVer-Net, CLAM, UNI/Virchow WSI FMs
13. **Tools Comparison & Integration** — Fiji vs. napari vs. CellProfiler vs. QuPath vs. ilastik selection guide, Snakemake / Nextflow reproducibility, BioImage Model Zoo

## 📄 Page anatomy

Each topic page follows the workspace template:

- `page-hero` with step badge, bilingual H1 and subtitle
- 4–6 sections combining concept, decision-tree (`.decision-tree`), comparison tables (`.comp-table`), callouts (`.callout.tip` / `.callout.warn` / `.callout.danger`)
- Code tabs (`.code-tabs`) with **Python primary** and **Fiji/ImageJ secondary** lanes (per workspace convention)
- Where useful, interactive widgets built with Chart.js (`filterChart`, `rlChart`, `histChart`) and pure DOM sliders
- 3-question `.quiz-section` self-check at the bottom of every page, with bilingual explanations

## 🌐 Language

The bilingual toggle is implemented by `i18n.js` (storage key `bioimage_lang`). All content uses either `data-lang="zh|en"` blocks for paragraphs and `data-zh="..." data-en="..."` for spans / inline labels.

## 🔗 Companion modules

- `references/index.html` — academic citations with DOI links, indexed by step
- `bioimage-quiz/index.html` — 130+ bilingual self-test questions with explanations, wrong-answer review, and per-subject progress tracking (localStorage)

## 📝 Adding a new page

1. Copy any existing topic page (e.g. `quantification.html`) as a starting point
2. Update the top-nav `class="active"` to the new file
3. Replace the hero badge, H1, subtitle, and sections
4. Update the `page-nav` (previous / next) links
5. Add the new page to `index.html`'s hub grid and to `references/index.html`'s TOC
6. Add a corresponding subject to `bioimage-quiz/data.js`

## 📌 Conventions

- Cream / teal palette inherited from sister tutorials (`--c-bg`, `--c-accent`, `--c-highlight`)
- Display font Crimson Pro; body font DM Sans; mono font JetBrains Mono
- Python is the primary code lane; Fiji macros / Groovy / CLI are secondary tabs
- Decision trees use `.decision-tree` with 🌳 icon
- Callouts: `.callout.tip` (green), `.callout.warn` (yellow), `.callout.danger` (red)

## ✏️ License & credits

© Charlene · Bioimage Analysis Interactive Tutorial. Tool / paper references with DOIs in `references/index.html` (verified May 2026).

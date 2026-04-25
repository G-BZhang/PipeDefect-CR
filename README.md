# PipeDefect-CR Dataset

## Overview

PipeDefect-CR is a cross-regional CCTV image dataset for automated drainage pipe defect classification. It contains 1,359 annotated images collected from two distinct sources: municipal inspection imagery from the Greater Bay Area (GBA) in China and a curated subset of the publicly available Sewer-ML dataset. The dataset covers four high-frequency defect categories:

- CJ-Deposition
- ZW-Obstacle
- PL-Fracture
- CK-Disconnection

The GBA subset consists of 981 images, while the Sewer-ML subset contains 378 images. All images were organized and labeled under a unified defect taxonomy.

## Data Access

The complete dataset can be downloaded from:

https://drive.google.com/file/d/1cZMSXWZRWDt8ReanSlWSHxKAopywL2ya/view?usp=drive_link

## Directory Structure

The `PipeDefect-CR dataset` directory is organized in a hierarchical manner. The dataset root contains three top-level folders corresponding to:

1. `PipeDefect-CR/` – Contains the primary collection of pipeline defect images and corresponding annotations. The numerical prefix (0–3) in filenames denotes the defect category, while the suffix indicates the number of samples contained within each compressed archive.
2. `fGBA/` – A supplementary dataset derived from or associated with the fGBA acquisition protocol, adhering to the same categorical taxonomy.
3. `fSewer-ML/` – An additional dataset pertaining to sewer inspection scenarios, structured analogously to the preceding directories.

Within each data source directory, samples are further organized according to four defect categories and stored in compressed archive format `.zip` to facilitate research tasks such as classification, cross-domain generalization, and transfer learning. Images originating from the fGBA source are encoded in the `.jpeg` format, whereas those from the fSewer-ML source are encoded in the `.jpg` format.

```text
PipeDefect-CR dataset/
├── PipeDefect-CR/
│   ├── 0 CJ-Deposition 362.zip
│   ├── 1 CK-Disconnection 464/
│   │   ├── 1.zip
│   │   └── 2.zip
│   ├── 2 PL-Fracture 219.zip
│   └── 3 ZW-Obstacle 314.zip
├── fGBA/
│   ├── 0 CJ-Deposition 274.zip
│   ├── 1 CK-Disconnection 319.zip
│   ├── 2 PL-Fracture 189.zip
│   └── 3 ZW-Obstacle 199.zip
└── fSewer-ML/
    ├── 0 CJ-Deposition 88.zip
    ├── 1 CK-Disconnection 145.zip
    ├── 2 PL-Fracture 30.zip
    └── 3 ZW-Obstacle 115.zip
```

## **Remarks on Data Packaging and Storage Constraints**

### **1.Compressed Archive Format**

All data within each subdirectory are distributed as `.zip` archives. Each archive corresponds to a specific defect class, as indicated by its filename . Users must extract these archives prior to data utilization.

### **2.**Split Archive for High-Volume Category****

Owing to file size restrictions imposed by the hosting platform, the category **`1 CK-Disconnection 464`** within the `PipeDefect-CR/` directory has been partitioned into two separate compressed files: `1.zip` and `2.zip`, both located inside the subfolder `1 CK-Disconnection 464/`. To reconstruct the complete dataset for this category, users must extract the contents of both split archives into a common destination directory.
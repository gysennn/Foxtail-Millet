# Foxtail Millet Pest–Disease Detection Dataset

This repository provides the public metadata, category definitions, YOLO configuration, example images, and access information for the datasets used in:

> **KGMA-Det: Structured Biological Knowledge-Guided Learning for Data-Scarce Foxtail Millet Pest-Disease Detection**

The study organizes pest individuals, disease manifestations, and pest-induced host damage within a fixed 10-category identity–state vocabulary.

> **Availability note:** the complete image and annotation archives are not hosted in this repository. They are available for academic research upon reasonable request; see [Dataset Access](#dataset-access).

## Dataset Overview

The study uses two field RGB datasets:

- **2025 development dataset:** covers all 10 identity–state categories and contains **8,409 annotated object instances**. It was divided into training, validation, and internal-test subsets using source-grouped partitioning.
- **Independent 2026 evaluation dataset:** covers five predefined categories and contains **446 annotated object instances**. It was reserved exclusively for cross-year external evaluation and was not used for training, augmentation, validation, hyperparameter selection, or reference sampling.

The image counts in the tables below are **class-associated image occurrences**, not counts of unique images. One image may contain more than one category, so the column sums must not be interpreted as the number of unique source images.

## Data Collection and Annotation

The 2025 field images were collected from June to August 2025 in Mizhi County, Yulin, Shaanxi Province, China. Images were acquired with an iPhone 15, Huawei nova 7 SE, and Redmi Note 14 at resolutions from 1600 × 2133 to approximately 3000 × 4000 pixels. The collection includes natural variation in illumination, viewpoint, viewing distance, occlusion, and plant growth stage.

Images with severe blur, exposure errors, irrelevant content, unlocalizable targets, or ambiguous phenotypes were excluded. Duplicate and near-duplicate images were screened through manual inspection and image-similarity analysis. Two annotators labeled the retained images under the supervision of plant-protection specialists from the Mizhi Agricultural Experimental Station. Each object was assigned a bounding box and an identity–state label; biological descriptors used by the associated study additionally cover symptom attributes, affected organ, morphology, and relative scale.

## 2025 Development Dataset Statistics

| Biological target | Annotation dimension | Identity–state label | Image occurrences | Instances |
|---|---|---|---:|---:|
| Foxtail millet leaf spot | Lesion type | Foxtail millet leaf spot | 869 | 2,038 |
| Leaf beetle | Developmental stage | Larva | 468 | 751 |
| Leaf beetle | Damage symptom | Leaf beetle damage symptom | 492 | 871 |
| Foxtail millet downy mildew | Vegetative-stage symptom | Water-soaked lesion | 983 | 1,813 |
| Foxtail millet downy mildew | Vegetative-stage symptom | Gray-back symptom | 189 | 236 |
| Foxtail millet downy mildew | Reproductive-stage symptom | Spear-like stalk symptom | 705 | 780 |
| Foxtail millet downy mildew | Reproductive-stage symptom | Hedgehog-like panicle | 693 | 775 |
| Millet stem borer | Developmental stage | Larva | 671 | 813 |
| Millet stem borer | Developmental stage | Adult | 66 | 71 |
| Millet stem borer | Damage symptom | Dead-heart symptom | 167 | 261 |
| **Column sum** |  |  | **5,303** | **8,409** |

## Independent 2026 Evaluation Dataset Statistics

| Biological target | Annotation dimension | Identity–state label | Image occurrences | Instances |
|---|---|---|---:|---:|
| Leaf beetle | Pest developmental stage | Larva | 71 | 201 |
| Foxtail millet downy mildew | Vegetative stage | Water-soaked lesion | 56 | 89 |
| Foxtail millet downy mildew | Vegetative stage | Gray-back symptom | 39 | 47 |
| Millet stem borer | Pest developmental stage | Larva | 40 | 80 |
| Millet stem borer | Damage symptom | Dead-heart symptom | 29 | 29 |
| **Column sum** |  |  | **235** | **446** |

## Detection Categories

The model uses the following 10 class IDs:

| ID | Class |
|---:|---|
| 0 | Foxtail millet leaf spot |
| 1 | Leaf beetle larva |
| 2 | Leaf beetle damage symptom |
| 3 | Water-soaked lesion |
| 4 | Gray-back symptom |
| 5 | Spear-like stalk symptom |
| 6 | Hedgehog-like panicle |
| 7 | Millet stem borer larva |
| 8 | Millet stem borer adult |
| 9 | Dead-heart symptom |

These class IDs are consistent with `data.yaml`.

## Dataset Partitioning

The 2025 data were divided into training, validation, and internal-test subsets using source-grouped partitioning. Images from the same plant, acquisition burst, or near-duplicate source were assigned to the same subset to reduce information leakage. Training-dependent procedures were restricted to the training subset, the validation subset was used for model selection, and the internal-test subset was reserved for final evaluation.

## Annotation Format

Annotations follow the standard YOLO object-detection format:

```text
class_id x_center y_center width height
```

All bounding-box coordinates are normalized to `[0, 1]`.

## Repository Contents

```text
Foxtail-Millet/
├── example/       # Representative field images
├── data.yaml     # YOLO dataset configuration and class mapping
├── LICENSE
└── README.md
```

The repository contains representative examples only; it does not contain the complete dataset archive.

## Dataset Access

The complete datasets are available for academic research upon reasonable request. To request access, contact:

**Yusen Guo**<br>
Northwest A&F University<br>
Email: **guoys@nwafu.edu.cn**

Please include your name, affiliation, research purpose, and intended use. Access to the complete dataset does not grant permission to redistribute it to third parties.

## Intended Use

The datasets are intended for research on:

- foxtail millet pest–disease detection;
- data-scarce and class-imbalanced agricultural vision;
- object detection under natural field conditions;
- lightweight crop-monitoring models;
- cross-year evaluation of agricultural detectors.

## License and Data Use

Repository materials are provided under the terms in [LICENSE](LICENSE). Access and redistribution conditions for the complete image and annotation archives are provided separately when dataset access is granted.

If you use these datasets or repository materials in a publication, please cite the associated manuscript.


## Contact

For dataset access or repository questions, contact **Yusen Guo** at **guoys@nwafu.edu.cn**.

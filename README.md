# Foxtail-Millet Pest and Disease Detection Dataset

This repository provides the dataset configuration, example images, and class definitions used for foxtail millet pest and disease detection.

The dataset contains field RGB images collected under natural agricultural conditions and includes pest bodies, disease symptoms, and pest-induced host-damage symptoms. Annotations are provided in YOLO object-detection format.

## Dataset Access

The complete dataset is available for academic research upon request.

To request access, please contact:

**Yusen Guo**  
Northwest A&F University  
Email: **guoys@nwafu.edu.cn**

When requesting the dataset, please briefly state your name, affiliation, research purpose, and intended use of the data.

## Dataset Categories

The dataset contains 11 fine-grained detection categories:

| ID | Class |
|---:|---|
| 0 | Stem borer larva |
| 1 | Stem borer adult |
| 2 | Stem borer damage |
| 3 | Water-soaked lesion |
| 4 | Hedgehog-like panicle |
| 5 | Spear-like stalk |
| 6 | Gray-back symptom |
| 7 | Leaf spot |
| 8 | Leaf beetle |
| 9 | Leaf beetle damage |
| 10 | Dead-heart symptom |

The class IDs above are consistent with the labels defined in `data.yaml`.

## Annotation Format

Annotations follow the standard YOLO object-detection format:

```text
class_id x_center y_center width height
```

All bounding-box coordinates are normalized to the range `[0, 1]`.

## Repository Structure

```text
Foxtail-Millet/
├── example/
│   └── ...
├── data.yaml
└── README.md
```

- `example/`: example images for visual inspection.
- `data.yaml`: dataset configuration and class-name mapping.
- `README.md`: dataset description and access information.

## Example `data.yaml`

```yaml
path: .

train: images/train
val: images/val
test: images/test

nc: 11

names:
  0: Stem borer larva
  1: Stem borer adult
  2: Stem borer damage
  3: Water-soaked lesion
  4: Hedgehog-like panicle
  5: Spear-like stalk
  6: Gray-back symptom
  7: Leaf spot
  8: Leaf beetle
  9: Leaf beetle damage
  10: Dead-heart symptom
```

## Intended Use

This dataset is intended for research on:

- foxtail millet pest and disease detection;
- few-shot object detection;
- class-imbalanced agricultural vision;
- lightweight object detection;
- intelligent crop monitoring.

## Data Use

The complete dataset is not directly hosted in this repository. Access is provided upon reasonable academic request.

Users should not redistribute the dataset to third parties without permission from the dataset authors. If the dataset is used in a publication, please acknowledge the dataset source and cite the associated paper once the citation information becomes available.

## Citation

Citation information will be updated after publication of the associated work.

```bibtex
@article{KGMA-Det,
  title   = {KGMA-Det: A Knowledge-Guided Modulation and Augmentation Detector with Multi-Scale Dilated Attention for Few-Shot Foxtail Millet Pest and Disease Detection},
  author  = {To be updated},
  journal = {To be updated},
  year    = {2026}
}
```

## Contact

For dataset access or other questions, please contact:

**Yusen Guo**  
Email: **guoys@nwafu.edu.cn**

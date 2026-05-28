[Picture.pdf](https://github.com/user-attachments/files/28344747/Picture.pdf)
[Picture.pdf](https://github.com/user-attachments/files/28344728/Picture.pdf)

# SIGHT: A Structured Image-Grounded Hierarchical Taxonomy for Evaluating Multimodal Cultural Alignment


SIGHT is a large-scale, Human-annotated multimodal benchmark for culturally grounded and hierarchical visual understanding. It is designed to evaluate multimodal models across diverse global, regional, and culturally significant visual domains.It comprises over 5M image-caption pairs drawn from 450+ authoritative sources, spanning 13 culturally grounded semantic categories.

<div align="center">
<img alt="License" src="https://img.shields.io/badge/License-CC BY 4.0-blue"></a> </p> </div>
</div>



## 📝 Dataset Summary

- **Modality:** Image–Text
- **Task Type:** `Image Classification`
- **Scale:** 5M+ image–caption pairs curated from 450+ global sources out of which 5,086 Instances annotated by three annotators.
- **Inter-annotator agreement** validated at Krippendorff's α = 0.680
- **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

---

##  Benchmark Task

### Image Classification


>  The primary task in SiGHT is hierarchical semantic classification of multimodal visual content. Given an image along with its associated metadata or caption, annotators assign:
*  One primary category representing the dominant semantic theme of the image.
*  Optional secondary categories when additional semantic concepts occupy a substantial portion of the visual scene or are necessary for contextual understanding.
   -  Each selected category must be paired with at least one corresponding subcategory, enabling fine-grained and semantically precise annotations within the hierarchical taxonomy.
   - Annotations are grounded primarily in the visual semantics of the image. Captions and metadata are used only as auxiliary contextual signals for source verification or ambiguity resolution.

---

## 📂 Taxonomy Overview

- **SiGHT organizes visual content into a hierarchical taxonomy consisting of top-level semantic categories and fine-grained subcategories.**

| Top-level Category                 | Associated Subcategories                                                                                                            |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Cultural & Societal**            | Festivals & Rituals; Traditional Attire & Jewelry; Food & Cuisine; Occupations & Professions; Arts, Music & Dance; Cultural Symbols |
| **Religion & Tradition**           | Temples & Places of Worship; Religious Ceremonies; Sacred Texts & Symbols; Pilgrimage Sites; Devotional Objects                     |
| **Geographic & Environmental**     | Landscapes & Terrain; River Systems & Water Bodies; Weather Patterns; Flora & Fauna; Ecological Zones                               |
| **Infrastructure & Public Spaces** | Transport Systems; Public Utility Visuals; Smart City Assets; Government Institutions; Private Institutions                         |
| **Education & Literacy**           | Textbooks; Classroom Photographs; Exam Papers; Educational Institutions; Learning Materials; Literacy Campaigns                     |
| **Commerce & Economy**             | Street Vendors; Agricultural Practices; Banking & Finance; Markets & Trade; Industrial Activity                                     |
| **Digital & Print Media**          | News Clippings; Posters & Banners; Social Media Posts; Advertisements; Digital Screens; Archival Print                              |
| **Scripts & Multilingual Text**    | OCR-ready Images; Handwritten Text; Multilingual Captions; Script Identification; Code-switched Text; Printed Text                  |
| **Historical & Archival Data**     | Archival Documents; Historical Photographs; Museum Artifacts; Heritage Collections; Historical Maps; Vintage Media                  |
| **Science & Engineering**          | Scientific Equipment; Research Labs; Engineering Projects; Technology & Innovation; Space & Defense                                 |
| **Sports & Competition**           | Professional Sport Events; Motor Racing; Traditional Sports; Athletic Competitions; Sports Infrastructure                           |
| **Community & Social Life**        | Villages & Rural Life; Community Gatherings; Public Events; Street Life; Family & Household; Daily Routines                         |
| **Urban Development & Buildings**  | Residential Buildings; Commercial Complexes; Heritage Architecture; Construction Sites; City Planning                               |



## Dataset at a Glance

| Metric | Value |
|---|---|
| Total images | 5,086 |
| Modalities | Image + Caption |
| Annotation style | Multi-label hierarchical taxonomy |
| Annotation levels | Category + Subcategory |
| Human annotators | 3 |
| Languages | English |
| Metadata format | JSONL |

---

> SIGHT taxonomy: 13 top-level categories and representative subcategories, illustrated with example images from the benchmark.
<img width="1575" height="1265" alt="Picture_page-0001" src="https://github.com/user-attachments/assets/5a511a0f-0dda-4fec-8e11-caa1c96739f6" />


## Repository Structure

```
SIGHT_benchmark_data/
│
├── images/
│   ├── toi_000000016.jpg
│   ├── ancient_0001401.jpg
│   └── ...
│
├── metadata.jsonl
├── README.md
└── .gitignore
```

---

## Metadata Format

Each line in `metadata.jsonl` is a valid JSON object with the following fields:

| Field | Description |
|---|---|
| `image_id` | Unique image identifier |
| `image` | Relative path to the image file |
| `caption` | Associated caption text |
| `annotator_1/2/3` | Independent label sets from each annotator |
| `ground_truth_combined` | Consensus ground truth for evaluation |
| `predicted_categories` | VLM model predictions |

### Example Entry

```json
{
  "image_id": "toi_000000016",
  "image": "images/toi_000000016.jpg",
  "caption": "IPL schedule 2026: Full list of fixtures for all 10 teams",

  "annotator_1": {
    "categories": ["Sports & Competition", "Community & Social Life"],
    "subcategories": ["Professional Sport Events", "Public Events"]
  },

  "annotator_2": {
    "categories": ["Digital & Print Media", "Sports & Competition", "Community & Social Life"],
    "subcategories": ["News Clippings", "Social Media Posts", "Professional Sport Events"]
  },

  "annotator_3": {
    "categories": ["Community And Social Life", "Digital And Print Media", "Sports And Competition"],
    "subcategories": ["Public Events", "News Clippings", "Professional Sport Events"]
  },

  "ground_truth_combined": {
    "categories": ["Community And Social Life", "Digital And Print Media", "Sports And Competition"],
    "subcategories": ["Public Events", "News Clippings", "Professional Sport Events"]
  },

  "predicted_categories": {
    "categories": ["Sports & Competition", "Community & Social Life"],
    "subcategories": ["Professional Sport Events", "Cricket", "Public Events"]
  }
}
```

---

## Annotation Methodology

Each image was independently annotated by three annotators using a hierarchical semantic taxonomy. Annotations include:

- **Primary semantic categories** — top-level domain classification
- **Fine-grained subcategories** — specific sub-domain labels
- **Multi-label assignments** — multiple categories permitted per image

A consensus-based ground truth was constructed from the three annotations for use in benchmark evaluation.

---

## Data Sources

| Source | Type |
|---|---|
| Wikimedia Commons | Open media repository |
| Press Information Bureau | Government releases |
| The Hindu, Times of India | News media |
| Public Archival Collections | Historical records |

> Original licenses and attributions belong to their respective owners.

---

## Intended Use Cases

- Vision-Language Model evaluation
- Multimodal semantic understanding
- Hierarchical image classification
- Multilingual multimodal retrieval
- Taxonomy-aware reasoning
- Cross-cultural semantic analysis

---

## License

Released under the **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

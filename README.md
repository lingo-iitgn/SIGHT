<<<<<<< HEAD
# SIGHT: A Structured Image-Grounded Hierarchical Taxonomy for Evaluating Multimodal Cultural Alignment


SIGHT is a large-scale, Human-annotated multimodal benchmark for culturally grounded and hierarchical visual understanding. It is designed to evaluate multimodal models across diverse global, regional, and culturally significant visual domains.

<div align="center">
<img alt="License" src="https://img.shields.io/badge/License-CC BY 4.0-blue"></a> </p> </div>
</div>



## 📝 Dataset Summary

- **Modality:** Image–Text
- **Task Type:** `Hierarchical Multi-label Classification`
- **Scale:** 5M+ image–caption pairs curated from 450+ global sources out of which 5,086 Instances annotated by three annotators.
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

## 📄 License

This dataset is distributed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.
=======
# SIGHT — Structured Image-Grounded Hierarchical Taxonomy

**Indic Multimodal Benchmark for Semantic Understanding in Vision-Language Models**
Developed by LINGO Lab, IIT Gandhinagar

---

## What is SIGHT?

SIGHT is a large-scale, hierarchically annotated benchmark corpus for evaluating multimodal cultural alignment in Vision-Language Models (VLMs). It comprises over 5M image-caption pairs drawn from 450+ authoritative sources, spanning 13 culturally grounded semantic categories.

The benchmark includes:
- A high-quality manually annotated subset of 5,000+ instances
- A structured human-in-the-loop annotation protocol
- Inter-annotator agreement validated at Krippendorff's α = 0.680

**Key finding:** Even advanced VLMs such as Llama-Vision achieve only **46.8% category-level accuracy** against expert human ground truth, exposing substantial limitations in hierarchical cultural and semantic reasoning.

---

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

## Taxonomy

The dataset spans 13 culturally rich, semantically diverse domains:

| # | Category |
|---|---|
| 1 | Cultural & Societal |
| 2 | Religion & Tradition |
| 3 | Geographic & Environment |
| 4 | Infrastructure & Public Spaces |
| 5 | Education & Literacy |
| 6 | Commerce & Economy |
| 7 | Digital & Print Media |
| 8 | Scripts & Multilingual Text |
| 9 | Historical & Archival Data |
| 10 | Science & Engineering |
| 11 | Sports & Competition |
| 12 | Community & Social Life |
| 13 | Urban Development & Buildings |

---

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
- Indic AI research

---

## License

Released under the **Apache-2.0 License**.

Individual images may retain their original source licenses. Users are responsible for complying with source-specific licensing requirements.

---

## Citation

```bibtex
@misc{chitrabhasha2026,
  title={Chitrabhasha: Indic Multimodal Benchmark for Semantic Understanding},
  author={LINGO Lab, IIT Gandhinagar},
  year={2026}
}
```

---

## Team

Developed at [LINGO Lab, IIT Gandhinagar](https://lingo.iitgn.ac.in/)

- Naren Kumar
- Rajvee Sheth
- Khushi Shukla
- Indrayudh Mandal

---

## Contact

For issues, collaborations, or benchmark usage inquiries:

- Open a [GitHub issue](../../issues)
- Email: [khushi.clgwork2226@gmail.com](mailto:khushi.clgwork2226@gmail.com)
>>>>>>> de2dd6f (Initial commit: SIGHT benchmark dataset)

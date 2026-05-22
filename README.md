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

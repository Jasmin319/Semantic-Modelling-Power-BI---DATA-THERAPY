![Banner](https://github.com/Jasmin319/Semantic-Modelling-Power-BI---DATA-THERAPY/blob/main/Brand%20Assets/Banner.png)

![Microsoft MVP](https://img.shields.io/badge/Microsoft-MVP-5E5E5E)

# Metadata Description Guide

**Write clear, concise descriptions for Power BI semantic model objects.**

This resource makes **Section 15.4, “Description text for model objects,”** actionable, together with guideline rules **DOC-003** (short descriptions versus detailed documentation), **DOC-004** (maintaining metadata on model objects), and **DOC-010** (maintaining validated synonyms).

> **Describe what is known. Do not manufacture business meaning.**

## Guides

- [Deutsch | Leitfaden für Description-Texte](METADATA_DESCRIPTION_GUIDE_DE.md)
- [English | Metadata Description Guide](METADATA_DESCRIPTION_GUIDE_EN.md)

Both guides contain compact sentence structures, clearly **illustrative examples**, synonym-maintenance guidance, anti-patterns, a review checklist, and safe Copilot prompts.

## Where a description belongs

| Location | Purpose | Level of detail |
| --- | --- | --- |
| **Table / measure Description property** | Explain the meaning of an object quickly while exploring the model | Short, neutral and factual |
| [**Table Documentation**](../table_documentation/README.md) | Trace grain, source, keys, relationships, history and limitations | Detailed, as needed |
| [**Measure Documentation**](../measure_documentation/README.md) | Trace calculation, DAX, dependencies, filter logic, approved synonyms and tests | Detailed, as needed |
| [**KPI Definition Sheet**](../kpi_definition/README.md) | Record agreed business definition and accountability | Business-approved definition |

## Key writing principles

1. Describe **business meaning**, not merely repeat the name or DAX syntax.
2. For **tables**, mention content, row grain and analytical role when known and relevant.
3. For **measures**, describe the calculated quantity and essential reference basis; specify denominator, comparison base or relevant filters where they affect interpretation.
4. Keep sentences complete, **neutral and concise**; avoid unsupported value judgments such as “higher is better.”
5. Leave unconfirmed facts open and request business clarification before publishing them as facts.

## Suggested workflow

1. Retrieve the confirmed definition and implementation context from the appropriate documentation.
2. Draft a short Description using the examples in the selected language guide.
3. Check the wording with the business owner when semantic meaning is involved.
4. Store the agreed Description directly in the appropriate model object's Description property where feasible.
5. Review it when definitions or model behavior change.

## GitHub Copilot

You can ask Copilot to **draft** descriptions using only verified facts supplied to it. Copilot output is not evidence that a business rule is true. Both language guides include suggested prompts and review guardrails.

## Guideline alignment

**Primary source:** Sections **15.3/15.4** and **DOC-003/004/010**. Example scenarios and Copilot prompts in these guides are **supplementary illustrations**, not verbatim material from the guideline.

The current published guideline is **Semantic Modeling in Power BI, v0.1 (Draft), November 16, 2026**. Its rule classifications are proposed; these resources do not turn them into approved organizational requirements.

## Changelog

- **2026-11-16:** Added linguistic metadata and synonym maintenance guidance, including product-specific validation for Copilot and Fabric data agents.

## 📄 License & Usage

Unless otherwise noted, the original documentation and other original content in this repository are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](../../../../LICENSE). Third-party material is excluded unless explicitly stated otherwise.

---

## 🔗 Related content

🎥 YouTube: [Power BI with AI Vibes](https://www.youtube.com/@BIVibes-JasminSimader)  
🏠 Website: [Jasmin Simader](https://www.jasminsimader.com/)  
👩🏻‍💻 LinkedIn: [Jasmin Simader](https://www.linkedin.com/in/jasmin-simader)  
📝 Blog / Substack: [Substack](https://substack.com/@datatherapywithjasmin)

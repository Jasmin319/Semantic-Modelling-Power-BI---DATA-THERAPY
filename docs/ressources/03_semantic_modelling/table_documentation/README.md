![Banner](https://github.com/Jasmin319/Semantic-Modelling-Power-BI---DATA-THERAPY/blob/main/Brand%20Assets/Banner.png)

![Microsoft MVP](https://img.shields.io/badge/Microsoft-MVP-5E5E5E)

# Table Documentation Template

**Document a table's business role, grain, keys and limits.**

This resource turns **Section 15.2, “Short description of a table”**, into a reusable, structured worksheet for a Power BI semantic model. It supports the *Semantic Model Specification* and is distinct from the short **Description** property stored on a model object.

> **A table name does not explain what a row represents.**

## Templates

- [Deutsch | Tabellendokumentation](TABLE_DOCUMENTATION_DE.md)
- [English | Table Documentation](TABLE_DOCUMENTATION_EN.md)

Create one copy per table or maintain the information in an equivalent, centrally controlled catalog. Only document relevant details; mark unknowns as **Open** rather than guessing.

## What it covers

| Area | Clarification |
| --- | --- |
| Role | Fact, dimension, bridge or another explicit function |
| Purpose and source | Business content, intended use and lineage |
| Grain | Exactly what one row represents |
| Keys | Unique/primary key and relevant foreign keys |
| Relationships | Cardinality, filter direction and special behavior |
| History and unknowns | Historical handling and missing/unmatched members |
| Attributes and limits | Key analytical attributes, assumptions and exclusions |
| Ownership and refresh | Accountable roles, update schedule and known lag |

The worksheet also offers **optional technical and review fields** to connect the table to an implementation and its validation. Those additions are supporting material, not additional rules from Section 15.2.

## Recommended workflow

1. Identify the table's **business purpose and grain** before defining relationships.
2. Confirm **key behavior**, including uniqueness and missing or unmatched values.
3. Document **relationships**, historical rules, important attributes and limitations.
4. Link to the implemented model and validate representative data and relationship behavior.
5. Use the [Metadata Description Guide](../metadata_description_guide/README.md) to derive a concise, factual model-object Description from confirmed information.

## Connections to other resources

- [Semantic Model Specification](../semantic_model_specification/README.md): model-wide overview; link to the relevant table record instead of duplicating details.
- [KPI Definition Sheet](../kpi_definition/README.md): definitions for business-critical measures that may depend on this table.
- [Measure Documentation Template](../measure_documentation/README.md): references the tables and columns a measure uses.
- [Semantic Model Review Checklist](../../04_validation/semantic_model_review_checklist/README.md): validates grain, keys, relationships and documentation.

## Guideline alignment

**Primary source:** Section **15.2**. Related topics: **MOD-002–MOD-005**, **DOC-001**, **DOC-003/004**, and Chapter **12**.

The current published guideline is **Semantic Modeling in Power BI, v0.1 (Draft), November 11, 2026**. Its rule classifications are proposed; these resources do not turn them into approved organizational requirements.

## Changelog

- **2026-11-16:** Corrected the published guideline date in this README.

## 📄 License & Usage

Unless otherwise noted, the original documentation and other original content in this repository are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](../../../../LICENSE). Third-party material is excluded unless explicitly stated otherwise.

---

## 🔗 Related content

🎥 YouTube: [Power BI with AI Vibes](https://www.youtube.com/@BIVibes-JasminSimader)  
🏠 Website: [Jasmin Simader](https://www.jasminsimader.com/)  
👩🏻‍💻 LinkedIn: [Jasmin Simader](https://www.linkedin.com/in/jasmin-simader)  
📝 Blog / Substack: [Substack](https://substack.com/@datatherapywithjasmin)

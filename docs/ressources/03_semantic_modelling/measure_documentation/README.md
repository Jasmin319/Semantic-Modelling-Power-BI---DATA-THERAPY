![Banner](https://github.com/Jasmin319/Semantic-Modelling-Power-BI---DATA-THERAPY/blob/main/Brand%20Assets/Banner.png)

![Microsoft MVP](https://img.shields.io/badge/Microsoft-MVP-5E5E5E)

# Measure Documentation Template

**Describe a measure's DAX implementation without losing its business meaning.**

This resource operationalizes **Section 15.3, “Short description of a measure,”** of the Power BI Semantic Modeling Guideline. Use it for measures whose calculation, filter behavior or limitations require explicit technical documentation.

> **A valid DAX expression is not a confirmed business definition.**

## Templates

- [Deutsch | Measure-Dokumentation](MEASURE_DOCUMENTATION_DE.md)
- [English | Measure Documentation](MEASURE_DOCUMENTATION_EN.md)

## What it covers

| Area | Question |
| --- | --- |
| Business meaning and decision | What is calculated, and what business purpose does it support? |
| DAX and brief technical explanation | How is the implemented calculation expressed? |
| Dependencies | Which measures, tables and columns are used? |
| Filtering | What is the ordinary filter behavior, and what context is overridden? |
| Unit and aggregation | Which unit, display format and aggregation logic are valid? |
| Exceptions and pitfalls | Which edge cases or known limitations affect use? |
| Ownership and validation | Who confirms meaning and which references/tests support correctness? |
| Synonym governance | Which confirmed alternative terms apply by language/culture, and when were they last reviewed? |

Optional implementation links, review evidence and revision fields have been added as practical aids; they are **not new guideline requirements**.

## How this differs from the KPI Definition Sheet

- [KPI Definition Sheet](../kpi_definition/README.md): the **agreed business meaning** and ownership of a KPI.
- **Measure Documentation**: the **specific technical implementation** of a measure, including DAX, dependencies, filter behavior and tests.
- [Metadata Description Guide](../metadata_description_guide/README.md): a **short, user-facing description** on the model object.

One KPI may be implemented through multiple supporting measures; not every technical measure requires a separate KPI sheet. Reference existing business definitions instead of copying them.

## Suggested use

1. Link the measure to a confirmed KPI definition or document the relevant business meaning and its owner.
2. Record the DAX and explain the calculation in plain language.
3. Identify dependencies, context transitions, fixed filters and aggregation assumptions.
4. Test totals, segments, edge cases and trusted source/reference values.
5. Write a short Description from confirmed facts only; do not copy the full DAX into the Description property.

## Related resources

- [Table Documentation Template](../table_documentation/README.md)
- [Semantic Model Specification](../semantic_model_specification/README.md)
- [Semantic Model Review Checklist](../../04_validation/semantic_model_review_checklist/README.md)

## Guideline alignment

**Primary source:** Section **15.3**. Related: **DOC-002/003/004/010**, DAX and measures chapter, and Chapter **12**.

The current published guideline is **Semantic Modeling in Power BI, v0.1 (Draft), November 16, 2026**. Its rule classifications are proposed; these resources do not turn them into approved organizational requirements.

## Changelog

- **2026-11-16:** Added business-approved synonyms, language/culture, ambiguity, and review date to the measure template; updated alignment to DOC-010.

## 📄 License & Usage

Unless otherwise noted, the original documentation and other original content in this repository are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](../../../../LICENSE). Third-party material is excluded unless explicitly stated otherwise.

---

## 🔗 Related content

🎥 YouTube: [Power BI with AI Vibes](https://www.youtube.com/@BIVibes-JasminSimader)  
🏠 Website: [Jasmin Simader](https://www.jasminsimader.com/)  
👩🏻‍💻 LinkedIn: [Jasmin Simader](https://www.linkedin.com/in/jasmin-simader)  
📝 Blog / Substack: [Substack](https://substack.com/@datatherapywithjasmin)

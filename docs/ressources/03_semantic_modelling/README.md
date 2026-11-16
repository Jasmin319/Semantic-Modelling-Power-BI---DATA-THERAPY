![Banner](https://github.com/Jasmin319/Semantic-Modelling-Power-BI---DATA-THERAPY/blob/main/Brand%20Assets/Banner.png)

![Microsoft MVP](https://img.shields.io/badge/Microsoft-MVP-5E5E5E)

# Semantic Modelling Resources

**Connect agreed business definitions to a documented semantic model design.**

The resources in this folder help teams define KPIs, specify model designs, document tables and measures, and write concise metadata descriptions. They complement the [Power BI Semantic Modeling Guideline](../../guidelines/Guideline_Semantic_Modelling_Power_BI.pdf).

Their guiding principle is:

> **Agree on meaning before calculation. Specify the model before implementation.**

## Purpose

A KPI definition, a model design, detailed object documentation, and short model descriptions answer different questions. Together, they connect business meaning to model design and implementation without replacing one another.

These are practical supporting resources, not additional mandatory standards. The current published guideline is **Version 0.1 (Draft), November 16, 2026**.

## Resources

| Resource | What it helps clarify |
| --- | --- |
| [**KPI Definition Sheet**](kpi_definition/README.md) | What does a specific KPI mean, where does it apply, how is it calculated, and how will it be validated? |
| [**Semantic Model Specification**](semantic_model_specification/README.md) | How should the semantic model meet its business and technical requirements, and how will its design be validated? |
| [**Table Documentation**](table_documentation/README.md) | What does a table contain, what does one row represent, and how is it related to other tables? |
| [**Measure Documentation**](measure_documentation/README.md) | How is a measure implemented, filtered, and validated? |
| [**Metadata Description Guide**](metadata_description_guide/README.md) | How can confirmed object meaning be summarized in a concise model description? |

## When to use them

- Use the **KPI Definition Sheet** when a measure's business meaning, scope, calculation, owner, or validation needs agreement.
- Use the **Semantic Model Specification** to record or review the design of a semantic model, including its context, sources, structure, security, operations, and risks.
- Use **Table Documentation** and **Measure Documentation** when detailed information about a table or measure needs to be recorded and reviewed.
- Use the **Metadata Description Guide** to write concise model-object descriptions based on confirmed information.
- Use both when a model implements agreed KPIs and the relationship between business definitions and model design needs to remain traceable.

## Suggested workflow

1. Clarify the decision or business question the information should support, using the [Decision Mapping Canvas](../01_decision_design/decision_mapping_canvas/README.md) when helpful.
2. Agree on the meaning and validation of each relevant KPI with its business owner.
3. Record the model-wide design and reference the agreed KPI definitions rather than duplicating them.
4. Implement and review the model using the [Semantic Modeling Guideline](../../guidelines/Guideline_Semantic_Modelling_Power_BI.pdf).
5. Document relevant tables and measures, and write concise descriptions from confirmed information.
6. Update the documents when business definitions, sources, or model design decisions change.

These are suggested activities, not compulsory sequential approval steps. Keep assumptions and unresolved decisions clearly identified.

## Expected output

Agreed KPI definitions, a reviewable model specification, relevant table and measure documentation, and concise descriptions of model objects.

The templates document requirements and design; filling them in does not by itself validate an implementation or constitute production approval.

## Relationship to the other resources

| Resource | Role |
| --- | --- |
| [Decision Mapping Canvas](../01_decision_design/decision_mapping_canvas/README.md) | Clarifies which decision or action the information should support. |
| [Dashboard Canvas](../02_requirements_stakeholder/dashboard_canvas/README.MD) | Describes the requirements of a specific dashboard or report. |
| **KPI Definition Sheet** | Establishes the agreed meaning of a specific KPI. |
| **Semantic Model Specification** | Describes the model-wide design and its assumptions and constraints. |
| [Table Documentation](table_documentation/README.md) | Records a table's role, grain, relationships, and limitations. |
| [Measure Documentation](measure_documentation/README.md) | Records a measure's implementation, filter behavior, and validation. |
| [Metadata Description Guide](metadata_description_guide/README.md) | Supports concise, factual model-object descriptions. |
| [Semantic Model Review Checklist](../04_validation/semantic_model_review_checklist/README.md) | Records review evidence, findings, and readiness checks. |
| [Semantic Modeling Guideline](../../guidelines/Guideline_Semantic_Modelling_Power_BI.pdf) | Guides modeling, documentation, validation, and review in Power BI. |

## Templates

Choose the appropriate language version for each resource:

- **KPI Definition Sheet:** [English](kpi_definition/KPI_Template_EN.md) · [Deutsch](kpi_definition/KPI_Template_DE.md)
- **Semantic Model Specification:** [English](semantic_model_specification/SEMANTIC_MODEL_SPECIFICATION_EN.md) · [Deutsch](semantic_model_specification/SEMANTIC_MODEL_SPECIFICATION_DE.md)
- **Table Documentation:** [English](table_documentation/TABLE_DOCUMENTATION_EN.md) · [Deutsch](table_documentation/TABLE_DOCUMENTATION_DE.md)
- **Measure Documentation:** [English](measure_documentation/MEASURE_DOCUMENTATION_EN.md) · [Deutsch](measure_documentation/MEASURE_DOCUMENTATION_DE.md)
- **Metadata Description Guide:** [English](metadata_description_guide/METADATA_DESCRIPTION_GUIDE_EN.md) · [Deutsch](metadata_description_guide/METADATA_DESCRIPTION_GUIDE_DE.md)

See the individual resource overviews for further guidance.

## Changelog

- **2026-11-16:** Updated this overview to include table documentation, measure documentation, and the metadata description guide.
- **2026-11-16:** Aligned the guideline status and date with the current published version.

## Author and usage

**Data Therapy · Jasmin Simader**

Unless a resource states otherwise, consult the repository's [license](../../../LICENSE) for reuse terms.

## 🔗 Related content

🎥 YouTube: [Power BI with AI Vibes](https://www.youtube.com/@BIVibes-JasminSimader)  
🏠 Website: [Jasmin Simader](https://www.jasminsimader.com/)  
👩🏻‍💻 LinkedIn: [Jasmin Simader](https://www.linkedin.com/in/jasmin-simader)  
📝 Blog / Substack: [Substack](https://substack.com/@datatherapywithjasmin)

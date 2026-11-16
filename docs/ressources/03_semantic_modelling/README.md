![Banner](https://github.com/Jasmin319/Semantic-Modelling-Power-BI---DATA-THERAPY/blob/main/Brand%20Assets/Banner.png)

![Microsoft MVP](https://img.shields.io/badge/Microsoft-MVP-5E5E5E)

# Semantic Modelling Resources

**Connect agreed business definitions to a documented semantic model design.**

The resources in this folder help teams agree on the meaning of individual KPIs and describe how a semantic model is intended to meet its business and technical requirements. They complement the [Power BI Semantic Modeling Guideline](../../guidelines/Guideline_Semantic_Modelling_Power_BI.pdf).

Their guiding principle is:

> **Agree on meaning before calculation. Specify the model before implementation.**

## Purpose

A KPI definition and a model design answer different questions. The **KPI Definition Sheet** makes the meaning, scope, calculation, ownership, and validation of a specific measure explicit. The **Semantic Model Specification** records the model-wide design, assumptions, and open decisions.

These are practical supporting templates, not additional mandatory standards. The guideline is currently a draft.

## The two resources

| Resource | What it helps clarify |
| --- | --- |
| [**KPI Definition Sheet**](kpi_definition/README.md) | What does a specific KPI mean, where does it apply, how is it calculated, and how will it be validated? |
| [**Semantic Model Specification**](semantic_model_specification/README.md) | How should the semantic model meet its business and technical requirements, and how will its design be validated? |

## When to use them

- Use the **KPI Definition Sheet** when a measure's business meaning, scope, calculation, owner, or validation needs agreement.
- Use the **Semantic Model Specification** to record or review the design of a semantic model, including its context, sources, structure, security, operations, and risks.
- Use both when a model implements agreed KPIs and the relationship between business definitions and model design needs to remain traceable.

## Suggested workflow

1. Clarify the decision or business question the information should support, using the [Decision Mapping Canvas](../01_decision_design/decision_mapping_canvas/README.md) when helpful.
2. Agree on the meaning and validation of each relevant KPI with its business owner.
3. Record the model-wide design and reference the agreed KPI definitions rather than duplicating them.
4. Implement and review the model using the [Semantic Modeling Guideline](../../guidelines/Guideline_Semantic_Modelling_Power_BI.pdf).
5. Update the documents when business definitions, sources, or model design decisions change.

These are suggested activities, not compulsory sequential approval steps. Keep assumptions and unresolved decisions clearly identified.

## Expected output

An agreed description of important KPI meanings and a reviewable specification of the semantic model's intended design, constraints, validation, and open decisions.

The templates document requirements and design; filling them in does not by itself validate an implementation or constitute production approval.

## Relationship to the other resources

| Resource | Role |
| --- | --- |
| [Decision Mapping Canvas](../01_decision_design/decision_mapping_canvas/README.md) | Clarifies which decision or action the information should support. |
| [Dashboard Canvas](../02_requirements_stakeholder/dashboard_canvas/README.MD) | Describes the requirements of a specific dashboard or report. |
| **KPI Definition Sheet** | Establishes the agreed meaning of a specific KPI. |
| **Semantic Model Specification** | Describes the model-wide design and its assumptions and constraints. |
| [Semantic Model Review Checklist](../04_validation/semantic_model_review_checklist/README.md) | Records review evidence, findings, and readiness checks. |
| [Semantic Modeling Guideline](../../guidelines/Guideline_Semantic_Modelling_Power_BI.pdf) | Guides modeling, documentation, validation, and review in Power BI. |

## Templates

Create a copy of the appropriate language template for each KPI or semantic model:

- **KPI Definition Sheet:** [English](kpi_definition/KPI_Template_EN.md) · [Deutsch](kpi_definition/KPI_Template_DE.md)
- **Semantic Model Specification:** [English](semantic_model_specification/SEMANTIC_MODEL_SPECIFICATION_EN.md) · [Deutsch](semantic_model_specification/SEMANTIC_MODEL_SPECIFICATION_DE.md)

See each resource's [overview](kpi_definition/README.md) or [specification overview](semantic_model_specification/README.md) for further guidance.

## Author and usage

**Data Therapy · Jasmin Simader**

Unless a resource states otherwise, consult the repository's [license](../../../LICENSE) for reuse terms.

## 🔗 Related content

🎥 YouTube: [Power BI with AI Vibes](https://www.youtube.com/@BIVibes-JasminSimader)  
🏠 Website: [Jasmin Simader](https://www.jasminsimader.com/)  
👩🏻‍💻 LinkedIn: [Jasmin Simader](https://www.linkedin.com/in/jasmin-simader)  
📝 Blog / Substack: [Substack](https://substack.com/@datatherapywithjasmin)

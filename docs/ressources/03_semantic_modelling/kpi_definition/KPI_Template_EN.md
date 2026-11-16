# KPI Definition Sheet

**Business meaning before calculation. Ownership before publication.**

> **Note:** This template is based on Section 15.1, “Definition Sheet for a Key Business Measure,” of the *Power BI Semantic Modeling Guideline*, Version 0.1 (Draft), November 16, 2026. Complete all blank fields or mark them as “not applicable.” This is a template, not an already approved KPI definition.

## 1. Business KPI definition

| Field | Entry |
| --- | --- |
| **KPI name** | `[Name]` |
| **Business-approved synonyms / language or culture** | `[Alternative terms with the same meaning; record language/culture and business confirmation]` |
| **Business definition** | `[What does the KPI mean in the agreed business context?]` |
| **Scope** | `[Organizational units, business processes, products, periods, etc.]` |
| **Calculation** | `[Business calculation rule; numerator / denominator, inclusions and exclusions]` |
| **Unit / presentation** | `[e.g., EUR, %, units; rounding and format]` |
| **Data source(s)** | `[Owned data sources / data products]` |
| **Freshness** | `[Data as-of date, update frequency, and relevant delays]` |
| **Exceptions and limitations** | `[Known restrictions, comparability limits, special cases]` |
| **Decision use** | `[Which specific decision or business question does this support?]` |
| **Business owner** | `[Role / responsible person who confirms the meaning and changes]` |
| **Validation** | `[Reference values, test cases, comparison methods, and results]` |
| **Effective from** | `[YYYY-MM-DD or business validity rule]` |

## 2. Additional implementation details (optional)

_These fields supplement Section 15.1 by connecting the KPI to the Decision Mapping Canvas and the technical model specification._

| Field | Entry |
| --- | --- |
| **KPI ID** | `[e.g., KPI-001]` |
| **Decision reference** | `[e.g., DEC-001; optional]` |
| **Related business questions** | `[Question(s) / reference(s)]` |
| **Aggregation and time reference** | `[Additive, semi-additive, or non-additive; relevant date field]` |
| **Filter behavior / context** | `[Which filters affect the interpretation?]` |
| **Technical implementation** | `[Model name, measure name, link to technical documentation]` |
| **Technical contact** | `[Role / contact]` |
| **Definition status** | `[Draft / under review / business-approved]` |
| **Approved by / on** | `[Name or role / date; do not prefill]` |

## 3. Validation and business sign-off

| Test case | Expected result / reference | Actual result | Status |
| --- | --- | --- | --- |
| `[e.g., Total for reference period]` | `[Reference]` | `[Result]` | `[Open / Passed / Failed]` |
| `[e.g., Filter by region]` | `[Reference]` | `[Result]` | `[Open / Passed / Failed]` |
| `[e.g., Null, cancellation, or boundary case]` | `[Reference]` | `[Result]` | `[Open / Passed / Failed]` |

**Open questions:** `[Unconfirmed assumptions and items to clarify]`

## 4. Change history

| Version | Effective from | Change / reason | Business-approved by |
| --- | --- | --- | --- |
| `0.1` | `[Date]` | `[Initial version]` | `[Open / role]` |

---

**Important:** Do not derive the business definition solely from a DAX formula. Confirmation by the business owner must be treated separately from the technical implementation.

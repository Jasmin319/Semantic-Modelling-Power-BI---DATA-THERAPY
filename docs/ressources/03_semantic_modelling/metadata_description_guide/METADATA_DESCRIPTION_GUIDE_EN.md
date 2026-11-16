# Metadata Description Guide

**Clear, business-grounded descriptions for Power BI semantic model objects.**

Based on **Section 15.4**, **DOC-003** and **DOC-004** of *Semantic Modeling in Power BI*, v0.1 (Draft), November 7, 2026.

## 1. Principle

A model object's **Description** property gives users quick orientation. It is **not a substitute** for a KPI Definition Sheet, Table Documentation or Measure Documentation.

Use short, complete, neutral sentences. Add the context the name cannot convey. Do not repeat DAX syntax or invent sources, business rules, interpretations or limitations.

## 2. Sentence patterns from Section 15.4

**Table:**

> Contains [business content]. One row represents [granularity, where known and relevant]. The table serves as [model role / analytical purpose] for [relevant context]. [Significant, substantiated limitation.]

**Measure:**

> Calculates [metric] as [business calculation / reference base] for [relevant period or scope]. The result is expressed in [unit]. [Important, substantiated limitation or filter rule.]

Do not fill every placeholder if the detail is unknown or unnecessary for interpretation.

## 3. Illustrative examples (not approved business definitions)

| Object | Weak | Better, **if confirmed by the business** |
| --- | --- | --- |
| `FactSales` | “Sales data.” | “Contains sales document line items. One row represents one document line. The table provides transaction values for revenue analysis.” |
| `DimCustomer` | “Customer table.” | “Contains customer attributes used to group and filter sales transactions.” |
| `[Revenue]` | “SUM of revenue.” | “Calculates invoiced net revenue for the selected period in EUR.” |
| `[Margin %]` | “Profitability, higher is better.” | “Calculates margin as the ratio of contribution margin to net revenue and expresses the result as a percentage.” |
| `[Revenue YoY %]` | “Revenue growth.” | “Calculates the relative change in revenue compared with the equivalent prior-year period, expressed as a percentage.” |

**Note:** These examples use hypothetical definitions. The actual revenue basis, cancellation treatment and ratio denominator must be confirmed in the relevant business context.

## 4. Extra care for measures

- **Ratios:** Clarify the denominator and business reference base where relevant.
- **Comparisons:** Specify the comparison base and distinguish absolute differences from relative changes.
- **Periods:** Mention time scope if it materially changes interpretation.
- **Fixed filters:** Include them when confirmed and relevant to understanding.
- **Limitations:** Include only meaningful, substantiated limitations.

## 5. Quick review

- [ ] Explains meaning rather than repeating only the name.
- [ ] Includes content, grain and role for tables where relevant.
- [ ] Explains calculation basis and unit for measures where relevant.
- [ ] Explains ratios, comparisons and fixed filters where they affect interpretation.
- [ ] Uses neutral, concise, complete sentences.
- [ ] Business claims are confirmed; unresolved items remain open.
- [ ] Links to detailed documentation where necessary.

## 6. GitHub Copilot prompt

```text
Draft a short Power BI model-object Description.
Use only the verified facts supplied below.
Do not repeat DAX syntax or assume business definitions.
For tables, describe content, grain and role when confirmed.
For measures, describe business calculation basis, unit and
material limitations when confirmed.
Write 1–3 concise, neutral English sentences.
If important facts are missing, list them under
"Open business questions" rather than inventing them.

Object name: [Name]
Object type: [Table/Measure]
Confirmed facts: [Paste here]
```

Review Copilot output with the relevant business owner before using it as an authoritative definition.

## 7. Related documentation

- [Table Documentation](../table_documentation/README.md): source, keys, grain, relationships and history.
- [Measure Documentation](../measure_documentation/README.md): DAX, dependencies, filters and tests.
- [KPI Definition Sheet](../kpi_definition/README.md): agreed business meaning.

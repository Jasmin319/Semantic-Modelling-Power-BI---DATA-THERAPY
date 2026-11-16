# Semantic Model Specification

**From Business Requirements to a Reliable Semantic Model**

> Working template based on *Semantic Modeling in Power BI*, Version 0.1 (Draft), November 16, 2026. This specification is not a substitute for business approval or technical review.

**How to use:** Replace `[placeholders]`; mark unknown details **Open** and irrelevant items **Not applicable**. Distinguish **planned**, **implemented**, and **validated** information.

## 1. Model overview

| Field | Entry |
| --- | --- |
| Model ID / name | `[ID / name]` |
| Business domain and purpose | `[What business need is supported?]` |
| Intended consumers | `[Roles, applications, reports]` |
| Business owner | `[Accountable role]` |
| Technical owner / support | `[Role / contact]` |
| Version / status / date | `[e.g. 0.1 / Draft / YYYY-MM-DD]` |
| Power BI workspace / environment | `[Link / name]` |
| Implemented model / repository | `[Link when available]` |

## 2. Business context and scope

| Reference (optional) | Decision / business question | Intended use |
| --- | --- | --- |
| `[DEC-001 / BQ-001]` | `[Decision / question]` | `[Use]` |

**In scope:** `[Business domains, processes, periods]`  
**Out of scope:** `[Explicit boundaries]`  
**Key assumptions:** `[Items awaiting confirmation]`

**Natural-language query use (if applicable):** `[Target product and environment; intended questions]`

## 3. Data sources and dependencies

| Source / data product | Contents / ownership | Freshness / quality | Transformation / dependency |
| --- | --- | --- | --- |
| `[Source]` | `[Contents, owner]` | `[SLA or known limitation]` | `[Pipeline / contract reference]` |

**Missing / invalid data policy:** `[Agreed behavior or open decision]`

## 4. Planned model structure

### Tables and grain

| Table | Role | Business purpose | Grain (“One row represents ...”) | Keys / history |
| --- | --- | --- | --- | --- |
| `[Fact...]` | `[Fact]` | `[Purpose]` | `[One row represents ...]` | `[Key / rule]` |
| `[Dim...]` | `[Dimension]` | `[Purpose]` | `[One row represents ...]` | `[Key / SCD / unknown]` |

### Relationships and modeling decisions

| From → To | Cardinality / filter direction | Active / inactive | Rationale / risk |
| --- | --- | --- | --- |
| `[Table.Key → Table.Key]` | `[1:n / direction]` | `[Status]` | `[Business rationale]` |

**Model sketch / diagram:** `[Link to diagram / PBIP / design]`  
**Intentional deviations from star schema:** `[Rationale or none]`

## 5. KPIs and measures

| KPI ID | Approved KPI definition (link) | Measure name | Model-specific behavior / status |
| --- | --- | --- | --- |
| `[KPI-001]` | `[Link to KPI Definition Sheet]` | `[Measure]` | `[Open / Implemented / Reviewed]` |

**Note:** Keep the business definition, calculation, owner and reference validation in the KPI Definition Sheet. Link it here and document model-specific deviations only.

## 6. Time, aggregation and filters

| Topic | Design decision |
| --- | --- |
| Date table(s) and calendar logic | `[Calendar, fiscal year, limitations]` |
| Date roles | `[e.g. Order date, invoice date]` |
| Mixed granularities | `[e.g. Monthly plan / line-level actuals]` |
| Critical filter behavior | `[e.g. inactive relationships, M:M, custom filters]` |

## 7. Security and governance

| Topic | Requirement / evidence |
| --- | --- |
| Sensitive data / classification | `[Protected data categories]` |
| RLS / OLS / permissions | `[Roles, consumers, rules]` |
| Security groups / access reviews | `[Owners, documentation, review]` |
| Business change approval | `[Who confirms changes in definitions?]` |

## 8. Performance and operations

| Topic | Target / assumption / measurement |
| --- | --- |
| Storage mode and rationale | `[Import / DirectQuery / Composite / Direct Lake; why?]` |
| Volume / growth | `[Estimate or measured value]` |
| Refresh strategy | `[Frequency, windows, failure handling]` |
| Expected usage / performance target | `[Representative scenario]` |
| Operations / monitoring / support | `[Owner, process, contact]` |

## 9. Validation and acceptance

| Test / acceptance criterion | Expected / reference | Actual result / evidence | Owner / status |
| --- | --- | --- | --- |
| `[KPI vs approved reference]` | `[Expected]` | `[Link / result]` | `[Owner / Open]` |
| `[Grain and relationships]` | `[Expected]` | `[Link / result]` | `[Reviewer / Open]` |
| `[RLS/OLS in target environment]` | `[Expected]` | `[Link / result]` | `[Reviewer / Open]` |
| `[Refresh and performance]` | `[Expected]` | `[Link / result]` | `[Reviewer / Open]` |
| `[Dependent report regression]` | `[Expected]` | `[Link / result]` | `[Reviewer / Open]` |
| `[Natural-language queries / expected metric mapping, if applicable]` | `[Representative questions and expected mapping in target product]` | `[Link / result]` | `[Reviewer / Open]` |

**Business confirmation:** `[Who confirmed what and when?]`  
**Technical review:** `[Who, when, evidence]`  
**Production approval:** `[Separate approval reference, if applicable]`

## 10. Decisions, risks and changes

| ID | Open question / risk / exception | Decision / mitigation | Owner / due date / status |
| --- | --- | --- | --- |
| `[R-001]` | `[Description]` | `[Action]` | `[Owner / status]` |

### Change history

| Version | Date | Change | Reviewed / confirmed by |
| --- | --- | --- | --- |
| `0.1` | `[YYYY-MM-DD]` | `[Initial draft]` | `[Open]` |

---

**Scope:** This is a **model specification**, not a full metadata catalog. Use the KPI Definition Sheet for KPI definitions, the guideline for modeling quality rules, and the applicable review process for production approval.

# Semantic Model Review Checklist | EN

**Review before release: business-valid, technically sound, and traceable.**

> Based on Section 12.1 (Review checklist) of *Semantic Modeling in Power BI*, Version 0.1 (Draft), November 7, 2026. The checklist follows the source review points; tracking columns are supplemental working fields.

## 1. Review context

| Field | Entry |
| --- | --- |
| **Model name / link** | `[Enter]` |
| **Model version / commit / release** | `[Enter]` |
| **Environment (e.g. test/production)** | `[Enter]` |
| **Change / scope (new or existing model)** | `[Enter]` |
| **Business model owner** | `[Enter]` |
| **Technical contact** | `[Enter]` |
| **Business reviewer / date** | `[Enter]` |
| **Technical reviewer / date** | `[Enter]` |
| **Review depth and risk rationale** | `[Enter]` |
| **Linked model specification / KPI sheets** | `[Enter]` |

## 2. Review results

**Status:** `Pass` = satisfied, `Fail` = not satisfied, `Open` = unresolved, `N/A` = not applicable (justify).

Link each review point to traceable evidence (test report, screenshot, query, ticket, or other reference).

### Business meaning

| ID | Review criterion | Status | Evidence / comment |
| --- | --- | --- | --- |
| R-01 | Purpose, audience, and supported decisions are documented. | `Open` | `[Link / note]` |
| R-02 | Core concepts and KPIs have agreed definitions, scopes, and owners. | `Open` | `[Link / note]` |
| R-03 | Exceptions, limitations, and historical rules are documented. | `Open` | `[Link / note]` |

### Model structure

| ID | Review criterion | Status | Evidence / comment |
| --- | --- | --- | --- |
| R-04 | Each fact table has a defined granularity. | `Open` | `[Link / note]` |
| R-05 | Facts, dimensions, and keys are explainable from a business perspective. | `Open` | `[Link / note]` |
| R-06 | Key quality and cardinalities are verified. | `Open` | `[Link / note]` |
| R-07 | Filter directions and many-to-many relationships have been deliberately chosen. | `Open` | `[Link / note]` |
| R-08 | Plan-versus-actual and other differing granularities have been tested. | `Open` | `[Link / note]` |
| R-09 | Date dimension and date roles are modeled transparently. | `Open` | `[Link / note]` |

### Measures and DAX

| ID | Review criterion | Status | Evidence / comment |
| --- | --- | --- | --- |
| R-10 | Business-critical KPIs are explicit measures. | `Open` | `[Link / note]` |
| R-11 | Reusable base measures are used. | `Open` | `[Link / note]` |
| R-12 | Divisions, blank values, and aggregation behavior are checked against business meaning. | `Open` | `[Link / note]` |
| R-13 | Filter-context changes are checked and documented where needed. | `Open` | `[Link / note]` |
| R-14 | Format, unit, and business descriptions are appropriate. | `Open` | `[Link / note]` |
| R-15 | Business-critical totals are reconciled at detail and grand-total levels with source data or a business-approved report; repeat after model changes. | `Open` | `[Link / note]` |

### Data preparation and operations

| ID | Review criterion | Status | Evidence / comment |
| --- | --- | --- | --- |
| R-16 | Sources, freshness, keys, and transformations are traceable. | `Open` | `[Link / note]` |
| R-17 | Data types, currencies, and time references are consistent. | `Open` | `[Link / note]` |
| R-18 | Query folding and refresh behavior are checked where applicable. | `Open` | `[Link / note]` |
| R-19 | Storage mode is justified and representative performance is measured. | `Open` | `[Link / note]` |

### Security and documentation

| ID | Review criterion | Status | Evidence / comment |
| --- | --- | --- | --- |
| R-20 | Access, RLS/OLS, and sensitive data are verified in the target environment. | `Open` | `[Link / note]` |
| R-21 | Workspace roles and general access use purpose-specific security groups where supported; owners, memberships, reviews, direct exceptions, and effective permissions are verified/documented. | `Open` | `[Link / note]` |
| R-22 | Security groups follow an agreed naming convention indicating environment, access type, target, and role/permission scope. | `Open` | `[Link / note]` |
| R-23 | RLS roles, assigned groups, and memberships are documented and tested with representative identities; direct assignments are justified exceptions. | `Open` | `[Link / note]` |
| R-24 | Model owner, technical contact, and support are identified. | `Open` | `[Link / note]` |
| R-25 | Minimum documentation is complete; brief object descriptions are separated from catalog-level details. | `Open` | `[Link / note]` |
| R-26 | Descriptions complement names, are neutral, and contain no unsupported business assumptions. | `Open` | `[Link / note]` |
| R-27 | Changes to model metadata and definitions have been reviewed with a traceable record. | `Open` | `[Link / note]` |
| R-28 | Dependent reports have been regression-tested. | `Open` | `[Link / note]` |
| R-29 | Open exceptions are documented and approved. | `Open` | `[Link / note]` |

### Text-based development and automation

| ID | Review criterion | Status | Evidence / comment |
| --- | --- | --- | --- |
| R-30 | For PBIP/TMDL changes, the diff is reviewed for unintended modifications. | `Open` | `[Link / note]` |
| R-31 | After TMDL changes, syntax, properties, dependencies, and relevant reports were checked. | `Open` | `[Link / note]` |
| R-32 | Automated metadata checks use documented criteria and appropriate exceptions. | `Open` | `[Link / note]` |
| R-33 | AI-generated descriptions were reconciled with model metadata and business definitions; unresolved assumptions were not treated as facts. | `Open` | `[Link / note]` |

## 3. Production release (Section 12.2)

The following seven conditions mirror the guideline release section; completing a review is not automatically release approval.

| ID | Release condition | Status | Evidence / approval |
| --- | --- | --- | --- |
| G-01 | Business owner confirms critical definitions and KPI results, including source/reference reconciliation. | `Open` | `[Link / name / date]` |
| G-02 | Model, relationships, and data quality have been reviewed. | `Open` | `[Link / name / date]` |
| G-03 | Security and permissions have been tested in the target environment. | `Open` | `[Link / name / date]` |
| G-04 | Performance and refresh have been evaluated for agreed scenarios. | `Open` | `[Link / name / date]` |
| G-05 | Dependent reports have been regression-tested. | `Open` | `[Link / name / date]` |
| G-06 | Documentation, operations, and support are arranged. | `Open` | `[Link / name / date]` |
| G-07 | Release approval and approved exceptions are traceable; changes are versioned and reviewed where required by process. | `Open` | `[Link / name / date]` |

## 4. Exceptions and actions (Section 13)

**Note:** Record the Section 13 fields for deviations from proposed MUST rules and obtain accountable approval. The draft classifications are only binding after formal adoption.

| Exception ID | Rule ID | Model / scope | Rationale / alternatives | Risks / controls | Approval | Review date |
| --- | --- | --- | --- | --- | --- | --- |
| `[EX-001]` | `[e.g. MOD-003]` | `[Scope]` | `[Details]` | `[Details]` | `[Owner / date]` | `[Date]` |

## 5. Outcome and release decision

| Field | Entry |
| --- | --- |
| **Open critical findings** | `[Count / references]` |
| **Review result** | `[Passed / Failed / Open]` |
| **Release decision** | `[Approved / Not approved / Open]` |
| **Accountable approval** | `[Role / person / date / ticket]` |
| **Next review date** | `[Date / trigger]` |

> This template records a review; it does not replace business validation or actual release authorization under the organization’s process.

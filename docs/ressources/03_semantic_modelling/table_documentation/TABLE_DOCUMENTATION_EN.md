# Table Documentation

**Working template based on Section 15.2 of the Power BI Semantic Modeling Guideline (v0.1, Draft).**

> Create one record per table, or maintain equivalent information in a governed catalog. Use `[Open]` when something has not been confirmed. Optional implementation and validation fields extend the guideline.

## 1. Table profile

| Section 15.2 field | Entry |
| --- | --- |
| Table name | `[Name in semantic model]` |
| Role | `[Fact / dimension / bridge / aggregation / parameter / other]` |
| Business purpose | `[What it contains and its analytical role]` |
| Source | `[Source system, object, data product and relevant transformations]` |
| Granularity | **One row represents …** `[precise business statement]` |
| Primary / unique key | `[Key column(s), uniqueness rules]` |
| Important foreign keys | `[Columns and referenced tables]` |
| Relationships / special filter logic | `[Related tables, cardinality, filter direction, inactive relationships, exceptions]` |
| Historical handling | `[Current-only / historical records; effective date rules]` |
| Unknown-member rules | `[Treatment of missing, invalid or unmatched keys]` |
| Key attributes | `[Business-relevant columns and meanings]` |
| Known limitations | `[Gaps, comparability constraints, incomplete periods, etc.]` |
| Business owner | `[Role / confirming person]` |
| Technical contact | `[Role / contact]` |
| Refresh | `[Frequency, data-as-of point, delays]` |

## 2. Additional implementation fields (optional)

| Field | Entry |
| --- | --- |
| Model / environment / link | `[Link to PBIP/TMDL or model]` |
| Dependent KPIs / reports | `[References, not duplicate definitions]` |
| Data-quality tests | `[Key uniqueness, nulls, referential integrity, row counts, etc.]` |
| Relevant security | `[RLS/OLS or link to security documentation]` |
| Planned / verified state | `[Draft / implemented / verified]` |

## 3. Review evidence (optional)

| Check | Expected / reference | Evidence / outcome | Status |
| --- | --- | --- | --- |
| Grain is clear and consistent | `[Expected]` | `[Evidence]` | `Open` |
| Key on the one-side is unique and nonblank | `[Expected]` | `[Evidence]` | `Open` |
| Foreign keys and unknown members handled | `[Expected]` | `[Evidence]` | `Open` |
| Relationship / filter behavior tested | `[Expected]` | `[Evidence]` | `Open` |
| History and freshness verified | `[Expected]` | `[Evidence]` | `Open` |

## 4. Short model-object Description

`Contains [business content]. One row represents [grain, where known and relevant]. The table serves as [model role / analytical purpose] for [context]. [Significant supported limitation, if necessary.]`

**Confirmed Description:** `[Insert a concise, neutral sentence.]`

A model-object Description is **not** a replacement for this record. See the [Metadata Description Guide](../metadata_description_guide/README.md).

## 5. Change and clarification history

| Version | Date | Change / open issue | Confirmed by |
| --- | --- | --- | --- |
| `0.1` | `[Date]` | `[Initial draft]` | `[Open]` |

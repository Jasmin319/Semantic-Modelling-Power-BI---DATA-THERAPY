# Measure Documentation

**Working template based on Section 15.3 of the guideline (v0.1, Draft).**

> Where a KPI Definition Sheet exists, it is the source for the approved business meaning. This document describes the measure's specific implementation. Mark unconfirmed facts as `[Open]`.

## 1. Meaning and implementation

| Section 15.3 field | Entry |
| --- | --- |
| Measure name | `[Power BI name]` |
| Business definition | `[Brief meaning or link to confirmed KPI Definition Sheet]` |
| Supported decision | `[Business question / DEC ID or Not applicable]` |
| DAX expression | `See code block below` |
| Brief technical description | `[Calculation explained in plain language]` |
| Referenced measures | `[Names / links]` |
| Referenced tables / columns | `[Names / links]` |
| Filter behavior | `[Which report/model filters ordinarily affect the result?]` |
| Filter context modifications | `[ALL, REMOVEFILTERS, USERELATIONSHIP, etc., only where actually used; purpose]` |
| Unit | `[EUR / % / units / other]` |
| Format | `[Format string / dynamic format / rounding]` |
| Aggregation behavior | `[Additive / semi-additive / non-additive; total vs detail]` |
| Exceptions, limitations and pitfalls | `[Blanks, zero denominators, edge cases and interpretation limits]` |
| Business owner | `[Role / confirming person]` |
| Validation | `[Comparison method / trusted values / test evidence link]` |

### DAX

```dax
-- Paste the DAX from the actual model here.
-- Do not assume unconfirmed business rules.
```

## 2. Additional details (optional)

| Field | Entry |
| --- | --- |
| Reference / ID | `[Measure ID / KPI ID]` |
| Model / display folder | `[Model and location]` |
| Implementation status | `[Planned / implemented / verified]` |
| Technical owner | `[Role / contact]` |
| Deviation from KPI definition | `[None / open deviation and rationale]` |

## 3. Validation tests (optional)

| Test case | Expected / source | Actual result | Status |
| --- | --- | --- | --- |
| Detail value | `[Reference]` | `[Result]` | `Open` |
| Grand total | `[Reference]` | `[Result]` | `Open` |
| Filter / time context | `[Reference]` | `[Result]` | `Open` |
| Blanks / edge cases | `[Reference]` | `[Result]` | `Open` |

## 4. Short model-object Description

`Calculates [metric] as [business calculation / reference base] for [period or scope]. The result is expressed in [unit]. [Important substantiated limitation or filter rule.]`

**Confirmed Description:** `[Short, neutral, business-confirmed text.]`

## 5. Change history

| Version | Date | Change | Business / technical reviewer |
| --- | --- | --- | --- |
| `0.1` | `[Date]` | `[Initial draft]` | `[Open]` |

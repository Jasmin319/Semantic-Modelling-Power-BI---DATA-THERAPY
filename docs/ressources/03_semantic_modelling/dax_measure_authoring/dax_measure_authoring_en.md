# DAX Measure Authoring Guide

**A practical proposal for Power BI measure names, DAX code, comments, metadata and review.**

> Status: Proposed companion resource. The existing Semantic Modeling Guideline, v0.1 (Draft), remains the source for its published rules. Examples are illustrative and require approved business definitions and data-model validation.

## 1. Choose a naming convention

**Recommended default: readable business names with spaces, no generic `m_` / `msr_` prefix.** This aligns with existing `NAM-001`–`NAM-005`. Do not mix German and English names arbitrarily within a model; decide the naming language for its audience.

### Three approaches

| Approach | Example | Strength | Trade-off |
| --- | --- | --- | --- |
| **A. Business-first + consistent suffix (recommended)** | `Revenue`, `Revenue PY`, `Revenue vs PY`, `Revenue vs PY %` | Concise, clear in report field lists | Agree on acronyms such as `PY` |
| **B. Full descriptive names** | `Revenue Previous Year`, `Revenue Change vs Previous Year %` | Understandable to nontechnical users | Longer names in visuals |
| **C. Prefix every measure** | `m_Revenue`, `KPI_Revenue` | Differentiates measures in some technical workflows | Adds noise for business users; contrary to guideline preference for visible measures |

**Scope of the recommendation:** names are *proposals*, not hardcoded semantics. The actual business definition is owned by the KPI Definition Sheet. For a model serving several languages, also manage translations and approved synonyms where supported.

### Suggested naming patterns (approach A)

| Type | Pattern | Example | Meaning requiring confirmation |
| --- | --- | --- | --- |
| Core measure | `<Business concept>` | `Revenue` | Specific approved revenue definition |
| Absolute total | `<Concept> Amount` or `<Concept>` | `Discount Amount` | Sum/aggregation rules |
| Count | `<Entity> Count` | `Order Count` | Distinct vs row count |
| Minimum / maximum | `Minimum <Concept>` / `Maximum <Concept>` | `Minimum Price`, `Maximum Price` | Underlying rows and unit |
| Deliberately modified filter scope | `<Concept> All <Dimension>` | `Revenue All Regions` | Exactly which filters remain or are removed |
| Average | `Average <Concept>` | `Average Order Value` | Denominator and population |
| Rate | `<Concept> %` | `Gross Margin %` | Numerator, denominator and scale |
| Prior-year comparison | `<Concept> PY` | `Revenue PY` | Comparable period and date role |
| Year-to-date | `<Concept> YTD` | `Revenue YTD` | Calendar, cut-off and fiscal rules |
| Absolute comparison | `<Concept> vs PY` | `Revenue vs PY` | Difference in the same unit |
| Relative comparison | `<Concept> vs PY %` | `Revenue vs PY %` | Ratio and behavior for zero / blank denominator |
| Actual/budget variants | `<Concept> Actual` / `<Concept> Budget` | `Revenue Actual` | Definition and plan grain |
| Formatting-only (optional) | `F_<Concept>_<Purpose>` | `F_Revenue_Color` | Only for technical presentation measures, with matching display folders |

**Important:** `Revenue vs PY` is an **absolute amount difference** and `Revenue vs PY %` is a **relative percentage change** in this proposed convention. The names alone do not authorize any specific calculation. Use `%` for rates, not for percentage-point differences; if subtracting two percentages, explicitly label the result as **percentage points**. Avoid `Revenue1`, `Revenue Final`, `Sales2`, `Calc_7`, `Measure_3`, vague `Variance`, and unexplained abbreviations. Prefer one term (`Revenue`) rather than mixing `Sales` and `Revenue` when they refer to the same agreed KPI. Maintain approved synonyms separately from the canonical measure name.

### Aggregation method, aggregation behavior and filter context are not the same

A measure name should communicate **business meaning and any material distinction in how the result is calculated**, not merely repeat the function used in the formula.

| Aspect | What it means | Illustrative case | Naming / documentation guidance |
| --- | --- | --- | --- |
| **Calculation / aggregation method** | DAX method, such as `SUM`, `AVERAGE`, `DISTINCTCOUNT`, or a ratio of measures | `SUM ( FactSales[NetAmount] )` | Name `Revenue` when that is the approved definition; reserve `Average ...` for an explicitly defined averaging basis |
| **Aggregation behavior** | Whether a result can be combined across dimensions and time | Revenue is often additive; period-end inventory is semi-additive; a percentage is usually non-additive | Document separately; do not infer it from `SUM` or `%` alone |
| **Filter-context behavior** | Whether the measure preserves, replaces or removes filters | `REMOVEFILTERS ( DimRegion )` | Use a qualified name such as `Revenue All Regions` only when that scope materially matters |

**Why this matters:**

- `AVERAGE ( FactSales[NetAmount] )` means **average line amount**, assuming one row per line. It does not mean average order value.
- `Average Order Value` is often `DIVIDE ( [Revenue], [Order Count] )`, where Order Count is based on unique orders. The exact population, exclusions and count logic must be confirmed.
- `Order Count` can mean distinct orders; `Order Line Count` can mean fact rows. Document both precisely.
- `ALL` is a DAX filter/table function, not an aggregation type. Prefer `REMOVEFILTERS` when the intent is solely to clear filters in `CALCULATE`, where supported.
- `Revenue All Regions` removes region filters, not automatically date, product, security or all other filters. Do not suggest it bypasses row-level security.

**Recommended default:** do not append `_SUM`, `_AVG` or `_ALL` to every measure. Instead, make `Average`, `Count`, `Minimum`, `Maximum`, a comparison basis or a deliberately different filter scope explicit when they change interpretation. The canonical names and approved synonyms must remain consistent with the KPI Definition Sheet.

## 2. DAX expression style

1. **Reuse explicit base measures** for business-critical metrics (`DAX-001/002`).
2. **Use descriptive `VAR` names in PascalCase** (for example `CurrentRevenue`, `PreviousYearRevenue`) when they make logic easier to read; use `RETURN` on its own line. A final `Result` variable is optional for longer calculations.
3. **Use uppercase DAX functions** (`CALCULATE`, `DIVIDE`), consistent spaces and indentation, and one argument per line in complex calls.
4. **Qualify column references with tables** (`FactSales[NetAmount]`), while using unqualified measure references (`[Revenue]`) where unambiguous.
5. **Prefer `DIVIDE`** when a denominator can be zero or blank. Do not automatically turn missing values into zero; this is a business decision (`DAX-003`).
6. **Review filters and date semantics** with `CALCULATE`, `ALL`, `REMOVEFILTERS`, `USERELATIONSHIP`, `TREATAS` etc. (`DAX-005`). `ALL` is not an aggregation method: specify which filters remain, which are removed, and whether the result behaves differently in totals.
7. **Avoid `FORMAT()` as general numeric formatting**: use model format strings instead (`DAX-007`). Keep numeric results numeric.
8. **Use `SUMX`, `FILTER`, and other iterators when required**, not when a simpler expression correctly expresses the business logic (`DAX-004`).

### Example: totals, averages and intentional filter removal

The examples assume `FactSales` contains one row per **order line**, `FactSales[OrderID]` identifies orders, and `DimRegion` is the intended region dimension. These are illustrative model assumptions, **not** validated facts about a real dataset.

```dax
Revenue =
    SUM ( FactSales[NetAmount] )

Average Line Amount =
    AVERAGE ( FactSales[NetAmount] )

Order Count =
    DISTINCTCOUNT ( FactSales[OrderID] )

Average Order Value =
    DIVIDE ( [Revenue], [Order Count] )

Revenue All Regions =
    // Remove region filters only; other relevant filters stay active.
    CALCULATE (
        [Revenue],
        REMOVEFILTERS ( DimRegion )
    )
```

`Average Line Amount` and `Average Order Value` are **different measures**. Their names indicate the averaging grain. For `Revenue All Regions`, verify relationships, expected slicer behavior and security in the actual model.

An **inventory balance** may be additive across items or locations but *not over time*, even if its daily snapshot is calculated using `SUM`. A **margin percentage** is normally non-additive and must be calculated from relevant base values, not by summing percentages.

### Example: a basic measure and a comparison

The examples assume a valid `FactSales[NetAmount]` column and a correctly modeled date dimension named `Date`. They do **not** establish whether that column is the approved revenue source.

```dax
Revenue =
    SUM ( FactSales[NetAmount] )

Revenue PY =
    CALCULATE (
        [Revenue],
        SAMEPERIODLASTYEAR ( 'Date'[Date] )
    )

Revenue vs PY % =
    VAR CurrentRevenue = [Revenue]
    VAR PreviousYearRevenue = [Revenue PY]
    // A missing or zero prior-year amount has no usable percentage base.
    RETURN
        DIVIDE (
            CurrentRevenue - PreviousYearRevenue,
            PreviousYearRevenue
        )
```

Validate missing/current-period scenarios, comparable periods and fiscal/calendar semantics. The chosen time-intelligence function is illustrative, not universally applicable.

## 3. Three documentation layers: do not confuse them

| Layer | What it explains | Where it is stored |
| --- | --- | --- |
| **DAX comments** | *Why* a technical choice was made: non-obvious filter, exception, BLANK handling | Inside the DAX expression, using `//` or `/* ... */` |
| **Measure Description** | *What* the measure means in business terms: quantity, aggregation basis / grain, filter scope, relevant period/unit/limitation | Measure **Description** property, or `///` in supported DAX Query View / TMDL workflows |
| **Full measure documentation** | Business owner, dependencies, test cases, detailed logic, validation, history | [Measure Documentation](../measure_documentation/README.md) and approved [KPI Definition](../kpi_definition/README.md) |

### Write helpful comments in the expression

```dax
Revenue vs PY % =
    VAR CurrentRevenue = [Revenue]
    VAR PreviousYearRevenue = [Revenue PY]
    // Maintain BLANK when the reference period has no meaningful denominator.
    // Confirm the intended behavior with the business owner.
    RETURN
        DIVIDE (
            CurrentRevenue - PreviousYearRevenue,
            PreviousYearRevenue
        )
```

Avoid redundant comments such as `// Calculate the revenue` immediately above `SUM(...)`; avoid unverified rules, people's names as ownership metadata, and obsolete notes. Comments must be reviewed whenever logic changes.

### Save the actual model Description directly from DAX Query View

**In DAX Query View**, insert `///` lines immediately above a `MEASURE` definition in a `DEFINE` block, then use **Update model with changes** (or the per-measure CodeLens action). Microsoft documents that this saves the Description in the model. Merely executing the query does **not** persist the measure or its description.

```dax
DEFINE
    /// Illustrative revenue measure based on the approved net-amount input.
    /// Returns a monetary amount in the active filter context.
    MEASURE '_Measures'[Revenue] =
        SUM ( FactSales[NetAmount] )

EVALUATE
    ROW ( "Revenue", [Revenue] )
```

Use such wording **only when the definition is approved**. A model Description must explain verified business meaning rather than simply narrating the DAX syntax. Setting `///` comments *inside the ordinary measure formula bar* does not by itself set the model Description property.

### TMDL / PBIP example

In TMDL, the `///` lines directly above the `measure` object declaration are its Description:

```tmdl
table _Measures
    /// Illustrative revenue amount for the current filter context.
    measure Revenue = SUM ( FactSales[NetAmount] )
        formatString: #,##0.00
```

**Important:** `///` above the declaration and `//` within the expression serve different purposes. Metadata also includes **FormatString**, **DisplayFolder**, and agreed **synonyms** (maintained via linguistic/culture metadata where supported); these properties do not arise from DAX comments. Review PBIP/TMDL diffs and the relevant culture files when synonyms change.

## 4. Measure metadata checklist

- [ ] Clear, consistent canonical name and no unnecessary technical prefix
- [ ] Average / count / ratio names state their actual business denominator or grain
- [ ] Calculation method and aggregation behavior (additive / semi-additive / non-additive) recorded where relevant
- [ ] Intentional filter removal is disclosed in the name or Description; impact on totals, slicers and security assessed
- [ ] Business definition approved (link to KPI Definition Sheet)
- [ ] Description matches that definition and documents decisive context/limitations
- [ ] Technical comments explain relevant non-obvious choices, not self-evident syntax
- [ ] Format string and numeric data type appropriate; `%` and units consistent
- [ ] Display folder makes the measure discoverable; technical-only measures separated or hidden as appropriate
- [ ] Synonyms checked with business owners, including possible ambiguous names
- [ ] Results validated at totals and detailed slices; time/BLANK/zero/filter cases tested
- [ ] Changes to DAX, description and synonyms reviewed together
- [ ] For Copilot / Fabric data agent use, representative natural-language questions tested in the actual target experience

## 5. Suggested Copilot prompt

```text
Review this DAX measure using the repository's DAX Measure Authoring Guide.
Propose a business-facing name that distinguishes averages, counts and filter scope
when relevant; specify the calculation method and additive behavior;
provide formatted DAX with helpful comments,
and a concise model Description suitable for DAX Query View (///).
Use only the approved KPI definition and confirmed source fields I provide.
Do not invent exclusions, time rules, meanings, synonyms, or data-quality guarantees.
Preserve numerical results and filter semantics. Explain any proposed
behavior change and provide validation tests. Do not apply model changes.
```

## Reference and scope

**Guideline-derived:** `NAM-001`–`NAM-005`, `DAX-001`–`DAX-007`, `DOC-002`–`DOC-004`, Section 15.3–15.4. **Supplementary proposals:** exact naming suffixes and aggregation naming examples, code-comment approach, optional `Result` variable and integration of DAX Query View `///` into a repeatable workflow.

**External technical references:** [Microsoft DAX Query View](https://learn.microsoft.com/en-us/power-bi/transform-model/dax-query-view), [Microsoft CALCULATE](https://learn.microsoft.com/en-us/dax/calculate-function-dax), [Microsoft REMOVEFILTERS](https://learn.microsoft.com/en-us/dax/removefilters-function-dax), [Microsoft TMDL](https://learn.microsoft.com/en-us/analysis-services/tmdl/tmdl-overview), [SQLBI naming](https://docs.sqlbi.com/dax-style/dax-naming-conventions), [SQLBI formatting](https://docs.sqlbi.com/dax-style/dax-format), [Microsoft data agent best practices](https://learn.microsoft.com/en-us/fabric/data-science/semantic-model-best-practices).

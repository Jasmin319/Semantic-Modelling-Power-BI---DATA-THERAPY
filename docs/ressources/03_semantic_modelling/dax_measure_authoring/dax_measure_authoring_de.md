# Leitfaden: DAX-Measures schreiben und dokumentieren

**Verständliche Namen. Lesbarer DAX-Code. Fachlich bestätigte Metadaten.**

> Status: Ergänzender Vorschlag zur Guideline *Semantische Modellierung in Power BI*, Version 0.1 (Entwurf). Die dargestellten Namensmuster und Beispiele sind Vorschläge und keine bereits verbindlich freigegebenen Organisationsstandards.

## 1. Namenskonventionen

**Empfohlener Ansatz:** fachlich verständliche Measure-Namen mit Leerzeichen, ohne pauschale Präfixe wie `m_` oder `msr_`. Das entspricht `NAM-001` bis `NAM-006`. Sprache und Benennungslogik werden pro Modell abgestimmt.

### Drei Optionen

| Option | Beispiele | Einordnung |
| --- | --- | --- |
| **A. Fachname + konsistenter Suffix (Empfehlung)** | `Revenue`, `Revenue PY`, `Revenue vs PY`, `Revenue vs PY %` | Kurz und gut in Feldlisten lesbar, Abkürzungen müssen definiert sein |
| **B. Ausgeschriebene Namen** | `Revenue Previous Year`, `Revenue Change vs Previous Year %` | Für nichttechnische Zielgruppen leicht verständlich, längere Namen |
| **C. Technische Präfixe für alle Measures** | `m_Revenue`, `KPI_Revenue` | Für fachlich sichtbare Measures eher nicht sinnvoll; `NAM-005/006` empfehlen solche Präfixe nicht allgemein |

### Vorgeschlagene Muster (Option A)

| Typ | Namensmuster | Beispiel | Fachlich zu klären |
| --- | --- | --- | --- |
| Basismessgröße | `<Begriff>` | `Revenue` | Bestätigte Umsatzdefinition |
| Betrag | `<Begriff> Amount` oder `<Begriff>` | `Discount Amount` | Vorzeichen und Aggregation |
| Anzahl | `<Objekt> Count` | `Order Count` | Zeilenzahl oder eindeutige Objekte |
| Minimum / Maximum | `Minimum <Begriff>` / `Maximum <Begriff>` | `Minimum Price`, `Maximum Price` | Grundgesamtheit und Einheit |
| Bewusst veränderter Filterkontext | `<Begriff> All <Dimension>` | `Revenue All Regions` | Welche Filter entfernt bzw. beibehalten werden |
| Durchschnitt | `Average <Begriff>` | `Average Order Value` | Nenner und betrachtete Grundgesamtheit |
| Quote | `<Begriff> %` | `Gross Margin %` | Zähler, Nenner, Prozentformat |
| Vergleichsperiode | `<Begriff> PY` | `Revenue PY` | Vorjahreszeitraum und Datumsrolle |
| Laufendes Jahr | `<Begriff> YTD` | `Revenue YTD` | Stichtag und Kalender-/Geschäftsjahr |
| Absolute Abweichung | `<Begriff> vs PY` | `Revenue vs PY` | Ergebnis in der Ausgangseinheit |
| Relative Abweichung | `<Begriff> vs PY %` | `Revenue vs PY %` | Prozentänderung zur Referenzbasis |
| Ist/Plan | `<Begriff> Actual` / `<Begriff> Budget` | `Revenue Actual` | Planungsgranularität und Gültigkeit |
| Formatierungs-Measure (optional) | `F_<Begriff>_<Zweck>` | `F_Revenue_Color` | Nur für technische Darstellungslogik, wenn im Modell vereinbart |

In diesem **vorgeschlagenen** Muster liefert `Revenue vs PY` eine **absolute Differenz** und `Revenue vs PY %` eine **relative prozentuale Änderung**. Das ist zu dokumentieren; der Name allein definiert keine Berechnungsregel. Die Differenz zwischen zwei Prozentwerten ist in **Prozentpunkten** anzugeben, nicht automatisch in `%`. Verwende keine mehrdeutigen Namen wie `Revenue Final`, `Sales2`, `Variance` ohne Bezugsbasis oder unbekannte Kürzel. Für dasselbe fachlich bestätigte Konzept einen kanonischen Namen wählen und gegebenenfalls Synonyme im Modell pflegen.

### Drei unterschiedliche Eigenschaften: Methode, Aggregierbarkeit und Filterkontext

Der Measure-Name soll die **fachliche Bedeutung** beschreiben und Berechnungsunterschiede sichtbar machen, wenn sie für die Interpretation wichtig sind. Er muss nicht die verwendete DAX-Funktion wiederholen.

| Eigenschaft | Bedeutung | Beispiel | Empfehlung |
| --- | --- | --- | --- |
| **Berechnungs-/Aggregationsmethode** | Eingesetzte Berechnung wie `SUM`, `AVERAGE`, `DISTINCTCOUNT` oder Quotient zweier Measures | `SUM ( FactSales[NetAmount] )` | `Revenue` ist möglich, wenn diese Definition bestätigt ist; `Average` verwenden, wenn die Durchschnittsbasis relevant ist |
| **Aggregierbarkeit** | Darf die Kennzahl über Dimensionen und Zeit summiert werden? | Umsatz meist additiv; Lagerbestand über Zeit semi-additiv; Quote meist nicht additiv | Unabhängig von der DAX-Funktion dokumentieren |
| **Filterkontext** | Welche Filter bleiben bestehen, werden ersetzt oder entfernt? | `REMOVEFILTERS ( DimRegion )` | Bei wesentlicher Veränderung den Geltungsbereich benennen, z. B. `Revenue All Regions` |

**Fachlich wichtige Unterschiede:**

- `AVERAGE ( FactSales[NetAmount] )` berechnet bei einem Faktengrain von einer Zeile je Belegposition den **Durchschnitt je Position**, nicht automatisch den durchschnittlichen Auftragswert.
- `Average Order Value` ist häufig `DIVIDE ( [Revenue], [Order Count] )`. Der Nenner und die Grundgesamtheit müssen bestätigt sein.
- `Order Count` kann eindeutige Aufträge zählen; `Order Line Count` einzelne Faktzeilen. Beides ist nicht austauschbar.
- `ALL` ist eine DAX-Tabellen-/Filterfunktion und **kein Aggregationstyp**. Für das reine Entfernen von Filtern in `CALCULATE` ist `REMOVEFILTERS` oft die klarere Wahl.
- `Revenue All Regions` entfernt beispielsweise Regionsfilter, aber nicht automatisch Datums-, Produkt-, sonstige Filter oder Row-Level Security.

**Namensempfehlung:** Keine pauschalen Suffixe wie `_SUM`, `_AVG` oder `_ALL`. Stattdessen Durchschnitt, Anzahl, Vergleichsbasis oder besondere Filterreichweite explizit machen, **wenn** sie die Bedeutung verändern. Fachlich bestätigte Namen und Synonyme konsistent halten.

## 2. Wie guter DAX geschrieben wird

1. **Geschäftskritische Kennzahlen als explizite Measures** und freigegebene Basis-Measures wiederverwenden (`DAX-001/002`).
2. **Sprechende Variablennamen** in PascalCase, zum Beispiel `CurrentRevenue`, `PreviousYearRevenue`; `VAR` und `RETURN` gut lesbar platzieren (`DAX-004`). Eine abschließende Variable `Result` kann bei komplexen Formeln sinnvoll sein, ist aber optional.
3. **Einheitliche Formatierung:** Funktionsnamen großschreiben, Leerzeichen an Operatoren und Klammern, bei mehreren Argumenten übersichtlich umbrechen.
4. **Spalten mit Tabelle referenzieren**, zum Beispiel `FactSales[NetAmount]`; Measures in der Regel ohne Tabellenpräfix (`[Revenue]`).
5. **DIVIDE** bei möglicherweise leerem oder nullwertigem Nenner verwenden; `BLANK()` nicht ungeprüft durch 0 ersetzen (`DAX-003`).
6. **Filterkontext dokumentieren und testen**, besonders bei `CALCULATE`, `ALL`, `REMOVEFILTERS`, `USERELATIONSHIP` und `TREATAS` (`DAX-005/008`). `ALL` ist kein Aggregationsverfahren: benenne gezielt entfernte Filter und prüfe Summen und Detailkontexte.
7. **Numerische Measures numerisch lassen** und über FormatString formatieren; `FORMAT()` nicht für die allgemeine Kennzahlenformatierung einsetzen (`DAX-007`).
8. **Iterationen wie `SUMX` nur bei fachlichem Bedarf** verwenden, nicht als Ersatz für einfache Summen (`DAX-004`).

### Beispiel: Summe, Durchschnitt, Anzahl und abweichender Filterkontext

Die Beispiele setzen voraus, dass `FactSales` **eine Zeile pro Auftragsposition** enthält, `FactSales[OrderID]` die Aufträge identifiziert und `DimRegion` die relevante Regionendimension ist. Das sind Modellannahmen, keine validierten Aussagen über echte Daten.

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
    // Nur Regionsfilter aufheben; andere gültige Filter bleiben erhalten.
    CALCULATE (
        [Revenue],
        REMOVEFILTERS ( DimRegion )
    )
```

`Average Line Amount` und `Average Order Value` haben unterschiedliche fachliche Grundlagen. Für `Revenue All Regions` müssen Beziehungen, das Verhalten von Slicern und die Sicherheit geprüft werden.

Ein **Lagerbestand** kann über Produkte additiv sein, aber **nicht über die Zeit** (semi-additiv), auch wenn die tägliche Bestandsmenge mit `SUM` gebildet wird. Eine **Marge in Prozent** ist üblicherweise nicht additiv und sollte aus geeigneten Basiswerten statt aus aufsummierten Prozentsätzen berechnet werden.

### Beispiel (nur Illustration)

Vorausgesetzt wird eine gültige Spalte `FactSales[NetAmount]` und eine geeignete Datumstabelle `Date`. Ob diese Grundlage den *fachlich freigegebenen Umsatz* abbildet, ist separat zu bestätigen.

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
    // Ohne sinnvollen Vorjahresnenner wird kein Prozentwert berechnet.
    RETURN
        DIVIDE (
            CurrentRevenue - PreviousYearRevenue,
            PreviousYearRevenue
        )
```

Zeitvergleich, fehlende Perioden, unterschiedliche Datumsrollen und Sonderfälle immer mit echten Testfällen validieren.

## 3. Drei Ebenen der Dokumentation

| Ebene | Inhalt | Ort |
| --- | --- | --- |
| **DAX-Kommentar** | Technisches *Warum*: besondere Filter, Annahmen oder Randfälle | `//` oder `/* ... */` **im DAX-Ausdruck** |
| **Measure-Description** | Fachliches *Was*: Kennzahl, Aggregationsbasis/Granularität, Filterreichweite, Zeitraum, Einheit und relevante Einschränkungen | **Description-Eigenschaft** des Measures; alternativ `///` in DAX Query View / TMDL |
| **Ausführliche Dokumentation** | Fachliche Definition, Verantwortliche, Abhängigkeiten, Tests, Änderungen | [Measure Documentation](../measure_documentation/README.md) und [KPI-Steckbrief](../kpi_definition/README.md) |

### Kommentare im DAX-Ausdruck

```dax
Revenue vs PY % =
    VAR CurrentRevenue = [Revenue]
    VAR PreviousYearRevenue = [Revenue PY]
    // BLANK bewusst beibehalten, wenn die Referenzperiode keinen sinnvollen Nenner hat.
    // Fachliches Verhalten durch KPI-Owner bestätigen lassen.
    RETURN
        DIVIDE (
            CurrentRevenue - PreviousYearRevenue,
            PreviousYearRevenue
        )
```

Keine Kommentare für selbstverständliche Schritte oder unbelegte Geschäftsregeln verwenden. Die Kommentare sind mit der Logik zu aktualisieren.

### Measure-Description direkt über DAX Query View pflegen

Microsoft unterstützt in der **DAX Query View** `///`-Zeilen **unmittelbar vor einem `MEASURE` im `DEFINE`-Block**. Über **Update model with changes** (oder die CodeLens-Aktion) wird daraus die gespeicherte **Description-Eigenschaft** des Measures. **Ein Query-Run allein speichert das nicht im Modell.**

```dax
DEFINE
    /// Beispiel: Umsatz auf Basis der fachlich bestätigten Netto-Betragsspalte.
    /// Geldbetrag im aktuellen Filterkontext.
    MEASURE '_Measures'[Revenue] =
        SUM ( FactSales[NetAmount] )

EVALUATE
    ROW ( "Revenue", [Revenue] )
```

Die Beschreibung ist nur dann für produktive Modelle geeignet, wenn die zugrunde liegende Definition und die Annahmen fachlich bestätigt sind. `///` im normalen **Measure-Formeleditor** ist **keine** verlässliche Methode, die Description-Eigenschaft zu schreiben. Alternativ die **Properties pane** verwenden.

### TMDL / PBIP

Direkt oberhalb der `measure`-Deklaration stehen `///`-Zeilen für die Description:

```tmdl
table _Measures
    /// Beispiel: Umsatzbetrag im aktuellen Filterkontext.
    measure Revenue = SUM ( FactSales[NetAmount] )
        formatString: #,##0.00
```

**Unterschied:** `///` vor der Measure-Deklaration beschreibt das Modellobjekt, `//` im Ausdruck kommentiert die DAX-Logik. **FormatString, DisplayFolder und Synonyme** sind zusätzliche Metadaten. Synonyme werden nicht automatisch aus DAX-Kommentaren erzeugt; bei PBIP/TMDL auch Culture-/Linguistic-Metadaten auf Änderungen prüfen.

## 4. Review-Checkliste

- [ ] Fachlich verständlicher, konsistenter Name ohne unnötiges technisches Präfix
- [ ] Durchschnitts-, Anzahl- und Quotenbezeichnungen benennen ihre fachliche Bezugsgröße bzw. Granularität
- [ ] Berechnungsmethode und Aggregierbarkeit (additiv / semi-additiv / nicht additiv) sind bei Bedarf dokumentiert
- [ ] Absichtlich entfernte Filter sind im Namen oder in der Description erkennbar; Summen, Slicer und Berechtigungen geprüft
- [ ] Business-Definition bestätigt, KPI-Steckbrief verlinkt
- [ ] Description beschreibt die Bedeutung fachlich korrekt, inklusive relevanter Grenzen
- [ ] `//`-Kommentare erklären besondere technische Entscheidungen
- [ ] FormatString, Datentyp, `%` und Einheiten sind passend
- [ ] DisplayFolder und Sichtbarkeit sinnvoll; Formatierungs-Measures getrennt
- [ ] Wo für natürlichsprachliche Abfragen sinnvoll: Synonyme fachlich bestätigt, Sprache/Culture berücksichtigt, eindeutig und bei Änderungen erneut geprüft
- [ ] Summen, Details, Zeiträume, Filterkontexte, BLANK/0 getestet
- [ ] Änderungen an DAX, Description und Synonymen gemeinsam reviewed
- [ ] Bei Copilot-/Data-Agent-Nutzung repräsentative natürlichsprachliche Fragen geprüft

## 5. Copilot-Prompt

```text
Prüfe dieses Measure anhand des DAX Measure Authoring Guide.
Schlage einen verständlichen Namen vor, der Durchschnitts- und Zählbasis sowie
abweichenden Filterkontext bei Bedarf erkennen lässt; nenne die
Berechnungsmethode und fachliche Aggregierbarkeit; liefere formatierten
DAX-Code mit hilfreichen
Kommentaren und eine knappe Description als ///-Text für DAX Query View vor.
Nutze ausschließlich die bestätigte KPI-Definition und vorhandene Modellfelder.
Erfinde keine Filterregeln, Geschäftsdefinitionen, Zeitbezüge oder Synonyme.
Ändere das Modell nicht selbstständig. Erkläre Verhaltensänderungen und
liefere passende fachliche Validierungstests.
```

## Herkunft und Abgrenzung

**Aus der Guideline:** `NAM-001` bis `NAM-006`, `DAX-001` bis `DAX-008`, `DOC-002` bis `DOC-004`, `DOC-010` bis `DOC-011`, Kapitel 12 und 15.3–15.4. **Ergänzend vorgeschlagen:** konkrete Namenssuffixe und Aggregationsbeispiele, Kommentierstil und DAX-Query-View-Workflow für Beschreibungen. Quelle: v0.1 (Entwurf), 16.11.2026.

**Externe Referenzen:** [Microsoft: DAX Query View](https://learn.microsoft.com/en-us/power-bi/transform-model/dax-query-view), [Microsoft: CALCULATE](https://learn.microsoft.com/en-us/dax/calculate-function-dax), [Microsoft: REMOVEFILTERS](https://learn.microsoft.com/en-us/dax/removefilters-function-dax), [Microsoft: TMDL](https://learn.microsoft.com/en-us/analysis-services/tmdl/tmdl-overview), [SQLBI: Naming](https://docs.sqlbi.com/dax-style/dax-naming-conventions), [SQLBI: Formatting](https://docs.sqlbi.com/dax-style/dax-format), [Microsoft: Data Agent](https://learn.microsoft.com/en-us/fabric/data-science/semantic-model-best-practices).

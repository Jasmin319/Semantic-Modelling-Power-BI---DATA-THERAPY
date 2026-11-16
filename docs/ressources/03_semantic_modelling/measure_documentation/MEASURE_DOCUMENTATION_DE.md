# Measure-Dokumentation

**Arbeitsvorlage auf Grundlage von Kapitel 15.3 der Guideline (v0.1, Entwurf).**

> Die fachliche KPI-Definition wird, sofern vorhanden, im [KPI-Steckbrief](../kpi_definition/README.md) verantwortet. Hier wird ihre konkrete Implementierung dokumentiert. Nicht bestätigte Aussagen als `[Offen]` markieren.

Measures sollten fachlich orientiert benannt werden. Durchschnittswerte, Quoten, Zeitvergleiche und wesentliche besondere Filterkontexte sollten bei Bedarf aus dem Namen hervorgehen. Die tatsächliche Berechnungsmethode wird separat dokumentiert, statt technische DAX-Details in den Namen aufzunehmen.

## 1. Bedeutung und Implementierung

| Feld aus Kapitel 15.3 | Eintrag |
| --- | --- |
| Measure-Name | `[Fachlich orientierter Power-BI-Name; Durchschnitt, Quote, Zeitvergleich oder besonderen Filterkontext bei Bedarf kenntlich machen]` |
| Fachliche Definition | `[Kurzdefinition oder Link zum bestätigten KPI-Steckbrief]` |
| Fachlich bestätigte Synonyme je Sprache/Culture | `[Nur gleichbedeutende Begriffe; Sprache/Culture und fachliche Bestätigung]` |
| Mehrdeutigkeiten / bewusst ausgeschlossene Begriffe | `[Konflikte, abweichende Definitionen oder nicht zulässige Zuordnungen]` |
| Synonymprüfung | `[Bestätigender Owner / Datum der letzten Prüfung]` |
| Unterstützte Entscheidung | `[Business Question / DEC-ID oder Nicht zutreffend]` |
| DAX-Ausdruck | `Siehe Codeblock unten` |
| Technische Kurzbeschreibung | `[Berechnungsweise in verständlichen Worten]` |
| Verwendete Measures | `[Namen / Links]` |
| Verwendete Tabellen / Spalten | `[Namen / Links]` |
| Filterverhalten | `[Welche Filter wirken normal auf das Ergebnis?]` |
| Filterkontextänderungen | `[ALL, REMOVEFILTERS, USERELATIONSHIP usw., soweit tatsächlich verwendet; Zweck]` |
| Einheit | `[EUR / % / Stück / andere]` |
| Format | `[Formatstring / dynamisches Format / Rundung]` |
| Berechnungs- / Aggregationsmethode | `[SUM / AVERAGE / DISTINCTCOUNT / gewichteter Durchschnitt / Quote / andere; tatsächliche Methode beschreiben]` |
| Aggregationsverhalten | `[Additiv / semi-additiv / nicht additiv; Verhalten bei Summen und Detailwerten erläutern]` |
| Filterkontextverhalten | `[Standard, ignoriert Regionsfilter, ignoriert Datumsfilter oder anderes wirksames Verhalten]` |
| Ausnahmen, Grenzen, Fallstricke | `[Nullwerte, Division durch null, Sondersituationen, Interpretationsgrenzen]` |
| Fachlicher Owner | `[Rolle / bestätigende Person]` |
| Validierung | `[Abgleichmethode / Referenzwerte / Link auf Testnachweis]` |

Das Aggregationsverhalten beschreibt, wie Ergebnisse über Gruppen hinweg zusammengefasst werden, nicht welche DAX-Funktion verwendet wird. Ein additives Measure muss nicht `SUM()` verwenden; eine mit `DIVIDE()` implementierte Quote ist typischerweise nicht additiv. Dokumentieren Sie daher die tatsächliche Methode und das Aggregationsverhalten getrennt.

### DAX

```dax
-- DAX aus dem tatsächlichen Modell hier einfügen.
-- Keine Geschäftsregeln ergänzen, die nicht fachlich bestätigt sind.
```

## 2. Zusatzangaben (optional)

| Feld | Eintrag |
| --- | --- |
| Referenz / ID | `[Measure-ID / KPI-ID]` |
| Modell / Display Folder | `[Modell und Bereich]` |
| Implementierungsstand | `[Geplant / implementiert / geprüft]` |
| Technischer Owner | `[Rolle / Kontakt]` |
| Änderungen gegenüber KPI-Definition | `[Keine / offene Abweichung mit Begründung]` |

## 3. Prüfungen (optional)

| Testfall | Erwartung / Quelle | Tatsächliches Ergebnis | Status |
| --- | --- | --- | --- |
| Detailwert | `[Referenz]` | `[Ergebnis]` | `Open` |
| Gesamtergebnis | `[Referenz]` | `[Ergebnis]` | `Open` |
| Filter- / Zeitkontext | `[Referenz]` | `[Ergebnis]` | `Open` |
| Leerwerte / Sonderfälle | `[Referenz]` | `[Ergebnis]` | `Open` |

## 4. Kurze Description im Modell

`Berechnet [Kennzahl] als [fachliche Berechnung / Bezugsgröße] für [Zeitraum oder Geltungsbereich]. Das Ergebnis wird in [Einheit] angegeben. [Relevante, belegte Einschränkung oder Filterregel.]`

**Bestätigte Description:** `[Kurzer, neutraler und fachlich geprüfter Satz.]`

## 5. Änderungshistorie

| Version | Datum | Änderung | Fachlich / technisch geprüft durch |
| --- | --- | --- | --- |
| `0.1` | `[Datum]` | `[Erstfassung]` | `[Offen]` |

# Tabellendokumentation

**Arbeitsvorlage auf Grundlage von Kapitel 15.2 der Power-BI-Semantic-Modeling-Guideline (v0.1, Entwurf).**

> Ein Dokument je Tabelle oder gleichwertige Pflege im Datenkatalog. `[Offen]` verwenden, wenn eine Angabe noch nicht bestätigt ist. Die optionalen Umsetzungs- und Prüffelder sind Ergänzungen zur Guideline.

## 1. Tabellenprofil

| Feld aus Kapitel 15.2 | Eintrag |
| --- | --- |
| Tabellenname | `[Name im semantischen Modell]` |
| Rolle | `[Fakt / Dimension / Bridge / Aggregation / Parameter / andere]` |
| Fachlicher Zweck | `[Was enthält die Tabelle und wofür wird sie verwendet?]` |
| Quelle | `[Quellsystem, Objekt, Datenprodukt und relevante Transformationen]` |
| Granularität | **Eine Zeile entspricht …** `[eindeutige fachliche Aussage]` |
| Primär-/eindeutiger Schlüssel | `[Schlüsselfeld(er), Eindeutigkeitsregel]` |
| Relevante Fremdschlüssel | `[Felder und referenzierte Tabellen]` |
| Beziehungen / besondere Filterlogik | `[Zieltabellen, Kardinalität, Filterrichtung, inaktive Beziehungen, Ausnahmen]` |
| Historisierung | `[z. B. aktuelle Sicht / historisierte Versionen; Gültigkeitsregeln]` |
| Unknown-Member-Regeln | `[Umgang mit fehlenden, ungültigen oder nicht zugeordneten Schlüsseln]` |
| Wichtige Attribute | `[Fachlich relevante Spalten und ihre Bedeutung]` |
| Bekannte Einschränkungen | `[Lücken, Vergleichbarkeitsgrenzen, unvollständige Zeiträume usw.]` |
| Fachlicher Owner | `[Rolle / bestätigende Person]` |
| Technische Betreuung | `[Rolle / Kontakt]` |
| Aktualisierung | `[Rhythmus, Datenstand, Verzögerungen]` |

## 2. Zusätzliche Umsetzungsangaben (optional)

| Feld | Eintrag |
| --- | --- |
| Modell / Umgebung / Link | `[Referenz auf PBIP/TMDL oder Modell]` |
| Abhängige Kennzahlen / Reports | `[Links/IDs, keine doppelte KPI-Definition]` |
| Datenqualitätsprüfungen | `[Schlüssel-Eindeutigkeit, Nulls, Referenzintegrität, Zeilenanzahl usw.]` |
| Relevante Sicherheitsregeln | `[RLS/OLS bzw. Verweis auf Sicherheitsdokumentation]` |
| Geplanter / geprüfter Zustand | `[Entwurf / implementiert / geprüft]` |

## 3. Reviewnachweise (optional)

| Prüfung | Erwartung oder Referenz | Nachweis / Ergebnis | Status |
| --- | --- | --- | --- |
| Granularität verständlich und konsistent | `[Erwartung]` | `[Nachweis]` | `Open` |
| Schlüssel auf der 1-Seite eindeutig und nicht leer | `[Erwartung]` | `[Nachweis]` | `Open` |
| Fremdschlüssel und Unknown Members behandelt | `[Erwartung]` | `[Nachweis]` | `Open` |
| Beziehung und Filterverhalten geprüft | `[Erwartung]` | `[Nachweis]` | `Open` |
| Historisierung und Aktualität geprüft | `[Erwartung]` | `[Nachweis]` | `Open` |

## 4. Kurzbeschreibung für die Description-Eigenschaft

`Enthält [fachliche Inhalte]. Eine Zeile entspricht [Granularität, soweit bekannt und relevant]. Die Tabelle dient als [Modellrolle / Analysezweck] für [Kontext]. [Wesentliche belegte Einschränkung, falls nötig.]`

**Bestätigte Beschreibung:** `[Hier einen knappen neutralen Text einsetzen.]`

Die Description ist **nicht** die vollständige Tabellendokumentation. Siehe [Metadata Description Guide](../metadata_description_guide/README.md).

## 5. Änderung und Klärung

| Version | Datum | Änderung / offener Punkt | Bestätigt durch |
| --- | --- | --- | --- |
| `0.1` | `[Datum]` | `[Erstentwurf]` | `[Offen]` |

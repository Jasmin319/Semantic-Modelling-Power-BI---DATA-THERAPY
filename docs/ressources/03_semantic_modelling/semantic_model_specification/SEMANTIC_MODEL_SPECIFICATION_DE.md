# Semantic-Model-Spezifikation

**Von fachlichen Anforderungen zum verlässlichen semantischen Modell**

> Arbeitsvorlage auf Basis der *Guideline Semantische Modellierung in Power BI*, Version 0.1 (Entwurf), 16.11.2026. Diese Spezifikation ersetzt keine fachliche Freigabe oder technische Prüfung.

**Ausfüllhinweis:** `[Platzhalter]` ersetzen; unbekannte Angaben als **Offen**, nicht relevante als **Nicht zutreffend** kennzeichnen. Zwischen **geplant**, **implementiert** und **validiert** unterscheiden.

## 1. Modellübersicht

| Feld | Angabe |
| --- | --- |
| Modell-ID / Modellname | `[ID / Name]` |
| Fachbereich und Zweck | `[Welcher fachliche Bedarf wird unterstützt?]` |
| Zielgruppe / Consumer | `[Rollen, Anwendungen, Reports]` |
| Business Owner | `[Verantwortliche Rolle]` |
| Technischer Owner / Support | `[Rolle / Kontakt]` |
| Version / Status / Datum | `[z. B. 0.1 / Entwurf / JJJJ-MM-TT]` |
| Power-BI-Workspace / Umgebung | `[Link / Bezeichnung]` |
| Implementiertes Modell / Repository | `[Link, sobald vorhanden]` |

## 2. Geschäftlicher Kontext und Geltungsbereich

**Unterstützte Entscheidungen / Business Questions:**

| Referenz (optional) | Entscheidung / Fragestellung | Erwartete Verwendung |
| --- | --- | --- |
| `[DEC-001 / BQ-001]` | `[Entscheidung / Frage]` | `[Nutzung]` |

**Im Scope:** `[Fachliche Bereiche, Prozesse, Zeiträume]`  
**Nicht im Scope:** `[Explizite Grenzen]`  
**Wichtige Annahmen:** `[Noch zu bestätigende Annahmen]`

## 3. Datenquellen und Abhängigkeiten

| Datenquelle / Datenprodukt | Inhalt / Verantwortlichkeit | Aktualität / Qualität | Transformation / Abhängigkeit |
| --- | --- | --- | --- |
| `[Quelle]` | `[Inhalt, Owner]` | `[SLA oder bekannte Grenze]` | `[Referenz auf Pipeline / Vertrag]` |

**Umgang mit fehlenden/ungültigen Daten:** `[Regeln bzw. offener Klärungsbedarf]`

## 4. Geplante Modellstruktur

### Tabellen und Granularität

| Tabelle | Rolle | Fachlicher Zweck | Granularität („Eine Zeile entspricht ...“) | Schlüssel / Historisierung |
| --- | --- | --- | --- | --- |
| `[Fact...]` | `[Fakt]` | `[Zweck]` | `[Eine Zeile entspricht ...]` | `[Schlüssel / Regel]` |
| `[Dim...]` | `[Dimension]` | `[Zweck]` | `[Eine Zeile entspricht ...]` | `[Schlüssel / SCD / Unknown]` |

### Beziehungen und Modellentscheidungen

| Von → Nach | Kardinalität / Filterrichtung | Aktiv / inaktiv | Begründung / Risiko |
| --- | --- | --- | --- |
| `[Tabelle.Schlüssel → Tabelle.Schlüssel]` | `[1:n / Richtung]` | `[Status]` | `[Fachliche Begründung]` |

**Modellskizze / Diagramm:** `[Link auf Grafik / PBIP / Diagramm]`  
**Bewusst gewählte Abweichungen vom Sternschema:** `[Begründung oder keine]`

## 5. KPIs und Measures

| KPI-ID | Fachliche KPI-Definition (Link) | Measure-Name | Besondere Modelllogik / Status |
| --- | --- | --- | --- |
| `[KPI-001]` | `[Link zum KPI-Steckbrief]` | `[Measure]` | `[Offen / Implementiert / Geprüft]` |

**Hinweis:** Fachliche Definition, Berechnungsregel, Owner und Validierung bleiben im KPI-Steckbrief. Hier nur verlinken und modellspezifische Besonderheiten festhalten.

## 6. Zeitbezug, Aggregation und Filter

| Thema | Vereinbarung |
| --- | --- |
| Datumstabelle(n) und Kalenderlogik | `[Kalender, Geschäftsjahr, Einschränkungen]` |
| Datumsrollen | `[z. B. Buchungsdatum, Rechnungsdatum]` |
| Unterschiedliche Granularitäten | `[z. B. Plan auf Monat / Ist auf Belegposition]` |
| Kritisches Filterverhalten | `[z. B. inaktive Beziehungen, M:N, Sonderfilter]` |

## 7. Sicherheit und Governance

| Thema | Anforderung und Nachweis |
| --- | --- |
| Sensible Daten / Klassifikation | `[Was ist schützenswert?]` |
| RLS / OLS / Berechtigungen | `[Rollen, Zielgruppen und Regeln]` |
| Sicherheitsgruppen / Zugriffspflege | `[Verantwortliche, Dokumentation, Review]` |
| Fachlicher Änderungsprozess | `[Wer bestätigt Definitionsänderungen?]` |

## 8. Performance und Betrieb

| Thema | Ziel / Annahme / Messung |
| --- | --- |
| Storage Mode und Begründung | `[Import / DirectQuery / Composite / Direct Lake; warum?]` |
| Datenvolumen / Wachstum | `[Annahme oder gemessener Wert]` |
| Refresh / Aktualisierungsstrategie | `[Häufigkeit, Zeitfenster, Fehlerbehandlung]` |
| Erwartete Nutzung / Performanceziel | `[Konkretes repräsentatives Szenario]` |
| Betrieb / Monitoring / Support | `[Owner, Vorgehen und Kontakt]` |

## 9. Validierung und Abnahme

| Prüffall / Akzeptanzkriterium | Erwartung / Referenz | Ergebnis / Nachweis | Verantwortlich / Status |
| --- | --- | --- | --- |
| `[KPI-Abgleich gegen Referenz]` | `[Erwartung]` | `[Link / Ergebnis]` | `[Owner / Offen]` |
| `[Granularität & Beziehungen]` | `[Erwartung]` | `[Link / Ergebnis]` | `[Reviewer / Offen]` |
| `[RLS/OLS im Zielsystem]` | `[Erwartung]` | `[Link / Ergebnis]` | `[Reviewer / Offen]` |
| `[Refresh und Performance]` | `[Erwartung]` | `[Link / Ergebnis]` | `[Reviewer / Offen]` |
| `[Abhängige Reports]` | `[Erwartung]` | `[Link / Ergebnis]` | `[Reviewer / Offen]` |

**Fachliche Bestätigung:** `[Wer, wann, was konkret bestätigt?]`  
**Technisches Review:** `[Wer, wann, Prüfnachweis]`  
**Produktionsfreigabe:** `[Separater Freigabenachweis, falls vorhanden]`

## 10. Entscheidungen, Risiken und Änderungen

| ID | Offene Frage / Risiko / Ausnahme | Maßnahme / Entscheidung | Owner / Zieltermin / Status |
| --- | --- | --- | --- |
| `[R-001]` | `[Beschreibung]` | `[Klärung]` | `[Verantwortlich / Status]` |

### Änderungshistorie

| Version | Datum | Änderung | Geprüft / bestätigt durch |
| --- | --- | --- | --- |
| `0.1` | `[JJJJ-MM-TT]` | `[Erstentwurf]` | `[Offen]` |

---

**Abgrenzung:** Dies ist die **Modellspezifikation**, nicht der vollständige Metadatenkatalog. Für KPI-Definitionen den KPI-Steckbrief verwenden, für Qualitätsstandards die Guideline und für Freigaben die geltenden Review-Prozesse.

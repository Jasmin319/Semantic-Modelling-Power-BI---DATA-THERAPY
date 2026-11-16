# Leitfaden für Description-Texte

**Kurze, fachlich korrekte Metadaten für Power-BI-Semantic-Modelle.**

Grundlage: Kapitel **15.3/15.4** sowie **DOC-003**, **DOC-004** und **DOC-010** der Guideline *Semantische Modellierung in Power BI*, v0.1 (Entwurf), 16.11.2026.

## 1. Grundsatz

Die **Description-Eigenschaft** dient der schnellen Orientierung am Modellobjekt. Sie ist **kein Ersatz** für KPI-Steckbrief, Tabellen- oder Measure-Dokumentation.

Schreibe kurze, vollständige, neutrale Sätze. Ergänze den Objektnamen um Informationen, die seine Bedeutung klären. Wiederhole keine DAX-Syntax; erfinde keine Quellen, Geschäftsregeln, fachlichen Bewertungen oder Einschränkungen.

## 2. Satzgerüste gemäß Kapitel 15.4

**Tabelle:**

> Enthält [fachliche Inhalte]. Eine Zeile entspricht [Granularität, sofern bekannt und relevant]. Die Tabelle dient als [Modellrolle / Analysezweck] für [relevanten Kontext]. [Wesentliche, belegte Einschränkung.]

**Measure:**

> Berechnet [Kennzahl] als [fachliche Berechnung / Bezugsgröße] für [relevanten Zeitraum oder Umfang]. Das Ergebnis wird in [Einheit] angegeben. [Wichtige, belegte Einschränkung oder Filterregel.]

Nicht jede Klammer muss ausgefüllt werden. Unbekannte oder nicht benötigte Details gehören nicht als Behauptung in die Beschreibung.

## 3. Illustrative Beispiele (keine bestätigten Unternehmensdefinitionen)

| Modellobjekt | Wenig hilfreich | Besser, **wenn fachlich bestätigt** |
| --- | --- | --- |
| `FactSales` | „Sales-Daten.“ | „Enthält Verkaufsbelegpositionen. Eine Zeile entspricht einer Belegposition. Die Tabelle liefert Transaktionswerte für Umsatzanalysen.“ |
| `DimCustomer` | „Kundentabelle.“ | „Enthält Kundenattribute für die Gruppierung und Filterung von Verkaufsvorgängen.“ |
| `[Revenue]` | „SUM über Revenue.“ | „Berechnet den fakturierten Nettoumsatz für den ausgewählten Zeitraum in EUR.“ |
| `[Margin %]` | „Profitabilität, höher ist besser.“ | „Berechnet die Marge als Verhältnis von Deckungsbeitrag zu Nettoumsatz und gibt das Ergebnis in Prozent an.“ |
| `[Revenue YoY %]` | „Wachstum zum Vorjahr.“ | „Berechnet die relative Veränderung des Umsatzes gegenüber dem entsprechenden Vorjahreszeitraum in Prozent.“ |

**Achtung:** Die Beispiele sind fiktiv. Ob z. B. Nettoumsatz fakturiert, welche Stornos berücksichtigt oder welcher Nenner verwendet wird, muss pro Organisation fachlich geklärt werden.

## 4. Besondere Sorgfalt bei Measures

- **Quoten:** Nenner und fachliche Bezugsgröße nennen, soweit relevant.
- **Vergleiche:** Vergleichsbasis angeben und absolute Differenz von relativer Veränderung unterscheiden.
- **Zeiträume:** Zeitbezug nennen, wenn er den Wert wesentlich beeinflusst.
- **Feste Filter:** Beschreiben, wenn sie die Interpretation verändern und bestätigt sind.
- **Einschränkungen:** Nur bekannte, belegte Einschränkungen aufnehmen.

## 5. Kurzer Review

- [ ] Die Beschreibung erklärt Bedeutung statt lediglich den Namen zu wiederholen.
- [ ] Inhalt, Granularität und Rolle sind bei Tabellen angemessen berücksichtigt.
- [ ] Berechnungsbasis und Einheit sind bei Measures verständlich.
- [ ] Quoten, Vergleiche und feste Filter sind bei Bedarf erklärt.
- [ ] Der Text ist neutral, knapp und in vollständigen Sätzen formuliert.
- [ ] Jede fachliche Behauptung ist bestätigt oder als offen gekennzeichnet.
- [ ] Detaildokumentation ist separat verlinkt, wo sie benötigt wird.

## 6. Linguistische Metadaten und Synonympflege

Synonyme ordnen einem Modellobjekt bestätigte, fachlich gleichbedeutende Begriffe zu. Sie ergänzen den kanonischen Modellnamen und die Description, ersetzen aber weder die Definition noch deren fachliche Bestätigung.

- Synonyme nur nach Bestätigung durch den fachlichen Owner eintragen.
- Sprache/Culture dokumentieren, wenn die Begriffe sprachabhängig sind.
- Mehrdeutige oder widersprüchliche Begriffe klären oder ausschließen.
- Bei Änderungen der Definition oder Benennung erneut prüfen; die Pflege der Description allein genügt nicht.
- Für Modelle mit natürlichsprachlichen Abfragen repräsentative Fragen mit alternativen Begriffen im Zielsystem testen und die erwartete Measure-Zuordnung dokumentieren.

Für Fabric Data Agents nennt Microsoft Synonyme als Modellmetadaten, die in die DAX-Abfragegenerierung einfließen ([Semantic model best practices for data agent](https://learn.microsoft.com/en-us/fabric/data-science/semantic-model-best-practices)). Die Power-BI-Copilot-Dokumentation beschreibt „Prep data for AI“ und Beschreibungen, belegt aber nicht, dass die `Synonyms`-Eigenschaft oder das Linguistic Schema von jeder Copilot-Funktion genutzt wird ([FAQ: Preparing data for AI](https://learn.microsoft.com/en-us/power-bi/create-reports/copilot-prepare-data-ai-faq)). Das konkrete Verhalten muss daher im Zielprodukt geprüft werden.

**Beispiel**

**KANONISCHES MEASURE:** `Revenue`

**FACHLICH BESTÄTIGTE SYNONYME:** `Sales`, `Total Revenue`, `Umsatz`

**BEISPIELFRAGEN:**

- “Show me revenue by month.”
- “Show me sales by month.”
- „Zeige mir den Umsatz pro Monat.“

Alle drei Fragen sollen dasselbe Measure verwenden, sofern die Begriffe in der Organisation dieselbe Umsatzdefinition bezeichnen. Die tatsächliche Zuordnung ist zu testen; Synonyme garantieren keine korrekte Antwort.

Bei PBIP-Projekten mit TMDL kann das Linguistic Schema in einer Culture-Datei unter `definition/cultures` versioniert werden. TMDL verwendet eine Datei pro Culture; die genaue Projektstruktur hängt vom Format ab ([TMDL overview](https://learn.microsoft.com/en-us/analysis-services/tmdl/tmdl-overview?view=sql-analysis-services-2025)).

## 7. GitHub-Copilot-Prompt

```text
Erstelle einen kurzen Description-Text für ein Power-BI-Modellobjekt.
Nutze ausschließlich die nachfolgend bestätigten Fakten.
Wiederhole keinen DAX-Code und ergänze keine angenommenen Geschäftsregeln.
Für Tabellen: Inhalt, Granularität und Rolle nennen, soweit belegt.
Für Measures: fachliche Berechnungsbasis, Einheit und relevante
Einschränkungen nennen, soweit belegt.
Formuliere einen neutralen deutschen Text aus 1–3 Sätzen.
Falls entscheidende Informationen fehlen, liste diese unter
„Offene fachliche Fragen“ auf, statt sie zu erfinden.

Objektname: [Name]
Objekttyp: [Tabelle/Measure]
Bestätigte Fakten: [Hier einfügen]
```

Copilot-Texte müssen vor der Übernahme fachlich geprüft werden.

## 8. Abgrenzung

- [Tabellendokumentation](../table_documentation/README.md): Quellen, Schlüssel, Granularität, Beziehungen, Historisierung.
- [Measure-Dokumentation](../measure_documentation/README.md): DAX, Abhängigkeiten, Filterverhalten und Tests.
- [KPI-Steckbrief](../kpi_definition/README.md): verbindlich abgestimmte fachliche Bedeutung.

# Leitfaden für Description-Texte

**Kurze, fachlich korrekte Metadaten für Power-BI-Semantic-Modelle.**

Grundlage: Kapitel **15.4** sowie **DOC-003** und **DOC-004** der Guideline *Semantische Modellierung in Power BI*, v0.1 (Entwurf), 07.11.2026.

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

## 6. GitHub-Copilot-Prompt

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

## 7. Abgrenzung

- [Tabellendokumentation](../table_documentation/README.md): Quellen, Schlüssel, Granularität, Beziehungen, Historisierung.
- [Measure-Dokumentation](../measure_documentation/README.md): DAX, Abhängigkeiten, Filterverhalten und Tests.
- [KPI-Steckbrief](../kpi_definition/README.md): verbindlich abgestimmte fachliche Bedeutung.

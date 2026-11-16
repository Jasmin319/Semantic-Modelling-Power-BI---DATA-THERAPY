# KPI-Steckbrief

**Bedeutung vor Berechnung. Verantwortung vor Veröffentlichung.**

> **Hinweis:** Diese Vorlage basiert auf Kapitel 15.1 „Bedeutungsblatt für eine zentrale Kennzahl“ der Guideline *Semantische Modellierung in Power BI*, Version 0.1 (Entwurf), 07.11.2026. Leere Felder sind bewusst auszufüllen oder als „nicht zutreffend“ zu kennzeichnen. Es handelt sich nicht um eine bereits freigegebene KPI-Definition.

## 1. Fachliche KPI-Definition

| Feld | Eintrag |
| --- | --- |
| **Name der Kennzahl** | `[Name]` |
| **Synonyme / alternative Bezeichnungen** | `[Bezeichnungen, unter denen die Kennzahl verwendet oder gesucht wird]` |
| **Geschäftliche Definition** | `[Was bedeutet die Kennzahl im abgestimmten fachlichen Kontext?]` |
| **Geltungsbereich** | `[Organisationseinheiten, Geschäftsprozesse, Produkte, Zeiträume etc.]` |
| **Berechnung** | `[Fachliche Berechnungsregel; Zähler / Nenner, Ein- und Ausschlüsse]` |
| **Einheit / Darstellung** | `[z. B. EUR, %, Stück; Rundung und Format]` |
| **Datenquelle(n)** | `[Verantwortete Datenquellen / Datenprodukte]` |
| **Aktualität** | `[Datenstand, Aktualisierungshäufigkeit und relevante Verzögerungen]` |
| **Ausnahmen und Grenzen** | `[Bekannte Einschränkungen, Vergleichbarkeitsgrenzen, Sonderfälle]` |
| **Entscheidungseinsatz** | `[Welche konkrete Entscheidung oder Business Question wird unterstützt?]` |
| **Fachlicher Owner** | `[Rolle / zuständige Person, die Bedeutung und Änderungen bestätigt]` |
| **Validierung** | `[Referenzwerte, Prüffälle, Vergleichsverfahren und Ergebnis]` |
| **Gültig ab** | `[JJJJ-MM-TT oder fachliche Gültigkeitsregel]` |

## 2. Ergänzende Angaben für die Umsetzung (optional)

_Diese Felder ergänzen Kapitel 15.1 als Verbindung zum Decision Mapping Canvas und zur technischen Modellspezifikation._

| Feld | Eintrag |
| --- | --- |
| **KPI-ID** | `[z. B. KPI-001]` |
| **Entscheidungsreferenz** | `[z. B. DEC-001; optional]` |
| **Verknüpfte Business Questions** | `[Frage(n) / Referenz(en)]` |
| **Aggregation und Zeitbezug** | `[Additiv, semi-additiv oder nicht additiv; maßgebliches Datumsfeld]` |
| **Filterverhalten / Kontext** | `[Welche Filter beeinflussen die Interpretation?]` |
| **Technische Implementierung** | `[Modellname, Measure-Name, Link zur technischen Dokumentation]` |
| **Technischer Ansprechpartner** | `[Rolle / Kontakt]` |
| **Definitionsstatus** | `[Entwurf / in Prüfung / fachlich bestätigt]` |
| **Bestätigung durch / am** | `[Name oder Rolle / Datum; nicht vorausfüllen]` |

## 3. Validierung und fachliche Abnahme

| Prüffall | Erwartetes Ergebnis / Referenz | Tatsächliches Ergebnis | Status |
| --- | --- | --- | --- |
| `[z. B. Gesamtwert Referenzperiode]` | `[Referenz]` | `[Ergebnis]` | `[Offen / Bestanden / Nicht bestanden]` |
| `[z. B. Filter nach Region]` | `[Referenz]` | `[Ergebnis]` | `[Offen / Bestanden / Nicht bestanden]` |
| `[z. B. Null-, Storno- oder Randfall]` | `[Referenz]` | `[Ergebnis]` | `[Offen / Bestanden / Nicht bestanden]` |

**Offene Fragen:** `[Nicht bestätigte Annahmen und Klärungsbedarf]`

## 4. Änderungshistorie

| Version | Gültig ab | Änderung / Grund | Fachlich bestätigt durch |
| --- | --- | --- | --- |
| `0.1` | `[Datum]` | `[Erstfassung]` | `[Offen / Rolle]` |

---

**Wichtig:** Die fachliche Definition darf nicht allein aus einer DAX-Formel abgeleitet werden. Die Bestätigung durch den fachlichen Owner ist getrennt von der technischen Umsetzung zu betrachten.


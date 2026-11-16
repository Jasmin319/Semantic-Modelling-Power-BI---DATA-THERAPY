# Semantic Model Review Checklist | DE

**Prüfung vor Freigabe: fachlich, technisch und nachvollziehbar.**

> Basierend auf Kapitel 12.1 (Review-Checkliste) der Guideline *Semantische Modellierung in Power BI*, Version 0.1 (Entwurf), 16.11.2026. Die Prüfpunkte sind aus der Guideline übernommen bzw. sinngemäß in prüfbare Zeilen überführt. Zusätzliche Erfassungsfelder sind als Arbeitshilfe ergänzt.

## 1. Review-Kontext

| Feld | Eintrag |
| --- | --- |
| **Modellname / Link** | `[Eintrag]` |
| **Modellversion / Commit / Release** | `[Eintrag]` |
| **Umgebung (z. B. Test/Produktion)** | `[Eintrag]` |
| **Änderung / Umfang (Neumodell oder bestehendes Modell)** | `[Eintrag]` |
| **Fachlicher Model Owner** | `[Eintrag]` |
| **Technische Ansprechperson** | `[Eintrag]` |
| **Business Reviewer / Datum** | `[Eintrag]` |
| **Technischer Reviewer / Datum** | `[Eintrag]` |
| **Review-Tiefe und Risikobegründung** | `[Eintrag]` |
| **Verknüpfte Model Specification / KPI-Steckbriefe** | `[Eintrag]` |

## 2. Prüfergebnisse

**Status:** `Pass` = erfüllt, `Fail` = nicht erfüllt, `Open` = ungeklärt, `N/A` = nicht anwendbar (begründen).

Pro Prüffall einen nachvollziehbaren Nachweis (Link, Testbericht, Screenshot, Query oder Ticket) referenzieren.

### Fachliche Bedeutung

| ID | Prüfkriterium | Status | Nachweis / Kommentar |
| --- | --- | --- | --- |
| R-01 | Zweck, Zielgruppe und unterstützte Entscheidungen sind beschrieben. | `Open` | `[Link / Hinweis]` |
| R-02 | Kernbegriffe und KPIs haben abgestimmte Definitionen, Geltungsbereiche und Owner. | `Open` | `[Link / Hinweis]` |
| R-03 | Ausnahmen, Einschränkungen und historische Regeln sind dokumentiert. | `Open` | `[Link / Hinweis]` |

### Modellstruktur

| ID | Prüfkriterium | Status | Nachweis / Kommentar |
| --- | --- | --- | --- |
| R-04 | Jede Faktentabelle hat eine definierte Granularität. | `Open` | `[Link / Hinweis]` |
| R-05 | Fakten, Dimensionen und Schlüssel sind fachlich nachvollziehbar. | `Open` | `[Link / Hinweis]` |
| R-06 | Schlüsselqualität und Kardinalitäten sind geprüft. | `Open` | `[Link / Hinweis]` |
| R-07 | Filterrichtungen und viele-zu-viele-Beziehungen sind bewusst entschieden. | `Open` | `[Link / Hinweis]` |
| R-08 | Plan-/Ist- und andere unterschiedliche Granularitäten sind getestet. | `Open` | `[Link / Hinweis]` |
| R-09 | Datumsdimension und Datumsrollen sind nachvollziehbar modelliert. | `Open` | `[Link / Hinweis]` |

### Measures und DAX

| ID | Prüfkriterium | Status | Nachweis / Kommentar |
| --- | --- | --- | --- |
| R-10 | Geschäftskritische Kennzahlen sind explizite Measures. | `Open` | `[Link / Hinweis]` |
| R-11 | Wiederverwendbare Basis-Measures werden genutzt. | `Open` | `[Link / Hinweis]` |
| R-12 | Grundgesamtheit und Nenner von Durchschnittswerten sind bestätigt; Berechnungsverfahren und Aggregierbarkeit sind getrennt geprüft. | `Open` | `[Link / Hinweis]` |
| R-13 | Wesentliche Änderungen des Filterumfangs, insbesondere entfernte Filter, sind dokumentiert und auf Detail- und Gesamtebene geprüft. | `Open` | `[Link / Hinweis]` |
| R-14 | Description, Formatstring, Einheit und bestätigte Synonyme stimmen mit fachlicher Definition und DAX überein. | `Open` | `[Link / Hinweis]` |
| R-15 | Geschäftskritische Summen sind auf Detail- und Gesamtebene mit der Quelle oder einem fachlich freigegebenen Bericht abgeglichen; nach Modelländerungen erneut prüfen. | `Open` | `[Link / Hinweis]` |
| R-37 | Measure-Namen, Vergleichssuffixe und Display Folders sind konsistent und verständlich; Durchschnitts- und Zählkennzahlen machen ihre Bezugsgröße bei Bedarf kenntlich. | `Open` | `[Link / Hinweis]` |
| R-38 | Relevante DAX-Ausdrücke sind verständlich und konsistent formatiert; nicht offensichtliche technische Entscheidungen sind kommentiert. | `Open` | `[Link / Hinweis]` |
| R-39 | Mit `///` in der DAX Query View gesetzte Descriptions wurden ins Modell übernommen; eine Query-Ausführung allein reicht nicht. | `Open` | `[Link / Hinweis]` |

### Datenaufbereitung und Betrieb

| ID | Prüfkriterium | Status | Nachweis / Kommentar |
| --- | --- | --- | --- |
| R-16 | Quellen, Aktualität, Schlüssel und Transformationen sind nachvollziehbar. | `Open` | `[Link / Hinweis]` |
| R-17 | Datentypen, Währungen und Zeitbezüge sind konsistent. | `Open` | `[Link / Hinweis]` |
| R-18 | Query Folding und Refresh-Verhalten sind geprüft, soweit relevant. | `Open` | `[Link / Hinweis]` |
| R-19 | Storage Mode ist begründet und repräsentative Performance ist gemessen. | `Open` | `[Link / Hinweis]` |

### Sicherheit und Dokumentation

| ID | Prüfkriterium | Status | Nachweis / Kommentar |
| --- | --- | --- | --- |
| R-20 | Zugriffe, RLS/OLS und sensible Daten sind im Zielsystem geprüft. | `Open` | `[Link / Hinweis]` |
| R-21 | Workspace-Rollen und allgemeine Zugriffe werden, soweit unterstützt, über zweckgebundene Sicherheitsgruppen verwaltet; Owner, Mitgliedschaften, Reviews, direkte Ausnahmen und effektive Rechte sind geprüft/dokumentiert. | `Open` | `[Link / Hinweis]` |
| R-22 | Sicherheitsgruppen folgen einer abgestimmten Namenskonvention mit Umgebung, Zugriffstyp, Zielobjekt und Rolle/Berechtigungsumfang. | `Open` | `[Link / Hinweis]` |
| R-23 | RLS-Rollen, zugewiesene Sicherheitsgruppen und Mitgliedschaften sind dokumentiert und mit repräsentativen Identitäten geprüft; direkte Zuweisungen sind begründete Ausnahmen. | `Open` | `[Link / Hinweis]` |
| R-24 | Model Owner, technische Betreuung und Support sind benannt. | `Open` | `[Link / Hinweis]` |
| R-25 | Mindestdokumentation ist vollständig; kurze Objektbeschreibungen und Katalogdetails sind getrennt. | `Open` | `[Link / Hinweis]` |
| R-26 | Beschreibungen ergänzen den Namen, sind neutral und enthalten keine unbelegten Fachannahmen. | `Open` | `[Link / Hinweis]` |
| R-27 | Änderungen an Modellmetadaten und Definitionen sind nachvollziehbar überprüft. | `Open` | `[Link / Hinweis]` |
| R-28 | Abhängige Berichte wurden auf Regressionen geprüft. | `Open` | `[Link / Hinweis]` |
| R-29 | Offene Ausnahmen sind dokumentiert und genehmigt. | `Open` | `[Link / Hinweis]` |
| R-34 | Für relevante Modellobjekte wurden gebräuchliche fachliche Alternativbegriffe geprüft und, soweit sinnvoll, als Synonyme gepflegt. | `Open` | `[Link / Hinweis]` |
| R-35 | Vorhandene Synonyme sind aktuell, eindeutig und mit den bestätigten Kennzahlendefinitionen vereinbar. | `Open` | `[Link / Hinweis]` |
| R-36 | Bei für Copilot oder Data Agents vorgesehenen Modellen wurden repräsentative natürlichsprachliche Fragen mit Alternativbegriffen getestet und die erwartete Zuordnung dokumentiert. | `Open` | `[Link / Hinweis]` |
### Textbasierte Entwicklung und Automatisierung

| ID | Prüfkriterium | Status | Nachweis / Kommentar |
| --- | --- | --- | --- |
| R-30 | Bei PBIP-/TMDL-Änderungen ist der Diff auf unbeabsichtigte Änderungen geprüft. | `Open` | `[Link / Hinweis]` |
| R-31 | Nach TMDL-Änderungen wurden Syntax, Eigenschaften, Abhängigkeiten und relevante Berichte geprüft. | `Open` | `[Link / Hinweis]` |
| R-32 | Automatisierte Metadatenprüfungen verwenden dokumentierte Kriterien und passende Ausnahmen. | `Open` | `[Link / Hinweis]` |
| R-33 | KI-generierte Beschreibungen sind mit Modellinformationen und fachlicher Definition abgeglichen; offene Annahmen wurden nicht als Fakten übernommen. | `Open` | `[Link / Hinweis]` |

## 3. Produktionsfreigabe (Kapitel 12.2)

Die folgenden sieben Punkte bilden den Freigabeabschnitt der Guideline ab; der Review ist nicht automatisch die Freigabe.

| ID | Freigabebedingung | Status | Evidenz / Freigabe |
| --- | --- | --- | --- |
| G-01 | Fachlicher Owner bestätigt kritische Definitionen und KPI-Ergebnisse inkl. Quell-/Referenzabgleich. | `Open` | `[Link / Name / Datum]` |
| G-02 | Modell, Beziehungen und Datenqualität sind geprüft. | `Open` | `[Link / Name / Datum]` |
| G-03 | Sicherheit und Berechtigungen sind im Zielsystem getestet. | `Open` | `[Link / Name / Datum]` |
| G-04 | Performance und Refresh sind für vereinbarte Szenarien bewertet. | `Open` | `[Link / Name / Datum]` |
| G-05 | Abhängige Reports sind auf Regressionen geprüft. | `Open` | `[Link / Name / Datum]` |
| G-06 | Dokumentation, Betrieb und Support sind geregelt. | `Open` | `[Link / Name / Datum]` |
| G-07 | Release-Freigabe und genehmigte Ausnahmen sind nachvollziehbar; Änderungen sind, falls vorgesehen, versioniert und reviewed. | `Open` | `[Link / Name / Datum]` |

## 4. Abweichungen und Maßnahmen (Kapitel 13)

**Hinweis:** Bei Abweichungen von vorgeschlagenen MUST-Regeln sind die in Kapitel 13 genannten Felder zu erfassen und eine verantwortliche Genehmigung einzuholen. Die vorgeschlagenen Klassifikationen sind erst nach formaler Freigabe verbindlich.

| Ausnahme-ID | Regel-ID | Modell / Umfang | Grund / Alternativen | Risiken / Maßnahmen | Genehmigung | Review-Termin |
| --- | --- | --- | --- | --- | --- | --- |
| `[EX-001]` | `[z. B. MOD-003]` | `[Bereich]` | `[Details]` | `[Details]` | `[Owner / Datum]` | `[Datum]` |

## 5. Ergebnis und Freigabeentscheidung

| Feld | Eintrag |
| --- | --- |
| **Offene kritische Punkte** | `[Anzahl / Verweise]` |
| **Review-Ergebnis** | `[Bestanden / Nicht bestanden / Offen]` |
| **Release-Entscheidung** | `[Freigegeben / Nicht freigegeben / Offen]` |
| **Verantwortliche Freigabe** | `[Rolle / Person / Datum / Ticket]` |
| **Nächster Review-Termin** | `[Datum / Anlass]` |

> Diese Vorlage dokumentiert einen Review, ersetzt aber weder fachliche Tests noch die tatsächliche Release-Freigabe im vereinbarten Organisationsprozess.

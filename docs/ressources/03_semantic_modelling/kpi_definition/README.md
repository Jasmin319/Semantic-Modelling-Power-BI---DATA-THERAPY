!\[Banner](https://github.com/Jasmin319/Semantic-Modelling-Power-BI---DATA-THERAPY/blob/main/Brand%20Assets/Banner.png)



!\[Microsoft MVP](https://img.shields.io/badge/Microsoft-MVP-5E5E5E)



\# KPI Definition Sheet



\*\*Define business meaning before implementing a measure.\*\*



The \*\*KPI Definition Sheet\*\* is a practical template for documenting a business-critical key performance indicator (KPI) or other important business measure. It is based on \*\*Section 15.1, “Bedeutungsblatt für eine zentrale Kennzahl,”\*\* of the \*Power BI Semantic Modeling Guideline\*, Version 0.1 (Draft), November 7, 2026.



Its guiding principle is:



> \*\*Agree on meaning before calculation. Make assumptions and limitations explicit.\*\*



\## Purpose



A KPI name or DAX formula alone does not establish a shared business definition. This template helps business owners and BI teams clarify \*\*what a measure means, where it applies, how it is calculated, who owns it, and how its correctness is validated\*\*.



It is suitable for KPI discussions, semantic model design, reviews, and change management.



\## Download the templates



\- \[Deutsch | KPI-Steckbrief (Markdown)](KPI\_TEMPLATE\_DE.md)

\- \[English | KPI Definition Sheet (Markdown)](KPI\_TEMPLATE\_EN.md)



Open a template and copy it for each KPI. Replace the placeholders with agreed, verifiable information.



\## What the template covers



| Area | What to clarify |

| --- | --- |

| Name and synonyms | How is the KPI named and searched for? |

| Business definition | What does it mean in the agreed business context? |

| Scope | Which organizational units, processes, and periods does it cover? |

| Calculation and unit | How is it calculated and presented? |

| Source and freshness | Where do the data come from, and how current are they? |

| Exceptions and limitations | When is the KPI not comparable or not meaningful? |

| Decision use | What decision or business question does it support? |

| Business owner | Who confirms the definition and approves changes? |

| Validation | Which reference values or tests establish correctness? |

| Effective date and change history | When does the definition apply, and what changed? |



These ten areas reflect the guideline's Section 15.1. The downloadable templates also provide \*\*optional implementation notes\*\*, a reference to a Decision ID, and a simple review status to connect business meaning with actual model development.



\## Suggested workflow



1\. \*\*Start with the business question or decision.\*\* Use the \[Decision Mapping Canvas](../../01\_decision\_design/decision\_mapping\_canvas/README.md) when the decision context is unclear.

2\. \*\*Agree on the definition.\*\* Involve the person accountable for the KPI and its intended consumers.

3\. \*\*Confirm scope and calculation.\*\* Explicitly document inclusions, exclusions, time reference, aggregation and any relevant filters.

4\. \*\*Validate against a trusted reference.\*\* Agree on test cases and expected outcomes before relying on the KPI.

5\. \*\*Translate into the semantic model.\*\* Use the \*Semantic Modeling Guideline\* for DAX, model design, descriptions, security and review.

6\. \*\*Maintain the definition.\*\* Record changes, effective dates and who accepted the update.



For dashboard-specific information requirements, see the \[Dashboard Canvas](../../02\_requirements\_stakeholder/dashboard\_canvas/README.md).



\## Relationship to the other resources



| Resource | Role |

| --- | --- |

| \[\*\*Decision Mapping Canvas\*\*](../../01\_decision\_design/decision\_mapping\_canvas/README.md) | Clarifies why a measure matters for a decision or action. |

| \[\*\*Dashboard Canvas\*\*](../../02\_requirements\_stakeholder/dashboard\_canvas/README.md) | Clarifies which KPIs and analysis capabilities a dashboard needs. |

| \*\*KPI Definition Sheet\*\* | Establishes the business meaning and agreed calculation of a specific KPI. |

| \*\*Semantic Modeling Guideline\*\* | Explains how the KPI is implemented, documented, tested and maintained in Power BI. |



One KPI can support several business questions and several reports. \*\*Do not create competing definitions for the same business concept.\*\* Reference an agreed KPI where possible.



\## Scope and status



This resource is a \*\*working template\*\*, not an automatically approved KPI standard or a substitute for business sign-off. Some fields may be marked \*not applicable\* when they do not affect interpretation. An unresolved definition must remain visibly open rather than being silently assumed.



The Semantic Modeling Guideline is currently \*\*Version 0.1 (Draft)\*\*. Its MUST/SHOULD/MAY classifications are proposed standards, not automatically binding organizational requirements.



\---



\## 🔗 Related content



🎥 YouTube: \[Power BI with AI Vibes](https://www.youtube.com/@BIVibes-JasminSimader)  

🏠 Website: \[Jasmin Simader](https://www.jasminsimader.com/)  

👩🏻‍💻 LinkedIn: \[Jasmin Simader](https://www.linkedin.com/in/jasmin-simader)  

📝 Blog / Substack: \[Substack](https://substack.com/@datatherapywithjasmin)




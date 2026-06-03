# EDAta – Business Analysis & Analytical Framework
### GovTech Hackathon 2026 · Challenge #5 · Alfa Diop-Wicki

---

## About this repository

This repository documents the **business analysis and analytical framework** I developed during the [GovTech Hackathon 2026](https://govtech.digisus-lab.ch/project/41) for Challenge #5 — *EDAta: Mehr Daten, bessere Diplomatie*.

My contribution focused on the **requirements and analysis phase**: problem framing, stakeholder identification, definition of the central analytical question, indicator selection, data source mapping, and structuring of the analytical framework that guided the technical implementation.

The analysis was published in the official project logs on the hackathon platform and is timestamped:  
> *Note: some indicators or data sources may have been adjusted during technical implementation. Such fine-tuning is a normal part of the development process and does not affect the analytical framework defined here.*  
🔗 [Project logs — govtech.digisus-lab.ch](https://govtech.digisus-lab.ch/project/41/log)

> 🔗 Live demo — AIDA AI Diplomatic Assistant *(decommissioned after the hackathon)*---

## Background & domain expertise

My analytical choices were informed by **5 years at SECO** (State Secretariat for Economic Affairs), where I was personally interested in topics related to Switzerland's economic cooperation priorities and bilateral trade policy. During this period, I also developed a curiosity for the activities of Swiss consulates and representations abroad, as well as in economic cooperation topics, which led me to seek a better understanding of the context in which diplomatic and consular personnel operate on a daily basis.

This awareness helped me identify **which indicators matter** for Swiss diplomatic and economic decision-making — not just which data is publicly available.

---

## IREB-structured Business Analysis

### 1. Problem Statement

Swiss diplomacy has access to a large number of public data sources (IMF, World Bank, SNB, etc.). However, these sources are fragmented, differently structured, and difficult to combine. This creates high manual effort and leaves important analytical connections unused.

**Affected users:** EDA staff, staff in other federal departments (e.g. SECO), and the Swiss representation network abroad — all of whom regularly produce country analyses, reports, and decision bases.

Before this type of tool, producing a comparable country briefing required approximately 48 hours of manual work. The prototype reduces this to seconds, supporting EDA staff and consular personnel in concentrating on their core diplomatic responsibilities.

---

### 2. Stakeholders

| Stakeholder | Type | Need |
|---|---|---|
| EDA diplomats | Primary user | Country briefings, bilateral overviews |
| EDA staff (non-diplomatic) | Primary user | Structured country profiles, trend monitoring |
| SECO / other federal departments | Secondary user | Economic intelligence, trade and investment signals |
| Other federal or mandated actors | Secondary user | Market attractiveness analysis based on public data |
| Swiss representations abroad | Primary user | Fast, data-driven country context |
| EDA Challenge owner (David Venzin) | Sponsor | Prototype demonstrating feasibility |

**Scalability note:** While the immediate client is EDA, the analytical framework is relevant to any Swiss federal actor working on country-level economic analysis. Following the prototype presentation, the challenge owner explicitly requested that the framework be extended to cover country groupings — starting from the individual country analysis defined here. This confirms the scalability by design of the analytical framework.

---

### 3. Central Analytical Question

> *How relevant, stable and economically attractive is a country for Switzerland, and which trends could become relevant for future economic or diplomatic decisions?*

This question was defined at the start of the hackathon to give the technical team a clear analytical direction and to ensure the prototype produces **diplomatically meaningful outputs**, not just data visualizations.

---

### 4. Analytical Framework — 4 Levels

The framework is structured around four data levels (1–4), each collecting objective indicators from a specific dimension. The fifth analytical dimension — detecting possible risk or opportunity signals — is not a data input but an analytical outcome, explicitly designed as user-driven: by combining the evidence from levels 1 to 4, the user forms an informed, holistic judgement over time. This intent was documented in the original project logs under [*"Possible objective: Provide a structured view of public selected economic indicators to support country monitoring and user-driven evaluation over time."*](https://govtech.digisus-lab.ch/project/41/log)

---

#### Level 1 — Economic Stability
*Is the country economically stable, or are there signs of increasing economic stress?*

| Indicator | Source | API Parameter | Purpose |
|---|---|---|---|
| GDP (USD) | IMF | NGDPD | Overall economic size |
| GDP Growth | IMF | NGDP_RPCH | Economic acceleration or slowdown |
| GDP per capita | IMF | NGDPDPC | Economic development level |
| Inflation Rate | IMF | PCPIPCH | Economic stress / purchasing power |
| Unemployment Rate | IMF | LUR | Social and economic pressure |
| Government Debt (% GDP) | IMF | GGXWDG_NGDP | Fiscal vulnerability |
| Income Category | World Bank | NY.GNP.PCAP.CD | Economic maturity |
| Innovation Index Rank | WIPO | GII Rank | Innovation and competitiveness |

---

#### Level 2 — Services Trade
*How relevant is the country as a services trade partner for Switzerland?*

| Indicator | Source | API Parameter | Purpose |
|---|---|---|---|
| Services Trade Receipts | SNB | bopserva (credits) | Economic activity |
| Services Trade Expenditures | SNB | bopserva (debits) | Economic integration |
| Total Services Trade | SNB | bopserva total | Overall services trade volume |
| Share of Swiss Services Trade | SNB | country share of total | Strategic relevance for Switzerland |
| Top 7 Service Sectors | SNB | sector/service dimension | Sector concentration analysis |

---

#### Level 3 — Direct Investments
*How significant is Switzerland's direct investment presence in the country?*

| Indicator | Source | API Parameter | Purpose |
|---|---|---|---|
| Direct Investments Abroad | SNB | fdiausbla | Swiss investment exposure |
| Share of Swiss Direct Investments | SNB | country share of total FDI | Strategic economic importance |

---

#### Level 4 — Goods Trade
*How relevant is the country as a goods trade partner for Switzerland?*

| Indicator | Source | API Parameter | Purpose |
|---|---|---|---|
| Exports (Mio CHF) | BAZG / SwissImpex | exports by country | Importance as export market |
| Imports (Mio CHF) | BAZG / SwissImpex | imports by country | Import dependency |
| Total Goods Trade | BAZG / SwissImpex | exports + imports | Overall trade volume |
| Share of Swiss Goods Trade | BAZG / SwissImpex | country share of CH trade | Strategic relevance for Switzerland |
| Rank as Trade Partner | BAZG / SwissImpex | ranking by total trade | Relative importance for Switzerland |

---

### 5. Analytical Signal Logic

The framework was designed to detect not just static snapshots but **meaningful changes over time**:

| Observation | Possible Signal |
|---|---|
| Rising inflation + declining growth | Economic stress |
| High trade concentration | Dependency risk |
| Rising direct investments | Increasing attractiveness |
| Rising innovation index | Future potential |
| Declining governance indicators | Possible instability |
| Growing trade with Switzerland | Increasing strategic relevance |

---

### 6. Possible Analytical Questions

Derived from the framework, the following questions structure the diplomatic use cases:

1. Which trends and changes become visible across countries?
2. Which indicators show unusual developments?
3. Which factors could point to increasing instability or risks?
4. How do bilateral or multilateral relationships evolve over time?
5. Can public data reveal changes in cooperation or alignment patterns?

---

### 7. Constraints & Assumptions

| Constraint | Description |
|---|---|
| Data access | Only freely accessible or provided datasets may be used |
| Data protection | Data protection and licensing conditions must be respected |
| Scope | Focus on a prototype — not a production-ready system |
| Architecture | Solutions must be modular and extensible |
| Time | Hackathon time constraint (approx. 2 days) |

---

### 8. Strategic Alignment

The analytical framework was explicitly designed in alignment with the **EDA Foreign Policy Strategy 2024–2027**, which identifies the following priorities relevant to this prototype:

- Economic resilience and de-risking
- Supply chain security and diversification
- Bilateral economic relevance monitoring
- Competitiveness and innovation tracking
- Geopolitical fragmentation and instability detection

The framework translates these strategic priorities into **measurable, publicly available indicators**.

---

### 9. Acceptance Criteria (prototype level)

- The prototype answers the central analytical question for any given country
- Outputs are sourced from verified public APIs only
- The LLM synthesises answers from structured evidence, never from raw API responses
- Results include an evidence table with source attribution
- The system is modular and extensible to new data sources and analytical bundles

---

### 10. Sample Output

The prototype generates two types of output:

**Chat briefing** — a direct answer to a country name or analytical question, structured as: Summary Assessment, Evidence Table with source attribution, Interpretation, and Caveats.

**HTML Report** — a more detailed exported report including: Executive Summary, Key Points, Headline Metrics, multi-year trend charts, and Data Caveats. Generated for the Swiss Federal Department of Foreign Affairs (EDA).

Both output types directly reflect the four-level analytical framework defined in this repository. Sample reports for Portugal and France are included below.

---

### 11. Original Contribution — Project Logs (timestamped)

The following text was published by Alfa Diop-Wicki in the official hackathon project logs during the event. It documents the analytical framework as originally defined, before technical implementation.

---

**Possible analytical dimensions**

1. Economic Stability — GDP, GDP growth, GDP per capita, inflation rate, unemployment rate, government debt, income category, innovation index rank.
2. Services Trade — services trade receipts/expenditures, total services trade, Swiss trade share, top sectors.
3. Direct Investments — direct investments abroad, Swiss investment share.
4. Goods Trade — exports/imports, total goods trade, Swiss trade share, trade partner rank.

*Possible objective: Provide a structured view of public selected economic indicators to support country monitoring and user-driven evaluation over time.*

---

**Economic Relationship & Stability Monitoring — Central Question**

> *How relevant, stable and economically attractive is a country for Switzerland, and which trends could become relevant for future economic or diplomatic decisions?*

**Possible Approach** — The prototype could combine public datasets in order to:

1. visualize economic stability,
2. evaluate competitiveness and attractiveness (Investment & Competitiveness),
3. highlight Swiss economic exposure,
4. identify trends over time,
5. detect possible risk or opportunity signals.

---

🔗 Full logs: [govtech.digisus-lab.ch/project/41/log](https://govtech.digisus-lab.ch/project/41/log)

---

## Files in this repository

| File | Description |
|---|---|
| [EDA_Prototype_Indicators_With_Links_Alfa.xlsx](EDA_Prototype_Indicators_With_Links_Alfa.xlsx) | Full indicator list with sources, API parameters, and links |
| [Portugal-HTML-Report.pdf](Portugal-HTML-Report.pdf) | Exported HTML report — Portugal bilateral overview |
| [France-HTML-Report.pdf](France-HTML-Report.pdf) | Exported HTML report — France bilateral overview |

---

## License

This work is published under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).  
You are free to share and adapt this material with attribution.

---

*Business analysis by Alfa Diop-Wicki · GovTech Hackathon 2026 · May 2026*

<div align="center">

# 🌍 World Bank: Global Economic Development & Income Distribution

**A production-grade semantic layer exploring two decades of global GDP and demographic shifts**

<br>

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0F2C59?style=flat-square)
![Power Query M](https://img.shields.io/badge/Power_Query_M-217346?style=flat-square)
![PBIP](https://img.shields.io/badge/PBIP-Source_Controlled-0F2C59?style=flat-square&logo=git&logoColor=white)
![Data](https://img.shields.io/badge/Data-World_Bank_WDI-00843D?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-2EA44F?style=flat-square)

<br>

<a href="https://app.powerbi.com/view?r=eyJrIjoiMGI0MDhkMTEtYmYxZi00NzQ4LTliZjktZGI4Y2YzMWI5YjQ2IiwidCI6ImE1ZGVjZDEwLTkxNjUtNDYzNi1hNjRjLTc5NTgwMDQyMTVmYSIsImMiOjR9">
  <img src="assets/dashboard_screenshot.png" alt="World Bank Dashboard Preview — click to open live report" width="100%">
</a>

<br><br>

[![Open Live Dashboard](https://img.shields.io/badge/▶_OPEN_LIVE_DASHBOARD-118DFF?style=for-the-badge&logoColor=white&labelColor=0F2C59)](https://app.powerbi.com/view?r=eyJrIjoiMGI0MDhkMTEtYmYxZi00NzQ4LTliZjktZGI4Y2YzMWI5YjQ2IiwidCI6ImE1ZGVjZDEwLTkxNjUtNDYzNi1hNjRjLTc5NTgwMDQyMTVmYSIsImMiOjR9)
<br>
<sub>No install required · Opens in your browser</sub>

</div>

<br>

## 📖 Table of Contents

- [Overview](#-overview)
- [Skills Demonstrated](#-skills-demonstrated)
- [Key Features](#-key-features--smart-ui)
- [Business Value & Insights](#-business-value--key-insights)
- [Getting Started](#-getting-started)
- [Technical Deep Dive](#️-technical-deep-dive) — architecture, star schema, DAX patterns
- [Roadmap](#️-roadmap)
- [Contact](#️-contact)

<br>

## 📌 Overview

This project demonstrates the design, optimization, and deployment of a robust **semantic layer** built to analyze global economic disparities, income distribution, and GDP per capita growth over the last two decades.

Engineered using official data from the **World Bank — World Development Indicators (WDI)**, the model is optimized for the VertiPaq engine, enabling seamless exploration of **217 economies (2000–2024)**. All financial figures are dynamically adjusted for **Purchasing Power Parity** *(PPP, constant 2021 international dollars)*.

> **Analytics Engineering Focus:** Decoupled semantic model, version-control-ready architecture (`.pbip`), advanced DAX aggregations, and structural data governance.

<br>

## 🧠 Skills Demonstrated

| Area | Applied Skill |
|---|---|
| **Data Modeling** | Star schema design, decoupled dimensions, disconnected parameter tables |
| **DAX Engineering** | Population-weighted aggregations, virtual filter injection (`TREATAS`), context-aware formatting |
| **Data Storytelling** | Auto-updating narrative panels that adapt copy to the active filter context |
| **Version Control** | `.pbip` project structure for Git diffing, branching, and CI/CD readiness |
| **UX/UI Design** | Custom theming, guided visual hierarchy, dynamic conditional formatting |

<br>

## 💡 Key Features & Smart UI

| Feature | Description |
|---|---|
| 🌐 **Globe Map** | Orthographic choropleth visualizing GDP per capita concentration across hemispheres |
| 🧠 **Smart Narrative** | Auto-updating KPI panel driven by `[Global Income Position]` and `[Economy in Focus]` — adapts contextually to every filter |
| 📉 **Growth Timeline** | Bar chart flagging recession years vs. recovery phases via dynamic HEX color injection |
| 🔬 **Regional Matrix** | `[Population Share]` vs. `[GDP Share]` — exposing structural economic gaps at regional granularity |
| 🏅 **Benchmarking** | Dual-line chart comparing any country or region against the global average without breaking filter context |

<br>

## 🎯 Business Value & Key Insights

A well-architected semantic layer must seamlessly answer complex business questions. The model's dynamic DAX architecture surfaces the following macro-economic trends:

**The Global Divide** — In 2024, despite a global average income of **$21,621 (PPP)**, the model exposes extreme structural gaps: North America generates **16.4% of global GDP** with only **4.7% of the population**, while South Asia holds **20.7% of the population** but accounts for only **9.4% of the GDP**.

**Resilience Tracking** — The dynamic baselines accurately flag the **2020 global recession** across multiple regions, contrasting it directly with the **3.2% global recovery growth rate** marked in 2024.

<br>

## 🚀 Getting Started

**Fastest path:** just [**open the live dashboard**](https://app.powerbi.com/view?r=eyJrIjoiMGI0MDhkMTEtYmYxZi00NzQ4LTliZjktZGI4Y2YzMWI5YjQ2IiwidCI6ImE1ZGVjZDEwLTkxNjUtNDYzNi1hNjRjLTc5NTgwMDQyMTVmYSIsImMiOjR9) — no install required.

To run or audit it locally:

<details>
<summary><strong>📋 Prerequisites</strong></summary>
<br>

| Requirement | Details |
|---|---|
| **Power BI Desktop** | May 2023 or newer — required to open `.pbip` source files |
| **Git** | Any recent version — required to clone the repository |
| **VS Code** *(optional)* | Recommended for TMDL and DAX syntax highlighting |

</details>

<details>
<summary><strong>⚡ Option 1 — Run the Dashboard</strong> <em>(explore the UI and KPIs)</em></summary>
<br>

```bash
# 1. Clone the repository
git clone https://github.com/your-username/worldbank-dashboard.git

# 2. Navigate to the report folder and open in Power BI Desktop
cd worldbank-dashboard/report
# Open: World_Bank_Delivery.pbix
```

</details>

<details>
<summary><strong>🔬 Option 2 — Audit the Semantic Model</strong> <em>(for analytics engineers & reviewers)</em></summary>
<br>

```bash
# 1. Clone the repository
git clone https://github.com/your-username/worldbank-dashboard.git

# 2. Open the semantic-model/ folder in VS Code
cd worldbank-dashboard/semantic-model
```

| Folder | Contents |
|---|---|
| `.SemanticModel/` | Table definitions, relationships, column types (TMDL) |
| `.Report/` | Visual layout, page config, theme references (JSON) |
| `dax/` | Extracted and documented DAX measure patterns |

</details>

<br>

## ⚙️ Technical Deep Dive

<details>
<summary><strong>🏗️ Project Architecture & Version Control</strong></summary>
<br>

Moving away from monolithic `.pbix` files, this repository uses the **Power BI Project (`.pbip`)** structure — a code-first approach that serializes the semantic model and report design into plain text (TMDL/JSON), enabling Git version control, branch collaboration, and CI/CD pipeline integration.

```text
worldbank-dashboard/
│
├── 📁 data/             # Static processed data (Excel/CSV) — local source of truth
├── 📁 semantic-model/   # ⚙️  SEMANTIC LAYER (.pbip): TMDL definition of tables, relations, and DAX
├── 📁 report/           # 📊 PRESENTATION LAYER: JSON layout and visual configurations
├── 📁 dax/              # Documented DAX measure patterns for peer review
└── 📁 assets/           # Custom JSON themes and structural background templates
```

</details>

<details>
<summary><strong>🗂️ Data Model — Star Schema</strong></summary>
<br>

The semantic layer follows a strict **Star Schema** optimized for the VertiPaq engine:

- **Decoupled Dimensions** — `Dim Country` and `Dim Year` are fully separated from the fact table, minimizing memory footprint and maximizing VertiPaq compression ratios.
- **Disconnected Parameter Table** — `Dim Reference Year` has no active physical relationship. It operates exclusively via `TREATAS` and `SELECTEDVALUE` in DAX, enabling point-in-time benchmarking without polluting the primary filter context.

> 🗂️ Full schema diagram, table definitions, field glossary, and relationship map → [`docs/data-model.md`](./docs/data-model.md)

</details>

<details>
<summary><strong>⚡ Advanced DAX Implementation</strong></summary>
<br>

The semantic layer is built on three core DAX engineering patterns:

**① Population-Weighted Macroeconomic Aggregations**

Core KPIs like `[GDP per Capita (PPP)]` and `[Poverty Headcount Ratio]` use a population-weighted `SUMX` iterator to prevent the statistical distortions caused by simple averages — ensuring that large economies carry their proper weight in regional and global aggregates.

```dax
-- Pattern: Population-weighted average (used across all core KPIs)
DIVIDE(
    SUMX(
        FILTER(
            'Fact World Bank Data',
            NOT ISBLANK( 'Fact World Bank Data'[gdp_per_capita] )
        ),
        'Fact World Bank Data'[gdp_per_capita] * 'Fact World Bank Data'[total_population]
    ),
    SUMX(
        FILTER(
            'Fact World Bank Data',
            NOT ISBLANK( 'Fact World Bank Data'[gdp_per_capita] )
        ),
        'Fact World Bank Data'[total_population]
    )
)
```

**② Virtual Filter Injection via `TREATAS`**

Instead of relying on an active model relationship, all base KPIs inject the selected reference year as a virtual filter context using `TREATAS(VALUES('Dim Reference Year'[Year]), 'Dim Year'[year])`. This pattern decouples the UI control from the physical model, preserving the historical trend lines used in background charts.

**③ Context-Aware Formatting & UI/UX**

The UI is programmatically driven by DAX — no native conditional formatting panels:

- **Dynamic Scaling** — `[World Population Display]` uses `HASONEVALUE` + `SWITCH` to format values as `M` (millions) or `K` (thousands) based on filter granularity.
- **Smart Highlighting** — `[GDP per Capita (PPP) Highlighted Color]` injects `#B22222` (recession), `#118DFF` (selected year), `#FFB3B3` / `#CFE7FF` (contextual) directly into visual color bindings.
- **Dynamic Labels** — `[Economy in Focus]`, `[Benchmark Economy]`, and `[Economic Scope Label]` adapt narrative text to the active filter context (country / region / global).

> 📁 All measure code is extracted and documented in the [`/dax`](./dax/) folder for peer review.

</details>

<details>
<summary><strong>🎨 UI/UX Design</strong></summary>
<br>

- **Color System** — custom JSON theme aligned with World Bank corporate identity; blue-dominant, minimal chrome.
- **Layout** — structured grid guiding the eye: global map → regional breakdown → country benchmarking.
- **Typography** — editorial hierarchy separating KPI values, axis labels, and narrative text for fast scanning.

</details>

<br>

## 🛣️ Roadmap

- [ ] **Automated CI/CD Pipeline** — GitHub Actions to deploy the `.pbip` semantic model directly to a Power BI Premium workspace on merge to `main`.
- [ ] **Data Governance & RLS** — Dynamic Row-Level Security restricting regional data access based on Active Directory user roles.
- [ ] **Incremental Refresh** — Refresh policies on `FACT_WORLD_BANK_DATA` to optimize VertiPaq memory as new yearly WDI data is ingested.
- [ ] **Predictive Analytics** — Python-based GDP per capita forecasting model projecting 5-year trends based on historical volatility.

<br>

## 🤝 Acknowledgments & Data Source

Data provided by the **[World Bank Open Data](https://data.worldbank.org/)** portal — World Development Indicators (WDI).
Indicators: **GDP per capita, PPP** *(constant 2021 international $)*, **Gini index**, **Poverty headcount ratio**, **Population totals**.

<br>

---

<div align="center">

## ✉️ Contact

**Yeison** · Data Analyst / Analytics Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](TU_LINK_DE_LINKEDIN)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=githubpages&logoColor=white)](TU_LINK_DEL_PORTAFOLIO)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:TU_CORREO@gmail.com)

<sub>[↑ Back to top](#-world-bank-global-economic-development--income-distribution)</sub>

</div>
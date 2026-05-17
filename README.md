<div align="center">

# 🌍 World Bank: Global Economic Development & Income Distribution

### *Analytics Engineering Portfolio: Building a scalable semantic layer to explore two decades of global GDP and demographic shifts*

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Architecture](https://img.shields.io/badge/Architecture-PBIP_Source_Control-0F2C59?style=for-the-badge&logo=git&logoColor=white)
![Data Source](https://img.shields.io/badge/Data-World_Bank_WDI-00843D?style=for-the-badge&logo=worldhealthorganization&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2EA44F?style=for-the-badge)

<br>

<img src="assets/dashboard_screenshot.jpg" alt="World Bank Dashboard Preview" width="100%">

</div>

---

## 📌 Overview

This project demonstrates the design, optimization, and deployment of a robust **semantic layer** built to analyze global economic disparities, income distribution, and GDP per capita growth over the last two decades.

Engineered using official data from the **World Bank — World Development Indicators (WDI)**, the data model is optimized for the VertiPaq engine, enabling seamless exploration of **217 economies (2000–2024)**. All financial figures are dynamically adjusted for **Purchasing Power Parity** *(PPP, constant 2021 international dollars)*.

> **Analytics Engineering Focus:** Decoupled semantic model, version control readiness (CI/CD) via `.pbip`, DAX optimization, and structural data governance.

---

## 🎯 Business Value & Key Insights

A well-architected semantic layer must seamlessly answer complex business questions. The model's dynamic DAX architecture reveals the following macro-economic trends:

**The Global Divide:** In 2024, despite a global average income of **$21,621 (PPP)**, the model exposes extreme structural gaps: North America generates **16.4% of global GDP** with only **4.7% of the population**, while South Asia holds **20.7% of the population** but only **9.4% of the GDP**.

**Resilience Tracking:** The dynamic baselines accurately flag the **2020 global recession** (red indicator) across multiple regions, contrasting it with the **3.2% global recovery growth rate** marked in 2024.

---

## 🏗️ Project Architecture & Version Control

Moving away from monolithic `.pbix` files, this repository utilizes the **Power BI Project (`.pbip`)** structure. This code-first approach stores the semantic model and report design in plain text (TMDL/JSON), enabling Git version control, branch collaboration, and CI/CD pipeline integration.

```text
worldbank-dashboard/
│
├── 📁 data/             # Static processed data (Excel/CSV) — local source of truth
├── 📁 semantic-model/   # ⚙️  SEMANTIC LAYER (.pbip): TMDL definition of tables, relations, and DAX
├── 📁 report/           # 📊 PRESENTATION LAYER: JSON layout and visual configurations
├── 📁 dax/              # Code documentation for complex analytical patterns
└── 📁 assets/           # Custom JSON themes and structural background templates
```

---

## ⚙️ Engineering & Technical Specifications

### Data Model — Star Schema

```mermaid
erDiagram
    DIM_COUNTRY       ||--o{ FACT_WORLD_BANK_DATA : "1:N (Filters)"
    DIM_YEAR          ||--o{ FACT_WORLD_BANK_DATA : "1:N (Filters)"
    DIM_YEAR_SELECTOR  |o--o{ FACT_WORLD_BANK_DATA : "Disconnected (DAX logic)"

    DIM_COUNTRY {
        Text        country_code PK
        Text        income_level
        Text        region
        Text        more_fields
    }

    DIM_YEAR {
        WholeNumber year PK
    }

    FACT_WORLD_BANK_DATA {
        Text          country_code FK
        WholeNumber   year FK
        DecimalNumber gdp_per_capita
        Text          more_fields
    }

    DIM_YEAR_SELECTOR {
        WholeNumber year
    }
```

**Strict Star Schema** — contextual dimensions (`Dim Country`, `Dim Year`) are fully decoupled from the quantitative fact table, minimizing memory footprint and maximizing VertiPaq compression.

**Disconnected Tables** — `Dim Year Selector` acts as a parameter table. It operates purely via DAX without physical relationships, enabling complex benchmark comparisons (e.g., specific country vs. world average) without polluting the primary filter context.

---

### Advanced DAX Implementation

The semantic model leverages advanced DAX patterns focused on query performance and dynamic context transition:

**① Macroeconomic Weighted Averages**
> `SUMX` iterated over `DIVIDE` to calculate regional and global GDP ratios strictly weighted by population — preventing the statistical distortions of simple averages.

**② Context Transition & Filter Overrides**
> `CALCULATE` + `REMOVEFILTERS` establishes dynamic baselines, preserving historical trend lines in background charts even when strict year filters are applied via slicers.

**③ DAX-Driven UI/UX**
> `SWITCH` injects HEX color codes dynamically (flagging negative growth years) and applies conditional formatting to display numbers as `M` (millions) or `K` (thousands) based on the active filter context.

> 📁 All measure code is documented in the [`/dax`](./dax/) folder.

---

## 🚀 How to Run & Audit

### 📋 Prerequisites

> **Power BI Desktop:** May 2023 release or newer is strictly required to open and compile `.pbip` source files.

### ⚡ Option 1 — Quick View

For UI/UX interactivity and business insight exploration:

```bash
# 1. Clone the repository
git clone https://github.com/your-username/worldbank-dashboard.git

# 2. Open in Power BI Desktop
# Navigate to report/ and open World_Bank_Delivery.pbix
```

### 🔬 Option 2 — Architecture & Code Audit

For peer review of the Semantic Model and TMDL structuring:

```bash
# Navigate to semantic-model/
# Explore .SemanticModel and .Report folders
# VS Code recommended for TMDL syntax highlighting
```

---

## ✉️ Contact

<div align="center">

**Yeison**
Data Analyst · Analytics Engineer

<br>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](TU_LINK_DE_LINKEDIN)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=githubpages&logoColor=white)](TU_LINK_DEL_PORTAFOLIO)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:TU_CORREO@gmail.com)

</div>
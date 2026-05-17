# 🌍 World Bank: Global Economic Development & Income Distribution

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Architecture](https://img.shields.io/badge/Architecture-Source_Control_PBIP-0F2C59?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## 📌 Overview

This analytical project provides an interactive and in-depth view of global economic disparities, income distribution, and GDP per capita growth over the last two decades.

Developed using official data from the **World Bank — World Development Indicators (WDI)**, the dashboard allows users to explore demographic and economic structures at regional and country levels, adjusted for Purchasing Power Parity (PPP in constant 2021 international dollars).

<div align="center">
  <img src="assets/dashboard_screenshot.png" alt="World Bank Dashboard Screenshot" width="100%">
</div>

---

## 🏗️ Project Architecture

To demonstrate best practices in **Analytics Engineering and BI development**, this repository uses the **Power BI Project (`.pbip`)** format for Git version control. This allows keeping the data and design code in plain text (JSON/TMDL), while also providing a compiled file (`.pbix`) for easy visualization and interaction.

```text
worldbank-dashboard/
├── data/       # Static processed data (Excel/CSV) - Local source of truth
├── dataset/    # ⚙️ SOURCE CODE (.pbip): Semantic model and design in plain text for Git
├── report/     # 🚀 DELIVERABLE (.pbix): Compiled file ready for end-users
├── dax/        # Code repository for extracted complex metrics
└── assets/     # Visual resources (JSON Themes, backgrounds, images)
```

---

## 💡 Key Features & Visual Analysis

- **Dynamic Data Storytelling:** A smart narrative panel that automatically updates key metrics based on user filters — for example, highlighting that in 2022, global income levels averaged **20,453 international dollars (PPP)** across **217 Economies** and a population of over **7,966.3 M**.

- **Advanced Geospatial Mapping (Globe Map):** An orthographic map illustrating *Global GDP per Capita by Economy*. The custom blue color scale instantly highlights the concentration of wealth across hemispheres.

- **Interactive Filtering System:**
  - A **Regional Coverage** slicer to isolate specific continents (e.g., East Asia & Pacific, Sub-Saharan Africa).
  - A dynamic **Timeline Slider** at the bottom, enabling seamless cross-filtering from 2000 to 2024.

- **Historical Impact & Volatility:** The *Evolution of Global GDP per Capita Growth* chart visually flags negative growth periods (e.g., the red bar during the **2020 global recession**) versus recovery phases (e.g., **3.6% growth in 2022**).

- **Regional Decomposition Matrix:** A detailed tabular view contrasting **Population Share** (% of World Population) against **GDP Share** (% of Global GDP), clearly exposing structural economic gaps.

- **Relative Benchmarking:** A dual-line chart (*GDP per Capita Relative to the Global Average*) evaluating a specific country's performance — e.g., Singapore — against the overarching Global GDP Trend.

---

## ⚙️ Technical Specifications

### Data Modeling & Transformation

- **Schema:** Dimensional modeling optimized for the VertiPaq engine.
- **Relative Connection:** To ensure portability, the model is fed from the static file located in the `/data/` folder.

### DAX & Time Intelligence

Advanced measures were implemented for calculating:

- Year-over-Year (YoY) Growth percentages.
- Relative percentage contributions (`DIVIDE` combined with `CALCULATE` to modify the filter context).
- Dynamic titles and text cards based on user selection (`SELECTEDVALUE`).

> 📝 The code for the main measures is documented in the `/dax/` folder.

### UI/UX Design

- **Color Palette:** Custom theme (JSON) inspired by the World Bank's corporate identity, prioritizing a clean, minimal interface.
- **Navigation:** Structured grid layout system that guides the user's eye from the high-level global map to specific regional tables and trend lines.

---

## 🚀 How to Run This Project

There are two ways to explore this repository depending on the level of detail you wish to consult:

### Option 1: Quick View *(Recommended for interaction)*

If you want to open the dashboard directly to test its interactivity and design:

1. Clone or download this repository to your local machine.
2. Navigate to the `report/` folder.
3. Open the `World Bank_Delivery.pbix` file with **Power BI Desktop**. The model and charts will load automatically.

### Option 2: Architecture & Code Audit

If you want to inspect the semantic model structure and version control setup:

1. Clone the repository.
2. Navigate to the `dataset/` folder.
3. Open the `.pbip` (Power BI Project) file. Explore the natively generated `.SemanticModel` and `.Report` folders to review code serialization in JSON and TMDL formats.

---

## ✉️ Contact

**[Your Name / Last Name]**  
Data Analyst / Analytics Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](#)
[![Portfolio](https://img.shields.io/badge/Web_Portfolio-000000?style=for-the-badge&logo=githubpages&logoColor=white)](#)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](#)
# Olympic Success Around the World — Data Visualization Project

**DSA 202: Data Visualization · North Carolina State University **

📄 [View the final poster (PDF)](./poster.pdf) · 📄 [View the final narrative (PDF)](./narrative.pdf) · 📊 [View the interactive Tableau dashboard](https://public.tableau.com/app/profile/khushi.chaturvedi5804/viz/OlympicSuccessAroundtheWorld/Dashboard1) · 💻 [View full source code](https://github.com/khushichaturvedi-04/DSA-202)

---

## Overview

A semester-long data visualization project investigating whether Olympic medal success is driven by a nation's wealth, geography, and Games structure. The project combined over a century of Olympic athlete-event data (1896–2016) with World Bank GDP-per-capita figures to build a four-chart interactive story, culminating in a published Tableau Public dashboard, a design-focused narrative writeup, and a final poster.

**Core question:** Do richer countries always win more Olympic medals, and how does the relative scale of the Summer vs. Winter Games affect that picture?

**Key finding:** Olympic success is concentrated among a small number of wealthy, densely populated countries with established sports infrastructure — the United States most prominently — but GDP per capita is a partial predictor at best (e.g., Norway, Luxembourg, and Qatar have high GDP but relatively few medals, while Russia and China have many medals despite lower GDP per capita).

## Data Sources

| Dataset | Source | Coverage |
|---|---|---|
| Olympic Games athlete events & results | Kaggle | 1896 – 2016 |
| GDP per capita | Our World in Data / World Bank | 1990 – 2020 |

## Project Progression

This project was built incrementally across the course, with each stage adding a visualization principle or tool:

- **Assignment 1 — Accessible chart design (Excel):** Built an accessibility-focused bar chart (astronaut mission data) applying core principles: a takeaway-style title, direct data labeling, deliberate color/contrast choices instead of relying on color alone, intentional use of white space, and screen-reader alt text — establishing the accessibility standard carried through the rest of the project.
- **Assignment 2 — Grammar-of-graphics visualization (R):** Built the "Olympic medal records over time by season" line chart in R (`ggplot2` + `dplyr`), aggregating medal counts by year and season and distinguishing Summer vs. Winter using color, line type, *and* point shape simultaneously — so the chart remains readable for viewers with color vision differences.
- **Assignment 3 — Interactive dashboard (Tableau):** Built the initial two-chart Tableau dashboard (medal count by nation, worldwide medal choropleth map), merging the Olympic and GDP datasets by country and establishing the visual language (color encoding, geographic roles) used in the final version.
- **Final deliverable — Full four-chart data story:** Expanded the dashboard to four coordinated visualizations, published to Tableau Public, and packaged with a full written narrative and a formal poster.

## The Four Visualizations

1. **Medal Count by Country (stacked bar chart)** — Top-performing nations broken down by gold/silver/bronze, built in Tableau. The United States is a clear outlier at 5,000+ total medals.
2. **GDP per Capita vs. Medal Count (scatter plot)** — Built in Tableau, plotting each country's average GDP per capita against total medal count. Shows a general positive relationship that breaks down for notable outliers in both directions.
3. **Medal Map (choropleth)** — World map shaded by total medal count using Tableau's built-in geographic country roles, showing medal concentration in North America, Europe, Russia, East Asia, and Oceania.
4. **Olympic Medal Records Over Time by Season (line chart)** — Built in R with `ggplot2`, showing Summer Games medal totals consistently outpacing Winter totals across history, reflecting the larger number of Summer events and broader global participation.

## Design & Accessibility Principles Applied

- Redundant encoding (color **and** shape/linetype) so charts don't rely on color perception alone
- Takeaway-oriented titles that state the finding, not just the topic
- Direct data labeling to avoid forcing axis-estimation
- Deliberate contrast and reduced visual clutter (removed redundant legends/gridlines)
- Alt text included for screen-reader accessibility

## Skills Demonstrated

`Tableau` (dashboard design, geographic mapping, dataset blending) · `R` (`ggplot2`, `dplyr`) · `Excel` (PivotCharts, accessibility features) · `Data Visualization Design Principles` · `Accessibility-First Chart Design` · `Data Storytelling` · `Exploratory Data Analysis` · `Data Source Integration/Blending`

## Result

Published an interactive four-chart Tableau Public dashboard alongside a full written narrative and formal poster, synthesizing over a century of Olympic data with global economic indicators into a coherent, accessible data story.

## Repository

Full source — Excel workbook, R Markdown, Tableau workbook, and datasets — is available in the [`DSA-202`](https://github.com/khushichaturvedi-04/DSA-202) repository.

---
*DSA 202 — Data Visualization, NC State University, Spring 2026*

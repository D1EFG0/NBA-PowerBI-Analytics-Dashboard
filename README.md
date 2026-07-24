# 🏀 NBA Power BI Analytics Dashboard

An interactive Power BI dashboard analyzing the **2024–2025 NBA season** using business intelligence best practices.

This project demonstrates the complete BI workflow from raw data transformation to executive reporting using Power BI.

---

# Dashboard Preview

## Executive Dashboard

![Executive Dashboard](images/executive-dashboard.png)

The Executive Dashboard provides a high-level overview of league performance, highlighting the highest-scoring team, best shooting teams, league averages, player totals, and executive insights.

---

## Data Model

The dashboard is built using a dimensional star schema to support scalable reporting and efficient DAX calculations.

## DAX Showcase

The dashboard uses custom DAX measures to calculate advanced basketball analytics while avoiding duplicate aggregation and ensuring accurate business reporting.

### Team Points Per Game

```DAX
Team PPG =
AVERAGEX(
    SUMMARIZE(
        Fact_Team_Game,
        Fact_Team_Game[Tm],
        Fact_Team_Game[Date],
        "GamePts", SUM(Fact_Team_Game[Team_PTS])
    ),
    [GamePts]
)
```

**Purpose**

Calculates each team's average points per game by first aggregating points at the game level and then averaging those totals. This approach prevents duplicate aggregation and produces accurate team-level statistics.

---

### Games Played

```DAX
Games Played =
DISTINCTCOUNT(Fact_Team_Game[GameKey])
```

**Purpose**

Calculates the number of unique games played for the selected player or team using a distinct game identifier.

---

### Dynamic Executive Dashboard Insight

```DAX
Executive Dashboard Highlights
```

**Purpose**

Generates dynamic narrative insights for the Executive Dashboard using DAX variables and text functions, automatically updating key business insights based on report calculations.

### Model Components

- **Fact_Team_Game** – Stores team-level game statistics.
- **Dim_Player** – Player dimension used for player-level analysis.
- **Dim_Team** – Team dimension used throughout the report.
- **Dim_Date** – Calendar dimension enabling time-series analysis.
- **Measures_Table** – Centralized repository for reusable DAX measures.
- **Team Metrics** – Supporting table used for metric selection and report flexibility.

This model separates facts from dimensions, improving report performance, simplifying relationships, and following Business Intelligence best practices.

![Data Model](images/data-model.png)



## Player Analysis

![Player Analysis](images/player-analysis.png)

Analyze individual player performance through interactive filtering, KPIs, and game-by-game scoring trends.

Features include:

- Points Per Game
- Rebounds Per Game
- Assists Per Game
- Shooting Percentages
- Minutes Per Game
- Games Played
- Dynamic scoring trend

---

## Team Analysis

![Team Analysis](images/team-analysis.png)

Compare every NBA team using interactive team selection, league rankings, and historical scoring trends.

---

## League Analysis

![League Analysis](images/league-analysis.png)

Explore league-wide relationships using scatter plots, custom report page tooltips, and efficiency rankings.

---

# Project Overview

The objective of this project was to build a complete Business Intelligence solution capable of transforming raw NBA game data into actionable insights for coaches, analysts, and executives.

The report emphasizes clean design, intuitive navigation, interactive exploration, and executive-level reporting.

---

# Skills Demonstrated

- Microsoft Power BI
- DAX
- Power Query
- Star Schema Data Modeling
- KPI Design
- Interactive Dashboards
- Report Page Tooltips
- Data Visualization
- Business Intelligence Reporting
- Sports Analytics

---

# Technologies

- Microsoft Power BI
- Power Query
- DAX
- NBA 2024–2025 Season Dataset

---

# Business Questions Answered

- Which team has the highest scoring offense?
- Which teams shoot most efficiently?
- Who are the league's top scorers?
- How does shooting efficiency relate to offensive production?
- How has player scoring changed throughout the season?
- How do teams compare across key offensive metrics?

---

# Project Highlights

✅ Executive Dashboard

✅ Interactive Player Analytics

✅ Team Performance Dashboard

✅ League Analysis Dashboard

✅ Dynamic DAX Measures

✅ Custom Report Page Tooltips

✅ Interactive Filtering

✅ Business-Oriented Visual Design

---

# Future Improvements

- Predictive player performance modeling
- Team comparison dashboard
- Win probability analytics
- Advanced player similarity analysis
- Automated data refresh pipeline

---

# Author

**Diego Castillo**

B.S. Computer Science

M.S. Sports Management

Business Intelligence • Data Analytics • Sports Analytics

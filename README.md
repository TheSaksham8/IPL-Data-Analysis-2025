# IPL-Data-Analysis-2025
## Author: Saksham Chaturvedi
# Overview
This project ingests Indian Premier League 2025 data from a cricket API, cleans and models it with Python/SQL, and builds interactive Power BI dashboards for match results, points table, squads, and records.
It is structured as a reproducible pipeline so anyone can fetch raw data, transform it into analytics-ready tables, and refresh the Power BI report locally.

# Preview
![image  alt](https://github.com/TheSaksham8/IPL-Data-Analysis-2025/blob/61fb9533ecfec1aced38f54cdcac1196d858ce5b/Images/Home1.png)
![image alt](https://github.com/TheSaksham8/IPL-Data-Analysis-2025/blob/fe6890028748c84a3c14be7512e83855fd42a7b9/Images/Overview1.png)
![Logo](https://github.com/TheSaksham8/IPL-Data-Analysis-2025/blob/fe6890028748c84a3c14be7512e83855fd42a7b9/Images/Points%20%20table1.png)
![Logo](https://github.com/TheSaksham8/IPL-Data-Analysis-2025/blob/fe6890028748c84a3c14be7512e83855fd42a7b9/Images/Squads1.png)

# Key features
• Automated data collection from a cricket API with parameterized endpoints for schedule, matches, points table, teams, and squads.

• Robust cleaning: schema-normalized tables, date parsing, null handling, de-duplication, and type-safe columns for analytics.

• Analytical model: star-schema with Facts (Matches, Innings, Batting, Bowling) and Dimensions (Teams, Players, Venues, Seasons).

• Power BI dashboards with slicers, KPIs, performance tiles, and DAX measures for wins, NRR, strike rate, economy, and player form.

• Reproducible local refresh: one-click Python pipeline + Power BI refresh connected to curated parquet/CSV outputs.

## Technology Used
• Python, Pandas, Requests, python-dotenv, and PyArrow/Parquet for efficient data handling

• SQL (SQLite or MySQL) for integrity checks and ad‑hoc analysis queries.

• Power BI Desktop with DAX measures and Power Query transformations.

##  Data sources
• Cricket API endpoints are used for schedules, results, team rosters, and points table; store raw responses before transformations for full traceability.

• Respect rate limits, cache responses where possible, and keep API keys in environment variables rather than committing secrets.

## Data model
Fact tables: FactMatches, FactInnings, FactBatting, FactBowling.

Dimension tables: DimTeams, DimPlayers, DimVenues, DimDate, DimSeason.

### Primary relationships
• DimTeams ↔ FactMatches (home_team_id, away_team_id).

• DimPlayers ↔ FactBatting/FactBowling (player_id).

• DimDate ↔ all facts (match_date_key).

### Things Remember
• Row counts, unique keys, and referential integrity (e.g., every match has two valid teams).

• Numeric ranges (overs, runs, wickets), date validity, and duplicate removal.

# US-Aligned Raw Materials Sourcing Pipeline

Data pipeline for identifying, tracking, and analyzing raw material suppliers from the US and US-aligned nations. Supports supply chain resilience by prioritizing domestic and allied sourcing for critical materials.

## Objective

Build an end-to-end data pipeline that:
- Ingests raw material supplier data from public trade databases, government sources (USGS, ITA, Census Bureau), and allied-nation trade APIs
- Classifies suppliers by country of origin and alliance status (NATO, Five Eyes, AUKUS, bilateral allies)
- Tracks critical minerals and strategic materials (rare earths, lithium, cobalt, titanium, etc.)
- Flags supply chain risks such as single-source dependencies or adversary-nation concentration
- Serves analytics dashboards for sourcing decisions

## Architecture

```
[Public APIs / Trade DBs]  -->  [Ingestion Layer]  -->  [Bronze Zone (Raw)]
                                                              |
                                                        [Transform / Enrich]
                                                              |
                                                        [Silver Zone (Clean)]
                                                              |
                                                   [Risk Scoring & Classification]
                                                              |
                                                        [Gold Zone (Analytics)]
                                                              |
                                                        [Dashboard / Reports]
```

## Data Sources

| Source | Description |
|--------|-------------|
| USGS Mineral Commodity Summaries | US mineral production and import data |
| US International Trade Administration | Trade flow and tariff data |
| Census Bureau Foreign Trade | Import/export statistics by commodity |
| UN Comtrade | International trade data for allied nations |
| USITC DataWeb | Tariff and trade data |

## Key Features

- **Alliance Classification Engine** - Categorizes suppliers by geopolitical alignment (US domestic, NATO, Five Eyes, AUKUS, other allies, neutral, adversary)
- **Critical Material Tracker** - Monitors supply levels for DoD-critical materials per the CMMC strategic materials list
- **Risk Scoring** - Flags concentration risk, single-source dependencies, and adversary-nation exposure
- **Substitution Recommender** - Suggests alternative US/allied sources when adversary-nation dependencies are detected

## Tech Stack

`Python` `Airflow` `PostgreSQL` `AWS S3` `dbt` `Streamlit`

## Status

In development - project scaffolding phase.

# actor_analytics_project

# 🎬 Actor Analytics Platform — SQL Data Engineering Project

This project implements a **SQL-based data modeling pipeline** to track actor performance across time using **cumulative history**, **Type 2 Slowly Changing Dimensions (SCD)**, and **incremental data processing**.

It reflects core data engineering patterns and supports powerful analytics — all modeled in **PostgreSQL**.

---

## 🔧 Tech & Tools

- PostgreSQL
- SQL (PostgreSQL syntax)
- pgAdmin



## Data Source

The dataset was loaded using a PostgreSQL `.dump` file from a real server (not included here).

---

## Data Model

### Composite Type: `films`

Each actor stores their film history as an array of composite records (`film`, `votes`, `rating`, `filmid`).

```sql
CREATE TYPE films AS (
  film TEXT,
  votes INT,
  rating NUMERIC,
  filmid TEXT
);

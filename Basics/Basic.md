# SQL Learning Journey – HackerRank (Beginner Level)

Welcome to my SQL practice repository!  
This repo contains my solutions to the **first 10 beginner-level SQL problems from HackerRank** as part of my learning journey toward mastering SQL for placements and real-world projects.

---

## Goals of This Repository

- Build strong SQL fundamentals  
- Understand core query patterns  
- Practice real interview-style problems  
- Improve problem-solving speed  

---

## What I Learned

- Writing basic `SELECT` queries  
- Filtering data using `WHERE`  
- Removing duplicates using `DISTINCT`  
- Sorting results using `ORDER BY`  
- Understanding real-world datasets  

---

## Problem List (Beginner – First 10)

| # | Problem Name | Concepts Used | Link |
|--|-------------|--------------|------|
| 1 | Revising the Select Query I | `SELECT *` | https://www.hackerrank.com/challenges/revising-the-select-query |
| 2 | Revising the Select Query II | `WHERE` condition | https://www.hackerrank.com/challenges/revising-the-select-query-2 |
| 3 | Select All | Basic `SELECT` | https://www.hackerrank.com/challenges/select-all-sql |
| 4 | Select By ID | `WHERE id = value` | https://www.hackerrank.com/challenges/select-by-id |
| 5 | Japanese Cities' Attributes | `WHERE` filtering | https://www.hackerrank.com/challenges/japanese-cities-attributes |
| 6 | Japanese Cities' Names | Column selection | https://www.hackerrank.com/challenges/japanese-cities-name |
| 7 | Weather Observation Station 1 | Multiple column select | https://www.hackerrank.com/challenges/weather-observation-station-1 |
| 8 | Weather Observation Station 3 | `DISTINCT` | https://www.hackerrank.com/challenges/weather-observation-station-3 |
| 9 | Weather Observation Station 4 | `COUNT`, `DISTINCT` | https://www.hackerrank.com/challenges/weather-observation-station-4 |
| 10 | Weather Observation Station 5 ⭐ | `ORDER BY`, `LENGTH()`, Top K | https://www.hackerrank.com/challenges/weather-observation-station-5 |

---

##  Highlight Problem

### ⭐ Weather Observation Station 5

**Concepts Used:**
- `ORDER BY`
- `LENGTH()`
- Multi-column sorting
- Fetching top result

**What I Learned:**
> Instead of using `MIN()` / `MAX()`, sorting + limiting gives better control when tie-breaking is needed.

---

## 🛠️ SQL Concepts Covered

```sql
SELECT column FROM table;
SELECT DISTINCT column FROM table;
SELECT * FROM table WHERE condition;
SELECT * FROM table ORDER BY column;
SELECT COUNT(DISTINCT column) FROM table;
SELECT column, LENGTH(column) FROM table;

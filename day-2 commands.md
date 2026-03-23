#  Day 2 – SQL Learning Journey 

> Documenting the SQL concepts I learned today as part of my placement preparation.

---

##  Topics Covered

* Pivoting Data (Rows → Columns)
* `ROW_NUMBER()` Window Function
* Conditional Aggregation (`CASE WHEN`)
* `COUNT(DISTINCT)`
* `AVG()` and Rounding (`ROUND`, `CEIL`)
* String Manipulation (`REPLACE`)
* Type Casting (`CAST`)
* SQL Joins (`LEFT JOIN`)

---

## 🔹 1. Pivoting Data (Rows → Columns)

Convert row values into column format using:

```sql
ROW_NUMBER() + CASE WHEN + MAX()
```

### Example:

```sql
SELECT
    MAX(CASE WHEN occupation = 'Doctor' THEN name END) AS Doctor,
    MAX(CASE WHEN occupation = 'Professor' THEN name END) AS Professor,
    MAX(CASE WHEN occupation = 'Singer' THEN name END) AS Singer,
    MAX(CASE WHEN occupation = 'Actor' THEN name END) AS Actor
FROM (
    SELECT
        name,
        occupation,
        ROW_NUMBER() OVER (PARTITION BY occupation ORDER BY name) AS rn
    FROM occupations
) t
GROUP BY rn;
```

---

## 🔹 2. ROW_NUMBER()

Assigns a unique number to rows within a group.

```sql
ROW_NUMBER() OVER (PARTITION BY column ORDER BY column)
```

📌 Used for:

* Ranking
* Group-wise alignment (Pivot problems)

---

## 🔹 3. CASE WHEN

Used for conditional logic in SQL.

```sql
CASE 
    WHEN condition THEN value
END
```

📌 Used in:

* Pivot queries
* Conditional columns

---

## 🔹 4. COUNT(DISTINCT)

Counts unique values.

```sql
COUNT(DISTINCT column_name)
```

📌 Used when joins create duplicate rows.

---

## 🔹 5. AVG() and Rounding

### Average:

```sql
AVG(column)
```

### Round to nearest:

```sql
ROUND(AVG(column))
```

### Round up:

```sql
CEIL(AVG(column))
```

---

## 🔹 6. REPLACE()

Replace characters in a string.

```sql
REPLACE(column, 'old', 'new')
```

📌 Example:

```sql
REPLACE(salary, '0', '')
```

---

## 🔹 7. CAST()

Convert one data type into another.

```sql
CAST(expression AS datatype)
```

📌 Example:

```sql
CAST(REPLACE(salary, '0', '') AS UNSIGNED)
```

---

## 🔹 8. LEFT JOIN

Used to combine tables while keeping all records from the left table.

```sql
SELECT *
FROM table1
LEFT JOIN table2
ON condition;
```

📌 Used in:

* Hierarchical queries
* Avoiding data loss

---

## Key Takeaways

* Pivot problems follow a fixed pattern:

  ```
  ROW_NUMBER + CASE + MAX + GROUP BY
  ```
* Always use `COUNT(DISTINCT)` when duplicates are possible.
* Use `CAST()` when working with string functions.
* Use `CEIL()` when question says "round up".

---

## 🚀 Progress

✅ Day 2 Completed
📈 Moving towards advanced SQL for placements

---

## 💼 Next Goals

* Practice advanced joins
* Solve aggregation + HAVING problems
* Learn subqueries deeply

---

> “Consistency beats intensity. One day at a time.” 💪

#  SQL Learning Journey 
> A structured collection of SQL concepts, patterns, and queries learned during my placement preparation.

---

##  Topics Covered

- Filtering (`WHERE`)
- Pattern Matching (`LIKE`)
- String Functions
- Sorting (`ORDER BY`)
- Aggregation (`GROUP BY`, `COUNT`)
- Conditional Logic (`CASE`)
- String Formatting (`CONCAT`)

---

##  1. Filtering Even IDs

```sql
-- MySQL
SELECT *
FROM table_name
WHERE id % 2 = 0;

-- Db2
SELECT *
FROM table_name
WHERE MOD(id, 2) = 0;
```

---

## 🔹 2. Remove Duplicates

```sql
SELECT DISTINCT city
FROM station;
```

---

## 🔹 3. Pattern Matching (LIKE)

```sql
-- Starts with 'a'
WHERE city LIKE 'a%'

-- Ends with 'a'
WHERE city LIKE '%a'

-- Contains 'a'
WHERE city LIKE '%a%'
```

---

## 🔹 4. Vowel-Based Filtering

### Starts with vowel

```sql
WHERE LOWER(city) LIKE 'a%' OR LOWER(city) LIKE 'e%'
   OR LOWER(city) LIKE 'i%' OR LOWER(city) LIKE 'o%'
   OR LOWER(city) LIKE 'u%'
```

### ❌ Does NOT start with vowel

```sql
WHERE LOWER(city) NOT LIKE 'a%'
AND LOWER(city) NOT LIKE 'e%'
AND LOWER(city) NOT LIKE 'i%'
AND LOWER(city) NOT LIKE 'o%'
AND LOWER(city) NOT LIKE 'u%'
```

---

## 🔹 5. First & Last Character Extraction

```sql
-- First character
SUBSTR(city, 1, 1)

-- Last character
SUBSTR(city, LENGTH(city), 1)
```

---

## 🔹 6. LEFT & RIGHT (MySQL)

```sql
LEFT(name, 2)    -- First 2 characters
RIGHT(name, 3)   -- Last 3 characters
```

---

## 🔹 7. Sort by Last 3 Characters

```sql
SELECT name
FROM students
WHERE marks > 75
ORDER BY SUBSTRING(name, LENGTH(name)-2, 3), id;
```

---

## 🔹 8. String Formatting (CONCAT)

```sql
SELECT CONCAT(name, '(', LEFT(occupation, 1), ')')
FROM occupations
ORDER BY name;
```

---

## 🔹 9. Aggregation + Formatting

```sql
SELECT
  CONCAT('There are a total of ', COUNT(*), ' ', LOWER(occupation), 's.')
FROM occupations
GROUP BY occupation
ORDER BY COUNT(*), occupation;
```

---

## 🔹 10. CASE Statement (Classification)

```sql
SELECT
  CASE
    WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
    WHEN A = B AND B = C THEN 'Equilateral'
    WHEN A = B OR B = C OR A = C THEN 'Isosceles'
    ELSE 'Scalene'
  END
FROM triangles;
```

---

## 🔹 11. Logical Operators

| Operator | Meaning                    |
|----------|----------------------------|
| `AND`    | All conditions must be true |
| `OR`     | Any condition true          |
| `NOT`    | Reverse condition           |

---

## 🔹 12. SQL Patterns Learned

| Pattern                  | Syntax                        |
|--------------------------|-------------------------------|
| ✅ Filtering              | `WHERE condition`             |
| ✅ Pattern Matching       | `LIKE '%pattern%'`            |
| ✅ String Extraction      | `SUBSTR()`, `LEFT()`, `RIGHT()` |
| ✅ Sorting                | `ORDER BY column`             |
| ✅ Aggregation            | `GROUP BY column`             |
| ✅ Conditional Classification | `CASE WHEN ... THEN ...`  |
| ✅ String Formatting      | `CONCAT()`                    |

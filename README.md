# SQL Joins Homework

This document demonstrates various types of SQL Joins based on the exercises from Chapter 7 of the textbook.

### Types of Joins

```sql
-- Inner Join
--The `INNER JOIN` keyword selects records that have matching values in both tables.
SELECT a.name, b.order_id
FROM customers a
INNER JOIN orders b ON a.customer_id = b.customer_id;

-- Left Join
--The LEFT JOIN keyword returns all records from the left table (customers), and the matched records from the right table (orders). The result is NULL from the right side, if there is no match.
SELECT a.name, b.order_id
FROM customers a
LEFT JOIN orders b ON a.customer_id = b.customer_id;

-- Right Join
--The RIGHT JOIN keyword returns all records from the right table (orders), and the matched records from the left table (customers). The result is NULL from the left side, when there is no match.
SELECT a.name, b.order_id
FROM customers a
RIGHT JOIN orders b ON a.customer_id = b.customer_id;

-- Full Outer Join
--The FULL OUTER JOIN keyword returns all records when there is a match in either left (customers) or right (orders) table records. Note that not all databases support FULL OUTER JOIN.
SELECT a.name, b.order_id
FROM customers a
FULL OUTER JOIN orders b ON a.customer_id = b.customer_id;

-- Cross Join
--The CROSS JOIN keyword returns the Cartesian product of the two tables. That means it will return all possible combinations of rows from the two tables.
SELECT a.name, b.order_id
FROM customers a
CROSS JOIN orders b;
```

# SQL Homework Queries

## Get the number of cities in the USA

```sql
--Using count, get the number of cities in the USA:

SELECT COUNT(*) AS number_of_cities
FROM city
WHERE CountryCode = 'USA';

--Find out what the population and average life expectancy for people in Argentina (ARG) is

SELECT Population, AVG(LifeExpectancy) AS avg_life_expectancy
FROM country
WHERE Code = 'ARG';

--Display all the cities for any country of your choice besides the USA (Example: Canada):

SELECT Name
FROM city
WHERE CountryCode = 'CAN';

--Two additional queries:

--Find the total population of all cities in Germany (DEU)

SELECT SUM(Population) AS total_population
FROM city
WHERE CountryCode = 'DEU';

--List all countries with a population greater than 100 million

SELECT Name
FROM country
WHERE Population > 100000000;


```

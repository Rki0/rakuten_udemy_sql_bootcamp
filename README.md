# SQL Bootcamp

## SELECT

```SQL
SELECT column_name
FROM table_name;
```

<img width="827" alt="Screenshot 2024-11-01 at 9 11 56" src="https://github.com/user-attachments/assets/604885bb-b2db-4324-811f-b190a1e4b23a">

---

```SQL
SELECT c1
FROM table_1;
```

<img width="824" alt="Screenshot 2024-11-01 at 9 12 25" src="https://github.com/user-attachments/assets/1b2d78b5-a5ba-4b79-a531-79319d8e04de">

---

```SQL
SELECT c1, c2
FROM table_1;
```

<img width="810" alt="Screenshot 2024-11-01 at 9 15 48" src="https://github.com/user-attachments/assets/c9e4d4bc-3314-4226-bb2b-2302b9614179">

---

```SQL
SELECT c1, c3
FROM table_1;
```

<img width="808" alt="Screenshot 2024-11-01 at 9 13 33" src="https://github.com/user-attachments/assets/a374ee65-8f5b-48f0-bac0-673a557a00bb">

---

```SQL
SELECT *
FROM table_1;
```

<img width="810" alt="Screenshot 2024-11-01 at 9 15 02" src="https://github.com/user-attachments/assets/aea308a4-054e-486b-be7c-2fcede26dc9e">

### Challenge

Q1. Grab the first and last names of every customer and their email address.

```SQL
SELECT first_name, last_name, email
FROM customer;
```

## DISTINCT

```SQL
SELECT DISTINCT column_name
FROM table_name;


SELECT DISTINCT(column_name)
FROM table_name;
```

<img width="553" alt="Screenshot 2024-11-01 at 9 46 33" src="https://github.com/user-attachments/assets/a9e8ff69-32c9-4646-b87e-bf5c5519f801">

---

```SQL
SELECT DISTINCT name
FROM color_table;
```

<img width="268" alt="Screenshot 2024-11-01 at 9 49 17" src="https://github.com/user-attachments/assets/c372a65a-4853-4d56-9c1e-a635419cacc6">

---

```SQL
SELECT DISTINCT choice
FROM color_table;
```

<img width="401" alt="Screenshot 2024-11-01 at 9 50 55" src="https://github.com/user-attachments/assets/5fbd8e37-dc1d-4c44-af63-86136a2c1968">

### Challenge

Q1. Retrieve the distinct rating types our films could have in our database.

```SQL
SELECT DISTINCT rating
FROM film;
```

## COUNT

```SQL
SELECT COUNT(column_name)
FROM table_name;
```

<img width="553" alt="Screenshot 2024-11-01 at 9 46 33" src="https://github.com/user-attachments/assets/a9e8ff69-32c9-4646-b87e-bf5c5519f801">

---

```SQL
SELECT COUNT(name)
FROM table;

SELECT COUNT(choice)
FROM table;

SELECT COUNT(*)
FROM table;
```

<img width="404" alt="Screenshot 2024-11-01 at 9 59 31" src="https://github.com/user-attachments/assets/849efe23-f904-47cd-8609-b34c40ffddad">

- Each column has the same number or rows.
- All returns the same thing, sice the original table had 4 rows.
- Because of this `COUNT` by itself simply returns back a count of the number of rows in a table.
- `COUNT` is much more useful when combined with other commands, such as `DISTINCT`.

---

```SQL
SELECT COUNT(DISTINCT name)
FROM table;

SELECT COUNT(DISTINCT (name))
FROM table;
```

<img width="404" alt="Screenshot 2024-11-01 at 10 03 23" src="https://github.com/user-attachments/assets/28370362-eabe-4d1b-99df-f2ebb1056fcc">

## WHERE

```SQL
SELECT column1, column2
FROM table
WHERE conditions;
```

<img width="553" alt="Screenshot 2024-11-01 at 9 46 33" src="https://github.com/user-attachments/assets/a9e8ff69-32c9-4646-b87e-bf5c5519f801">

### Comparison Operators

<img width="1016" alt="Screenshot 2024-11-01 at 10 11 09" src="https://github.com/user-attachments/assets/bb7f40db-9f12-4bdd-aeab-7fe8375807c7">

### Logical Operators

- AND
- OR
- NOT

---

```SQL
SELECT name
FROM table
WHERE name='David';
```

<img width="408" alt="Screenshot 2024-11-01 at 10 13 20" src="https://github.com/user-attachments/assets/1e29165b-849b-48ac-bbdd-b16e68d7fc9f">

---

```SQL
SELECT name, choice
FROM table
WHERE name='David';
```

<img width="792" alt="Screenshot 2024-11-01 at 10 12 43" src="https://github.com/user-attachments/assets/a7b87868-46c5-4164-84a6-2af290581555">

---

```SQL
SELECT name, choice
FROM table
WHERE
  name='David'
  AND choice='Red';
```

<img width="801" alt="Screenshot 2024-11-01 at 10 17 41" src="https://github.com/user-attachments/assets/7353ecf2-7320-4b69-94f6-d075ee237552">

### Challenge

Q1. What is the email for the customer with the name Nancy Thomas?

```SQL
SELECT email
FROM customer
WHERE
  first_name='Nancy'
  AND last_name='Thomas';
```

Q2. Could you give them the description for the movie "Outlaw Hanky"?

```SQL
SELECT description
FROM film
WHERE title='Outlaw Hanky';
```

Q3. Can you get the phone number for the customer who lives at "259 Ipoh Drive"?

```SQL
SELECT phone
FROM address
WHERE address='259 Ipoh Drive';
```

## ORDER BY

```SQL
SELECT column_1, column_2
FROM table
ORDER BY column_1 ASC

SELECT column_1, column_2
FROM table
ORDER BY column_1 DESC
```

- If you leave it blank, `ORDER BY` uses `ASC` by default.

<img width="828" alt="Screenshot 2024-11-01 at 10 36 46" src="https://github.com/user-attachments/assets/d371b9c3-0bce-430d-b856-76167a78aaec">

---

```SQL
SELECT company, name, sales
FROM table
ORDER BY company, sales
```

<img width="834" alt="Screenshot 2024-11-01 at 10 39 18" src="https://github.com/user-attachments/assets/8f024ff8-88ca-4361-94a4-7cc0f87caf3f">

### Challenge

Q1. What are the customer ids of the first 10 customers who created a payment?

```SQL
SELECT customer_id
FROM payment
ORDER BY payment_date ASC
LIMIT 10;
```

Q2. What are the titles of the 5 shortest (in length of runtime) movies?

```SQL
SELECT title, length
FROM film
ORDER BY length ASC
LIMIT 5;
```

Q3. If the previous customer can watch any movie that is 50 minutes or less in run time, how many options does she have?

```SQL
SELECT COUNT(title)
FROM film
WHERE length <= 50;
```

## LIMIT

```SQL
SELECT column_1, column_2
FROM table
LIMIT n;
```

<img width="709" alt="Screenshot 2024-11-01 at 10 47 35" src="https://github.com/user-attachments/assets/09104f6d-33dc-49a9-9a68-8c0f0d4a06a1">

- The `LIMIT` command allows us to limit the number of rows returned for a query.
- Useful for not wanting to return every single row in a table, but only view the top few rows to get an idea of the table layout.
- `LIMIT` goes at the very end of a query request and is the last command to be executed.

---

```SQL
SELECT *
FROM payment
LIMIT 1;
```

<img width="705" alt="Screenshot 2024-11-01 at 10 49 36" src="https://github.com/user-attachments/assets/c5e0bd48-1398-4573-af29-8f18fd7687f1">

---

```SQL
SELECT *
FROM payment
ORDER BY payment_date DESC
LIMIT 5;
```

<img width="708" alt="Screenshot 2024-11-01 at 10 48 44" src="https://github.com/user-attachments/assets/85615abf-7596-4dbd-9aa9-0c41aeefbc96">

## BETWEEN

<img width="712" alt="Screenshot 2024-11-01 at 10 59 38" src="https://github.com/user-attachments/assets/175a021e-baed-46d9-88af-c21692806f3b">

- The `BETWEEN` operator can be used to match a value against a range of values
  - `value >= low AND value <= high` is the same as `value BETWEEN low AND high`
- You can also combine `BETWEEN` with the `NOT` logical operator
  - `value < low OR value > high` is the same as `value NOT BETWEEN low AND high`
- The `BETWEEN` operator can also be used with dates.
  - Note that you need to format dates in the ISO 8601 standard format, which is YYYY-MM-DD
  - `date BETWEEN '2007-01-01' AND '2007-02-01'`

---

```SQL
SELECT *
FROM payment
WHERE amount BETWEEN 8 AND 9;;
```

<img width="709" alt="Screenshot 2024-11-01 at 10 59 58" src="https://github.com/user-attachments/assets/a7c30968-6783-4e51-8fff-a03369485032">

---

```SQL
SELECT *
FROM payment
WHERE amount NOT BETWEEN 8 AND 9;
```

<img width="712" alt="Screenshot 2024-11-01 at 11 00 43" src="https://github.com/user-attachments/assets/593dd8fc-fccb-4393-bdef-f1258d476daf">

---

```SQL
SELECT *
FROM payment
WHERE payment_date BETWEEN '2007-02-01' AND '20007-02-15';
```

<img width="712" alt="Screenshot 2024-11-01 at 11 01 44" src="https://github.com/user-attachments/assets/20c9627c-4ecc-4d5e-9910-1312d9030c16">

## IN

```SQL
value IN(option 1, option 2, ..., option_n)
```

---

```SQL
SELECT *
FROM payment
WHERE amount IN(0.99, 1.98);
```

<img width="707" alt="Screenshot 2024-11-01 at 11 05 15" src="https://github.com/user-attachments/assets/45a605a6-9577-4c75-b384-41311e9a359a">

---

```SQL
SELECT *
FROM customer
WHERE first_name IN('John', 'Jake', 'Julie');
```

<img width="1216" alt="Screenshot 2024-11-01 at 11 06 35" src="https://github.com/user-attachments/assets/ca5651ff-8002-465b-adc1-cd4c3b8d9428">

---

```SQL
SELECT *
FROM customer
WHERE first_name NOT IN('John', 'Jake', 'Julie');
```

<img width="1213" alt="Screenshot 2024-11-01 at 11 07 25" src="https://github.com/user-attachments/assets/a1313378-dab4-4907-8ceb-6d15962127e8">

## LIKE and ILIKE

- The `LIKE` operator allows us to perform pattern matching against string data with the use of wildcard characters:
  - Percent %
    - Matches any sequence of characters
    - All names that begin with an 'A'
      - `WHERE name LIKE 'A%'`
    - All names that end with an 'a'
      - `WHERE name LIKE '%a'`
  - Underscore \_
    - Matches any single character
    - Get all Mission Impossible films
      - `WHERE title LIKE 'Mission Impossible _'`
    - You can use multiple underscores to get the format like "Version#A4", "Version#B7", etc.
      - `WHERE value LIKE 'Version#__'`
- We can also combine pattern matching operators to create more complex patterns
  - `WHERE name LIKE '_her%'`
    - Cheryl
    - Theresa
    - Sherri
- Notice that `LIKE` is case-sensitive, we can use `ILIKE` which is case-insensitive.

---

```SQL
SELECT *
FROM customer
WHERE
  first_name LIKE 'J%'
  AND last_name LIKE 'S%';
```

<img width="1214" alt="Screenshot 2024-11-01 at 12 17 04" src="https://github.com/user-attachments/assets/082755c9-0dbb-4e82-afdf-2e40b45e931d">

---

```SQL
SELECT *
FROM customer
WHERE
  first_name LIKE 'j%'
  AND last_name LIKE 's%';
```

<img width="1212" alt="Screenshot 2024-11-01 at 12 20 35" src="https://github.com/user-attachments/assets/cef12681-00da-4460-9d25-c445199703a3">

---

```SQL
SELECT *
FROM customer
WHERE first_name LIKE '%er%';
```

<img width="1216" alt="Screenshot 2024-11-01 at 12 21 25" src="https://github.com/user-attachments/assets/a1454357-c5a8-4ea5-aa6c-fc60662e1bb2">

---

```SQL
SELECT *
FROM customer
WHERE first_name LIKE '_her%';
```

<img width="1212" alt="Screenshot 2024-11-01 at 12 22 19" src="https://github.com/user-attachments/assets/8f2a4e2c-44fb-4dd8-b63d-7640e154aa53">

---

```SQL
SELECT *
FROM customer
WHERE
  first_name LIKE 'A%'
  AND last_name NOT LIKE 'B%'
ORDER BY last_name;
```

<img width="1213" alt="Screenshot 2024-11-01 at 12 23 51" src="https://github.com/user-attachments/assets/38191385-0311-4506-90e8-5a5e6c4e852e">

## General Challenges 1

Q1. How many payment transactions were greater than $5.00?

```SQL
SELECT COUNT(amount)
FROM payment
WHERE amount > 5;
```

Q2. How many actors have a first name that starts with the letter P?

```SQL
SELECT COUNT(*)
FROM actor
WHERE first_name LIKE 'P%';
```

Q3. How many unique districts are our customers from?

```SQL
SELECT COUNT(DISTINCT(district))
FROM address;
```

Q4. Retrieve the list of names for those distinct districts from the previous question.

```SQL
SELECT DISTINCT(district)
FROM address;
```

Q5. How many films have a rating of R and a replacement cost between $5 and $15?

```SQL
SELECT COUNT(*)
FROM film
WHERE
  rating='R'
  AND replacement_cost BETWEEN 5 AND 15;
```

Q6. How many films have the word Truman somewhere in the title?

```SQL
SELECT COUNT(*)
FROM film
WHERE title LIKE '%Truman%';
```

## Aggregate Functions

- `AVG()` : returns average value
  - returns a floating point value many decimal places(e.g. 2.342418...)
  - You can use `ROUND()` to specify precision after the decimal.
- `COUNT()` : returns number of values
  - simply returns the number of rows, which means by convention we just use `COUNT(*)`.
- `MAX()` : returns maximum value
- `MIN()` : returns minimum value
- `SUM()` : returns the sum of all values

Aggregate function calls happen only in the `SELECT` clause or the `HAVING` clause.

## GROUP BY

<img width="469" alt="Screenshot 2024-11-01 at 13 58 18" src="https://github.com/user-attachments/assets/d1ed2b5b-5343-4560-aceb-93143af16bb0">

After, `GROUP BY`

<img width="584" alt="Screenshot 2024-11-01 at 13 58 52" src="https://github.com/user-attachments/assets/6b2bf57c-4751-4c0d-a0df-34d015f90af7">

After, applying aggregate functions

<img width="475" alt="Screenshot 2024-11-01 at 13 59 44" src="https://github.com/user-attachments/assets/12b4f69d-397a-4815-baf6-bcd7bbc65b45">

<img width="476" alt="Screenshot 2024-11-01 at 14 01 00" src="https://github.com/user-attachments/assets/e2305be3-2a1f-4858-a848-5d24b8d05770">

<img width="476" alt="Screenshot 2024-11-01 at 14 01 27" src="https://github.com/user-attachments/assets/23cdcdd3-44ee-403b-bd38-aec341b99214">

```SQL
SELECT category_col, AGG(data_col)
FROM table_name
GROUP BY category_col;
```

- `GROUP BY` clause must appear right after a `FROM` or `WHERE` statement.
- In the `SELECT` statement, columns must either have an aggregate function or be in the `GROUP BY` call.
  - `SELECT company, division, SUM(sales) FROM finance_table GROUP BY company, division`
- `WHERE` statements should not refer to the aggregation result, later on we will learn to use `HAVING` to filter on those results.
  - `SELECT company, division, SUM(sales) FROM finance_table WHERE division IN('marketing', 'transport') GROUP BY company, division`
- If you want to sort results based on the aggregate, make sure to reference the entire function
  - `SELECT company, SUM(sales) FROM finance_table GROUP BY company ORDER BY SUM(sales)`

---

```SQL
SELECT customer_id
FROM payment;
```

<img width="161" alt="Screenshot 2024-11-01 at 14 21 24" src="https://github.com/user-attachments/assets/ac1c450c-b608-4108-b809-deb135c4a39f">

---

```SQL
SELECT customer_id
FROM payment
GROUP BY customer_id;
```

<img width="159" alt="Screenshot 2024-11-01 at 14 22 15" src="https://github.com/user-attachments/assets/4fa164ba-995c-4735-8cd8-a6511888f854">

---

```SQL
SELECT customer_id, SUM(amount)
FROM payment
GROUP BY customer_id;
```

<img width="233" alt="Screenshot 2024-11-01 at 14 23 30" src="https://github.com/user-attachments/assets/d1251bef-7e0d-42f9-8e89-f1628b118074">

---

```SQL
SELECT customer_id, COUNT(amount)
FROM payment
GROUP BY customer_id
ORDER BY COUNT(amount) DESC;
```

<img width="237" alt="Screenshot 2024-11-01 at 14 24 47" src="https://github.com/user-attachments/assets/3329cd7c-ec6f-4fbe-8705-66dca8242d77">

---

```SQL
SELECT customer_id, staff_id, SUM(amount)
FROM payment
GROUP BY staff_id, customer_id;
```

<img width="316" alt="Screenshot 2024-11-01 at 14 29 11" src="https://github.com/user-attachments/assets/deeb459f-71fd-429b-9298-ac50abec8b1a">

---

```SQL
SELECT DATE(payment_date)
FROM payment
GROUP BY DATE(payment_date);
```

<img width="144" alt="Screenshot 2024-11-01 at 14 30 25" src="https://github.com/user-attachments/assets/b14d8ec9-5940-4d3d-8a49-483b3033c58a">

---

```SQL
SELECT DATE(payment_date), SUM(amount)
FROM payment
GROUP BY DATE(payment_date)
ORDER BY SUM(amount) DESC;
```

<img width="220" alt="Screenshot 2024-11-01 at 14 37 06" src="https://github.com/user-attachments/assets/97507a85-8f81-48e5-b044-b941a83d1cf2">

### Challlenge

Q1. How many payments did each staff member handle and who gets the bonus?

```SQL
SELECT staff_id, COUNT(amount)
FROM payment
GROUP BY staff_id;
```

Q2. What is the average replacement cost per MPAA rating?

```SQL
SELECT rating, ROUND(AVG(replacement_cost),2)
FROM film
GROUP BY rating;
```

Q3. What are the customer ids of the top 5 customers by total spend?

```SQL
SELECT customer_id, SUM(amount)
FROM payment
GROUP BY customer_id
ORDER BY SUM(amount) DESC
LIMIT 5;
```

## HAVING

- The `HAVING` clause allows us to filter **after** an aggregation has already taken place.
- `HAVING` allows us to use the aggregate result as a filter along with a `GROUP BY`

```SQL
SELECT company, SUM(sales)
FROM finance_table
WHERE company != 'Google'
GROUP BY company
HAVING SUM(sales) > 1000;
```

---

```SQL
SELECT customer_id, SUM(amount)
FROM payment
WHERE customer_id NOT IN (184, 87, 477)
GROUP BY customer_id
HAVING SUM(amount) > 100;
```

<img width="237" alt="Screenshot 2024-11-01 at 15 09 27" src="https://github.com/user-attachments/assets/cebf881b-23d3-4ad2-a03b-36c4da924447">

---

```SQL
SELECT store_id, COUNT(customer_id)
FROM customer
GROUP BY store_id
HAVING COUNT(customer_id) > 300;
```

<img width="215" alt="Screenshot 2024-11-01 at 15 10 43" src="https://github.com/user-attachments/assets/82c2d1a8-6501-4a01-91bc-9b64cecf0f3f">

### Challenge

Q1. What customer_ids are eligible for platinum status?

```SQL
SELECT customer_id, COUNT(*)
FROM payment
GROUP BY customer_id
HAVING COUNT(*) >= 40;
```

Q2. What are the customer ids of customers who have spent more than $100 in payment transactions with our staff_id member 2?

```SQL
SELECT customer_id, SUM(amount)
FROM payment
WHERE staff_id=2
GROUP BY customer_id
HAVING SUM(amount) > 100;
```

## ASSESSMENT TEST 1

Q1. Return the customer IDs of customers who have spent at least $110 with the staff member who has an ID of 2.

```SQL
SELECT customer_id, SUM(amount)
FROM payment
WHERE staff_id=2
GROUP BY customer_id
HAVING SUM(amount) > 110;
```

Q2. How many films begin with the letter J?

```SQL
SELECT COUNT(*)
FROM film
WHERE title LIKE 'J%';
```

Q3. What customer has the highest customer ID number whose name starts with an 'E' and has an address ID lower than 500?

```SQL
SELECT first_name, last_name
FROM customer
WHERE
  first_name LIKE 'E%'
  AND address_id < 500
ORDER BY customer_id DESC
LIMIT 1;
```

## AS

```SQL
SELECT column AS new_name
FROM table_name;
```

- `AS` operator gets executed at the very end of a query, meaning that we can not use the `ALIAS` inside a `WHERE` operator.

---

```SQL
SELECT amount AS rental_price
FROM payment;
```

<img width="167" alt="Screenshot 2024-11-01 at 15 51 08" src="https://github.com/user-attachments/assets/ec2224c6-258a-4933-a415-05ec3bac9d11">

---

```SQL
SELECT customer_id, SUM(amount) AS total_spent
FROM payment
GROUP BY customer_id
HAVING SUM(amount) > 100;
```

## JOIN

- `JOIN` allow us to combine multiple tables together.
- The main reason for the different `JOIN` types is to decide how to deal with information only present in one of the joined tables.

<img width="898" alt="Screenshot 2024-11-01 at 15 57 22" src="https://github.com/user-attachments/assets/6e366b3a-2808-41d1-af86-f7d4e653ef94">

## INNER JOIN

- Table order won't matter in an `INNER JOIN`.
- If you see just `JOIN` without the `INNER`, PostgreSQL will treat it as an `INNER JOIN`.

```SQL
SELECT *
FROM TableA
INNER JOIN TableB
ON TableA.col_match=TableB.col_match;
```

<img width="532" alt="Screenshot 2024-11-01 at 16 06 10" src="https://github.com/user-attachments/assets/fb8fec99-292d-4bea-8986-5c0bf987ccdf">

<img width="892" alt="Screenshot 2024-11-01 at 15 59 40" src="https://github.com/user-attachments/assets/674c95e8-4631-4d72-b974-cfeb359d3bb2">

---

```SQL
SELECT *
FROM Registrations
INNER JOIN Logins
ON Registrations.name=Logins.name;
```

<img width="1486" alt="Screenshot 2024-11-01 at 16 07 21" src="https://github.com/user-attachments/assets/8ae6cd2d-a8d9-4ac5-934f-95f8bc854b3d">

<img width="1477" alt="Screenshot 2024-11-01 at 16 07 59" src="https://github.com/user-attachments/assets/ef4435f9-d580-4aa9-8325-6ecef2f08e7a">

<img width="1478" alt="Screenshot 2024-11-01 at 16 08 21" src="https://github.com/user-attachments/assets/35e9dcca-f12a-43a6-ad34-13980504f6b9">

<img width="1477" alt="Screenshot 2024-11-01 at 16 08 57" src="https://github.com/user-attachments/assets/de203b98-ee42-4f00-b0e0-4972ef527dbf">

---

```SQL
SELECT reg_id, Logins.name, log_id
FROM Registrations
INNER JOIN Logins
ON Registrations.name=Logins.name;
```

<img width="528" alt="Screenshot 2024-11-01 at 16 14 13" src="https://github.com/user-attachments/assets/943f2ee7-2aa1-40b3-9298-f294379fbf74">

## OUTER JOINs

- They will allow us to specify how to deal with values only present in one of the tables being joined.

### FULL OUTER JOIN

```SQL
SELECT *
FROM TableA
FULL OUTER JOIN TableB
ON TableA.col_match=TableB.col_match;
```

<img width="585" alt="Screenshot 2024-11-01 at 16 54 39" src="https://github.com/user-attachments/assets/235be55b-8351-44a0-8ec0-3479ba7637d6">

---

```SQL
SELECT *
FROM Registrations
FULL OUTER JOIN Logins
ON Registrations.name=Logins.name;
```

<img width="1477" alt="Screenshot 2024-11-01 at 16 55 42" src="https://github.com/user-attachments/assets/eb2a2db1-59fa-47d2-bd9c-f1cc60ad3031">

<img width="821" alt="Screenshot 2024-11-01 at 16 56 40" src="https://github.com/user-attachments/assets/8ff03c16-a27b-4775-9cd2-f56eb8d9e8b8">

#### FULL OUTER JOIN with WHERE

```SQL
SELECT *
FROM TableA
FULL OUTER JOIN TableB
ON TableA.col_match=TableB.col_match
WHERE
  TableA.id IS null
  OR TableB.id IS null;
```

<img width="541" alt="Screenshot 2024-11-01 at 16 58 13" src="https://github.com/user-attachments/assets/313e05ad-f39e-4b07-8641-b80e112cf6aa">

---

```SQL
SELECT *
FROM Registrations
FULL OUTER JOIN Logins
ON Registrations.name=Logins.name
WHERE
  Registrations.reg_id IS null
  OR Logins.log_id IS null;
```

<img width="618" alt="Screenshot 2024-11-01 at 16 59 17" src="https://github.com/user-attachments/assets/48882c5f-c1e6-4ab8-be1a-bcd1c541c7bb">

<img width="826" alt="Screenshot 2024-11-01 at 16 59 41" src="https://github.com/user-attachments/assets/3e6fe25b-13fc-4aa5-8fc6-422d1464b85f">

### LEFT OUTER JOIN

- `LEFT OUTER JOIN` results in the set of records that are in the left table, if there is no match with the right table, the results are null.
- Order matters for `LEFT OUTER JOIN`.

```SQL
SELECT *
FROM TableA
LEFT OUTER JOIN TableB
ON TableA.col_match=TableB.col_match;
```

<img width="614" alt="Screenshot 2024-11-01 at 17 04 25" src="https://github.com/user-attachments/assets/482592a3-25ef-4c15-8e90-6e431b87151b">

---

```SQL
SELECT *
FROM Registrations
LEFT OUTER JOIN Logins
ON Registrations.name=Logins.name;
```

<img width="691" alt="Screenshot 2024-11-01 at 17 05 57" src="https://github.com/user-attachments/assets/1939c4e5-6de5-4d1f-90a2-2ac8031b71d3">

<img width="1485" alt="Screenshot 2024-11-01 at 17 06 48" src="https://github.com/user-attachments/assets/0510b532-eb01-402d-a546-8a88851d3d33">

#### LEFT OUTER JOIN with WHERE

```SQL
SELECT *
FROM TableA
LEFT OUTER JOIN TableB
ON TableA.col_match=TableB.col_match
WHERE TableB.id IS null;
```

<img width="604" alt="Screenshot 2024-11-01 at 17 14 21" src="https://github.com/user-attachments/assets/f13ec3db-5bea-48ef-8ff3-5c1e92b9cc04">

---

```SQL
SELECT *
FROM Registrations
LEFT OUTER JOIN Logins
ON Registrations.name=Logins.name
WHERE Logins.log_id IS null;
```

<img width="698" alt="Screenshot 2024-11-01 at 17 15 36" src="https://github.com/user-attachments/assets/80f7f799-9ce7-4aa4-8fb9-a242e67affef">

### RIGHT JOINS

- `RIGHT JOIN` is essentially the same as a `LEFT JOIN`, except the tables are switched.
- This would be the same as switching the table order in a `LEFT OUTER JOIN`.

```SQL
SELECT *
FROM TableA
RIGHT OUTER JOIN TableB
ON TableA.col_match=TableB.col_match;
```

<img width="649" alt="Screenshot 2024-11-01 at 17 18 06" src="https://github.com/user-attachments/assets/3652a430-c8ba-431d-9fc5-cce5b2c58a8e">

```SQL
SELECT *
FROM TableA
RIGHT OUTER JOIN TableB
ON TableA.col_match=TableB.col_match
WHERE TableA.id IS null;
```

<img width="600" alt="Screenshot 2024-11-01 at 17 18 59" src="https://github.com/user-attachments/assets/d9d0314a-615d-410e-ab97-0f9dbe0ce567">

### UNION

- `UNION` operator is used to combine the result-set of two or more `SELECT` statements.
- It basically serves to directly concatenate two results together, essentially "pasting" them together.

```SQL
SELECT column_name
FROM table1
UNION
SELECT column_name
FROM table2;
```

---

<img width="929" alt="Screenshot 2024-11-01 at 17 21 42" src="https://github.com/user-attachments/assets/e832cef9-cfd7-4ab4-bdc2-cf21cd899f8a">

```SQL
SELECT *
FROM Sales2021_Q1
UNION
SELECT *
FROM Sales2021_Q2;
```

<img width="323" alt="Screenshot 2024-11-01 at 17 22 29" src="https://github.com/user-attachments/assets/7d8e9367-8207-4fe7-983e-96f689255553">

## JOIN Challenges

Q1. What are te email of the customers who live in California?

```SQL
SELECT district, email
FROM address
INNER JOIN customer
ON address.address_id=customer.address_id
WHERE district='California';
```

Q2. Get a list of all the movies "Nick Wahlberg" has been in.

```SQL
SELECT title, first_name, last_name
FROM film_actor
INNER JOIN actor
ON film_actor.actor_id=actor.actor_id
INNER JOIN film
ON film_actor.film_id=film.film_id
WHERE
  first_name='Nick'
  AND last_name='Wahlberg';
```

## Timestamps and Extract

- `TIME` : Contains only time
- `DATE` : Contains only date
- `TIMESTAMP` : Contains date and time
- `TIMESTAMPTZ` : Contains date, time, and timezone

### Extract()

```SQL
EXTRACT(YEAR FROM date_col)
```

- Allows you to **extract** or obtain a sub-component of a date value
- `YEAR`
- `MONTH`
- `DAY`
- `WEEK`
- `QUARTER`

### AGE()

```SQL
AGE(date_col)
```

- Calculates and returns the current age given a timestamp

### TO_CHAR()

```SQL
TO_CHAR(date_col, 'mm-dd-yyyy')
```

- General function to convert data types to text
- Useful for timestamp formatting

### Challenge

Q1. During which months did payments occur? Format your answer to return back the full month name.

```SQL
SELECT DISTINCT(TO_CHAR(payment_date, 'MONTH'))
FROM payment;
```

Q2. How many payments occurred on a Monday?

```SQL
SELECT COUNT(*)
FROM payment
WHERE EXTRACT(dow FROM payment_date)=1
```

## Self Join

- can be viewed as a join of two copies of the smae table.
- The table is not actually copied, but SQL performs the command as though it were.
- When using a self join it is necessary to use an alias for the table.

![Screenshot 2024-11-05 at 17 19 28](https://github.com/user-attachments/assets/bfc28555-322b-4b99-b4b9-cabcd65dc2fc)

```SQL
SELECT emp.name, report.name AS rep
FROM employees AS emp
JOIN emplyees AS report ON
emp.emp_id=report.report_id;
```

## Creating Databases and Tables

### CREATE TABLE

```postgresql
CREATE TABLE table_name(
  column_name TYPE column_constraint,
  column_name TYPE column_constraint,
  table_constraint table_constraint
) INHERITS existing_table_name;
```

```postgresql
CREATE TABLE players(
  player_id SERIAL PRIMARY KEY,
  age SMALLINT NOT NULL,
  name VARCHAR(50) UNIQUE NOT NULL,
  created_on TIMESTAMP NOT NULL
);

CREATE TABLE players_job(
  user_id INTEGER REFERENCES players(player_id),
  hire_date TIMESTAMP NOT NULL
);
```

### INSERT

- `INSERT` allows you to add in rows to a table.

```postgresql
INSERT INTO table_name(column1, column2, ...)
VALUES
  (value1, value2, ...),
  (value1, value2, ...),
```

```postgresql
INSERT INTO account(username, password, email, create_on)
VALUES
  ('Jose', 'password', 'jose@mail.com',CURRENT_TIMESTAMP)
  ('Jose2', 'password2', 'jose2@mail.com',CURRENT_TIMESTAMP)
```

### UPDATE

- `UPDATE` allows for the changing of values of the columns in a table.

```postgresql
UPDATE table_name
SET column1=value1, column2=value2, ...
WHERE condition;
```

```postgresql
UPDATE account
SET last_login=CURRENT_TIMESTAMP
WHERE last_login IS NULL;

UPDATE TableA
SET original_col=TableB.new_col
FROM TableB
WHERE tableA.id=TableB.id

UPDATE account
SET last_login=created_on
RETURNING account_id,last_login;
```

### DELETE

```postgresql
DELETE FROM table_name
WHERE condition;

DELETE FROM tableA
USING tableB
WHERE tableA.id=TableB.id;

DELETE FROM table_name;
```

### ALTER TABLE

- `ALTER` allows for changes to an existing table structure, such as
  - Adding, dropping, or renaming columns
  - Changing a column's data type
  - Set DEFAULT values for a column
  - Add CHECK constraints
  - Rename table

```postgresql
ALTER TABLE table_name action;

ALTER TABLE table_name
ADD COLUMN new_col TYPE;

ALTER TABLE table_name
DROP COLUMN col_name;

ALTER TABLE table_name
ALTER COLUMN col_name
SET DEFAULT value;
```

### DROP

- `DROP` allows for the complete removal of a column in a table.

```postgresql
ALTER TABLE table_name
DROP COLUMN col_name;

ALTER TABLE table_name
DROP COLUMN col_name CASCADE;

ALTER TABLE table_name
DROP COLUMN IF EXISTS col_name;

ALTER TABLE table_name
DROP COLUMN col_one,
DROP COLUMN col_two;
```

### CHECK

- `CHECK` allows us to create more customized constraints that adhere to a certain condition.

```postgresql
CREATE TABLE example(
  ex_id SERIAL PRIMARY KEY,
  age SMALLINT CHECK (age > 21),
  parent_age SMALLINT CHECK(
    parent_age > age
  )
);
```

### Challenge

```postgresql
CREATE TABLE students(
  student_id serial PRIMARY KEY,
  first_name VARCHAR(45) NOT NULL,
  last_name VARCHAR(45) NOT NULL,
  homeroom_number integer,
  phone VARCHAR(20) UNIQUE NOT NULL,
  email VARCHAR(115) UNIQUE,
  grad_year integer
);
```

```postgresql
CREATE TABLE teachers(
  teacher_id serial PRIMARY KEY,
  first_name VARCHAR(45) NOT NULL,
  last_name VARCHAR(45) NOT NULL,
  homeroom_number integer,
  department VARCHAR(45),
  email VARCHAR(20) UNIQUE,
  phone VARCHAR(20) UNIQUE
);
```

## Conditional Expressions and Operators

### CASE

- use `CASE` to only execute SQL code when certain conditions are met.

```postgresql
CASE
  WHEN condition1 THEN result1
  WHEN condition2 THEN result2
  ELSE some_other_result
END
```

![Screenshot 2024-11-06 at 17 33 31](https://github.com/user-attachments/assets/01bd760d-37d5-46cc-b3f4-82c8688432f1)

```postgresql
SELECT a
CASE
  WHEN a=1 THEN 'one'
  WHEN a=2 THEN 'two'
  ELSE 'other'
END
FROM test;
```

![Screenshot 2024-11-06 at 17 33 54](https://github.com/user-attachments/assets/fd7b463e-e425-4d03-8534-7a369ed9a88e)

```postgresql
CASE expression
  WHEN value1 THEN result1
  WHEN value2 THEN result2
  ELSE some_other_result
END
```

```postgresql
SELECT a
CASE a
  WHEN 1 THEN 'one'
  WHEN 2 THEN 'two'
  ELSE 'other'
END
FROM test;
```

![Screenshot 2024-11-06 at 17 33 54](https://github.com/user-attachments/assets/fd7b463e-e425-4d03-8534-7a369ed9a88e)

#### Chanllenge

Q1. We want to know and compare the various amounts of films we have per movie rating.

```postgresql
SELECT
  SUM(
    CASE rating
      WHEN 'R' THEN 1
      ELSE 0
    END
  ) AS r,
  SUM(
    CASE rating
      WHEN 'PG' THEN 1
      ELSE 0
    END
  ) AS pg,
  SUM(
    CASE rating
      WHEN 'PG-13' THEN 1
      ELSE 0
    END
  ) AS pg13,
FROM film;
```

### COALESCE

- `COALESCE` function returns the first argument that is not null.
- If all arguments are null, the `COALESCE` function will return null.
- useful when querying a table that contains null values and substituting it with another value.

```postgresql
COALESCE(arg_1, arg_2, ..., arg_n);
```

```postgresql
SELECT COALESCE(1, 2) // 1

SELECT COALESCE(NULL, 2, 3) // 2
```

![Screenshot 2024-11-06 at 18 15 41](https://github.com/user-attachments/assets/30876763-fbdd-4d5b-a5f7-f56bab07cdcf)

Q. What is the final price?

A1. Doesn't work for item B, should be 300.

```postgresql
SELECT
  item,
  (price - discount) AS final
FROM table_name;
```

![Screenshot 2024-11-06 at 18 17 22](https://github.com/user-attachments/assets/ac1dfcb2-334d-4f92-9640-c7f41d4f0835)

A2. Work for item B!

```postgresql
SELECT
  item,
  (price - COALESCE(discount, 0)) AS final
FROM table_name;
```

### CAST

- `CAST` operator let you convert from one data type into another.

```postgresql
SELECT CAST('5' AS INTEGER)

SELECT '5'::INTEGER
```

### NULLIF

- `NULLIF` function takes in 2 inputs and returns NULL if both are equal, otherwise it returns the first argument passed.

```postgresql
NULLIF(arg1, arg2);

NULLIF(10,10); // NULL

NULLIF(10,12); // 10
```

### VIEWS

![Screenshot 2024-11-07 at 8 45 11](https://github.com/user-attachments/assets/710edc34-7c3c-4eb3-bb2c-4cd637fd5602)

### Import and Export

- allows us to import data from a ".csv" file to an already existing table.
- You MUST provide the 100% correct file path to your outside file, otherwise the Import command will fail to find the file.
- Import command DOES NOT create a table for you. It assumes a table is already created.

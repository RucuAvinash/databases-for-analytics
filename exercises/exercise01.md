# Exercise 01: World Database SQL Practice

- Name: Rucmanidevi Sethu
- Course: Database for Analytics
- Module: 1
- Database Used: World Database

---

## Instructions

- Answer each question below.
- All SQL commands **must be executed** against the World database.
- For each SQL command:
  - Include the SQL in a fenced code block
  - Include a **screenshot** showing the command and results
- Store screenshots in the `screenshots/` folder and embed them below each answer.

---

## Question 1

**Compare and contrast the data types used for:**
- `country.Population`
- `country.LifeExpectancy`

Why were these data types selected?

### Answer
Population is stored as INT datatype. Population counts are always stored as whole nunumbers and it does not make sense to store them as decimal.Storing as INT improves processing time.
LifeExpectancy is stored as decimal(3,1) which allows values from 0.0 to 99.9 which is applicable to most of the countries.

### Screenshot
![alt text](image-1.png)

## Question 2

**What is the data type of `country.IndepYear`?**
Why do you think this data type was selected?

### Answer
'country.IndepYear' is stored as smallInt.
this datatype uses only 2 bytes of storage unlike INT datatypes which uses 4 bytes of storage. This datatype also prevent non-numerical and fractional values.

### Screenshot

```sql
DESCRIBE country;
```

![Q2 Screenshot](screenshots/q2_indepyear.png)

![alt text](image-2.png)

---

## Question 3

**Make a case for a different data type for `country.IndepYear`.**
Explain why your proposed data type might be better in some situations.

### Answer
'country.IndepYear' can also be stored in INT format , which supports larger range of data to be stored.

## Question 4

Write a SQL command to **list the names of all cities in alphabetical order**.

### SQL

```sql
SELECT Name
FROM city
ORDER BY Name;
```

### Screenshot

![alt text](image-3.png)
---

## Question 5

Write a SQL command to **list all forms of government from the `country` table**, showing **each only once**, sorted alphabetically.

### SQL

```sql
SELECT DISTINCT GovernmentForm
FROM country
ORDER BY GovernmentForm;
```

### Screenshot

![alt text](image-4.png)

---

## Question 6

Write a SQL command to **list all countries in the `Oceania` continent**.

### SQL

```sql
SELECT Name
FROM country
WHERE Continent = 'Oceania';
```

### Screenshot

![alt text](image-5.png)
---

## Question 7

Write a SQL command to **list the names and country code of all cities**.

### SQL

```sql
SELECT Name, CountryCode
FROM city;

```

### Screenshot

![alt text](image-6.png)

---

## Question 8

Write a SQL command to **update the city named `"Nashville-Davidson"` to `"Nashville"`**.

### SQL

```sql
UPDATE city
SET Name = 'Nashville'
WHERE Name = 'Nashville-Davidson';
```

### Screenshot

![alt text](image-7.png)

---

## Question 9

Write a SQL command to **insert a new country named `"Narnia"`** with a country code of `"NAR"`.
Use reasonable values for the remaining columns.

### SQL

```sql
INSERT INTO country (Code, Name, Continent, Region, Population)
VALUES ('NAR', 'Narnia', 'Europe', 'Fantasy', 1000000);
```

### Screenshot

![alt text](image-8.png)

---

## Question 10

Write a SQL command to **delete the country with the country code `"NAR"`**.

### SQL

```sql
DELETE FROM country
WHERE Code = 'NAR';
```

### Screenshot

![alt text](image-9.png)

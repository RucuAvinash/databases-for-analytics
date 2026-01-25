# Exercise 03: MongoDB – Document Queries and Analysis

- Name: Rucmanidevi Sethu
- Course: Database for Analytics
- Module: 3
- Database Used: MongoDB
- Dataset: `restaurants-json.json`

---

## Instructions

- Import the provided `restaurants-json.json` file into MongoDB.
- All commands must be **executed by you** in the MongoDB shell or MongoDB Compass.
- For each query:
  - Include the MongoDB command in a fenced code block
  - Include a **screenshot** showing the command and its result
- Store screenshots in the `screenshots/` folder and embed them below each answer.

---

## Question 1

When importing the documents from `restaurants-json.json`, **how many documents were imported into your collection**?

### Answer
25358

### Screenshot
_![alt text](image-25.png)

```javascript
db["restaurants"].countDocuments()
```

![Q1 Screenshot](screenshots/q1_document_count.png)

---

## Question 2

Before writing queries on the data, **what command do you use to set the MongoDB shell to operate on the `44661` database**?

### MongoDB Command

```javascript
use 44661
```

### Screenshot

![alt text](image-26.png)

---

## Question 3

Using your `restaurants` collection in the `44661` database, write the MongoDB query needed to **locate all documents in the `"Queens"` borough**.

### MongoDB Query

```javascript
db["restaurants"].find({borough:'Queens'})
```

### Screenshot

![alt text](image-27.png)

---

## Question 4

Using your `restaurants` collection in the `44661` database, write the MongoDB query needed to **find the number of restaurants in the `"Queens"` borough**.

### MongoDB Query

```javascript
db["restaurants"].countDocuments({borough:'Queens'})
```

### Screenshot

![alt text](image-28.png)

---

## Question 5

Using your `restaurants` collection in the `44661` database, write the MongoDB query needed to **find the number of restaurants in the `"Queens"` borough whose cuisine is `"Hamburgers"`**.

### MongoDB Query

```javascript
db["restaurants"].countDocuments({borough:'Queens',cuisine:'Hamburgers'})
```

### Screenshot

![alt text](image-29.png)

---

## Question 6

Using your `restaurants` collection in the `44661` database, write the MongoDB query needed to **find the number of restaurants in Zipcode `10460`**.

*Hint: Look up how to query **embedded documents**.*

### MongoDB Query

```javascript
db["restaurants"].countDocuments({'address.zipcode':'10460'})
```

### Screenshot

![alt text](image-30.png)

---

## Question 7

Using your `restaurants` collection in the `44661` database, write the MongoDB query needed to **display only the names of restaurants in Zipcode `10460`**.

*Hint: Look up how to **project fields** in MongoDB.*

Your output should resemble:

```
{ name: "Wild Asia" }
{ name: "Terrace Cafe" }
{ name: "African Terrace" }
{ name: "Cool Zone" }
{ name: "Beaver Pond" }
...
```

### MongoDB Query

```javascript
db["restaurants"].find({'address.zipcode':'10460'},{'name':1,'_id':0})
```

### Screenshot

![alt text](image-31.png)

---

## Question 8

Using your `restaurants` collection in the `44661` database, write the MongoDB query needed to **display only the names of restaurants whose name contains `"IHOP"`**, ignoring case.

Your results should include:
- `"Ihop"`
- `"Ihop Restaurant"`

### MongoDB Query

```javascript
db["restaurants"].find({name: {$regex:"IHOP",$options:"i"}},
  {'name':1, '_id':0}
)
```

### Screenshot

![alt text](image-32.png)

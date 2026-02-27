# 🇮🇳 Indian States REST API

Live API: https://indian-states-rest-api.onrender.com/states 
Postman Documentation: https://documenter.getpostman.com/view/50871260/2sBXcHhyWd  

---

## 📌 Objective

This project implements a complete REST API using **Node.js + Express.js** to manage statistical data of Indian states using an in-memory JSON array.

The API demonstrates:

- REST architecture principles  
- Correct HTTP method usage  
- Dynamic routing  
- Array data manipulation  
- Proper status codes  
- PUT vs PATCH semantics  
- Resource deletion logic  

⚠️ No database, authentication, or external validation libraries are used.  
All operations modify the in-memory array.

---

## 🗂 Data Structure

Each state follows this structure:

```json
{
  "id": 1,
  "name": "Gujarat",
  "population": 63872399,
  "literacyRate": 78.03,
  "annualBudget": 243965,
  "gdp": 21000000
}
```

---

## 🚀 Setup Instructions

```bash
git clone https://github.com/Ammar-Meman/indian-states-rest-api.git
cd indian-states-rest-api
npm install
node index.js
```

Server runs on:

```
http://localhost:3000
```

---

# 📡 API Routes

## 🟢 GET Routes

### GET /states
Return all states  
**200 OK**

---

### GET /states/:id
Return state by ID  

**200 OK**
```json
{ state object }
```

**404**
```json
{ "message": "State not found" }
```

---

### GET /states/highest-gdp
Return state with highest GDP  

**200 OK**
```json
{ state object }
```

---

# 🟡 POST Route

### POST /states
Add new state  

**Request**
```json
{
  "name": "Haryana",
  "population": 25351462,
  "literacyRate": 75.55,
  "annualBudget": 180000,
  "gdp": 10000000
}
```

**201 Created**
```json
{ created state }
```

---

# 🔵 PUT Routes

### PUT /states/:id
Replace full state (except id)

**200 OK**

---

### PUT /states/:id/budget
Replace annualBudget

```json
{ "annualBudget": 260000 }
```

---

### PUT /states/:id/population
Replace population

```json
{ "population": 70000000 }
```

---

# 🟣 PATCH Routes

### PATCH /states/:id/literacy
Update literacyRate

```json
{ "literacyRate": 82 }
```

---

### PATCH /states/:id/gdp
Update GDP

```json
{ "gdp": 20000000 }
```

---

### PATCH /states/:id
Partial update (any fields)

```json
{ "annualBudget": 280000 }
```

---

# 🔴 DELETE Routes

### DELETE /states/:id
Delete by ID  

**204 No Content**

---

### DELETE /states/name/:stateName
Delete by name (case-insensitive)

**204 No Content**

---

### DELETE /states/low-literacy/:percentage
Delete states below literacy threshold  

**200 OK**
```json
{ "deletedCount": 2 }
```

---

# 🧰 Tech Stack

- Node.js  
- Express.js  
- CORS  
- In-memory JSON  

---

# 🌐 Deployment

Render:  
https://indian-states-rest-api.onrender.com/states  

---

# 📚 Postman Documentation

https://documenter.getpostman.com/view/50871260/2sBXcHhyWd  

---

# 👨‍💻 Author

Ammar Meman  
# Quantity Measurement Web App

## Overview

This is a simple web application built using **Vanilla JavaScript (ES6+)** and **JSON Server**.
It allows users to perform:

* Unit conversions
* Value comparisons
* Arithmetic operations on measurements

The frontend (HTML + CSS) is already provided. You need to implement the logic and data handling.

---

## Tech Stack

* JavaScript (ES6+)
* JSON Server (for backend simulation)
* HTML, CSS (pre-built UI)

---

## Project Structure

```
project/
│
├── index.html        # Provided UI
├── style.css         # Provided styling
├── db.json           # Database (you create this)
│
└── js/
    ├── api.js        # API calls (fetch)
    ├── conversion.js # Calculation logic
    ├── ui.js         # DOM updates
    └── app.js        # Main app logic
```

---

## Setup Instructions

1. Install JSON Server globally:

```
npm install -g json-server
```

2. Create `db.json` in the root folder.

3. Start the server:

```
json-server --watch db.json --port 3000
```

4. Open `index.html` in your browser.

---

## Database Structure (db.json)

```json
{
  "units": [
    { "id": 1, "type": "Length", "label": "Meter", "symbol": "m" }
  ],
  "conversions": [
    { "id": 1, "from": "km", "to": "m", "factor": 1000, "formula": null }
  ],
  "history": []
}
```

---

## Features

### 1. Conversion

* Converts values between units
* Uses factor or formula

### 2. Comparison

* Compares two values
* Returns GREATER / LESS / EQUAL

### 3. Arithmetic

* Performs +, −, ×, ÷
* Works after unit normalization

### 4. History

* Stores all calculations
* Displays latest first

---

## How It Works

* `api.js` → Handles all server calls
* `conversion.js` → Performs calculations
* `ui.js` → Updates UI elements
* `app.js` → Controls app flow and state

---

## Key Concepts

* Uses `fetch()` for API calls
* Uses a shared `state` object
* All calculations are rounded to 6 decimal places
* History is saved after every successful operation

---

## Notes

* JSON Server returns arrays even for single results
* Always check `res.ok` before parsing response
* Do not run JS before `DOMContentLoaded`
* Handle errors gracefully (show message, don’t break app)

---

## Example Commands

Run server:

```
json-server --watch db.json --port 3000
```

API endpoints:

```
GET  /units
GET  /conversions
GET  /history
POST /history
```

---

## Goal

Build the full working logic for:

* Fetching data
* Performing calculations
* Updating UI
* Saving history

---

## Author

Trainee Implementation

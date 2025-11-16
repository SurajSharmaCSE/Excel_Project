# 📊 Excel Clone — Web-Based Spreadsheet
A lightweight **Excel-like spreadsheet application** built using **HTML, CSS, and JavaScript**. This project recreates core spreadsheet functionality such as cell formatting, formulas, sheet handling, and more — all in the browser.

---

## 🚀 Features
### ✔️ 1. Cell Formatting
- Bold / Italic / Underline
- Font size, font family
- Text alignment (left, center, right)
- Text color and cell background color

### ✔️ 2. Multi-Sheet Support
- Create new sheets
- Switch between sheets
- Independent data for each sheet

### ✔️ 3. Formula Support
- Supports formulas like:
  ```
  =A1 + B2
  =A1 - B1
  =A1 * 5
  =10 / B2
  ```
- Auto-updates all dependent cells when formula cells change
- Cycle detection to prevent circular references

### ✔️ 4. Storage Engine
- Uses a **2D matrix** to store formatting and formula data
- `graphComponentMatrix` tracks dependencies between cells
- Detects cycles before updating values

---

## 📁 Project Structure
```
Excel-Clone/
│── index.html
│── style.css
│── script.js
│── grid.js
│── cell-properties.js
│── formula.js
│── cycleValidation.js
│── dependencyGraph.js
│── README.md
```

---

## 🛠️ How It Works
### 🔹 1. Grid Generation
A dynamic grid of 100 rows × 26 columns (A–Z) is generated.

### 🔹 2. Cell Storage Model
Each cell stores:
```json
{
  "bold": false,
  "italic": false,
  "underline": false,
  "alignment": "left",
  "fontSize": "14",
  "fontFamily": "Arial",
  "color": "#000000",
  "bgColor": "#ffffff",
  "formula": "",
  "value": ""
}
```

### 🔹 3. Formula Engine
- Parses formulas into tokens (A1, B2, numbers, operators)
- Replaces cell references with actual values
- Evaluates the expression using JS `eval()` (sanitized)

### 🔹 4. Cycle Detection
Prevents infinite loops:
- Builds dependency graph
- Runs DFS to check for cycles
- Alerts user if cycle found

---

## ▶️ Run the Project
Just open the `index.html` file in any browser.
No server required.

---

## 📸 Screenshots (optional section)
Add images here if needed.

---

## ✨ Future Enhancements
- Save/Load sheets (localStorage / backend)
- Drag & fill cells
- CSV import/export
- Collaborative editing

---

## 🌐 Live Demo
Add your GitHub Pages or hosted link here:
```
https://your-username.github.io/your-repo/
```

---

## 📜 License
Open-source. Use freely for learning and experimentation.

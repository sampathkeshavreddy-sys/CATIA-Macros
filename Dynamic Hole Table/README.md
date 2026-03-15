# Dynamic Hole Table — CATIA Macro

> Automatically extracts hole data from a CATPart and generates or updates a formatted hole table in a CATDrawing — including serial number annotations placed directly on the drawing view.

---

## ✨ What It Does

This macro eliminates the manual effort of creating and maintaining hole tables in CATIA drawings. It works in **two stages** — run it once in the part, once in the drawing.

| Stage | Document | Action |
|-------|----------|--------|
| 1 | CATPart | Extracts all hole positions & diameters → exports to CSV |
| 2 | CATDrawing | Creates or updates the hole table from CSV + places serial number annotations on the view |

---

## 🎯 Key Features

- **Auto-detects document type** — no need to choose a mode; just run the macro in the active document
- **Reference axis system support** — coordinates can be extracted relative to a custom axis system for accurate positioning
- **Smart table handling** — creates a new table if none exists; updates columns 1–5 if a table is already present
- **Editable columns** — columns 6 (Tolerance) and 7 (Remarks) are left untouched so you can fill them manually
- **Serial number annotations** — places numbered text labels directly at each hole location on the selected drawing view
- **Auto-cleanup** — removes old annotations before placing new ones to prevent duplicates

---

## 📋 Table Format

| S.No | X | Y | Z | Hole Diameter | Tolerance | Remarks |
|------|---|---|---|---------------|-----------|---------|
| 1 | 25.000 | 40.000 | 0.000 | Ø8.0 | *(editable)* | *(editable)* |
| 2 | 60.000 | 40.000 | 0.000 | Ø8.0 | *(editable)* | *(editable)* |
| ... | | | | | | |

---

## 🚀 How to Use

### Step 1 — Run in CATPart
1. Open your CATPart in CATIA
2. Run the macro
3. Enter your reference axis system name when prompted (default: `Axis System.1`)
4. The macro exports hole data to a CSV file
5. A confirmation message will tell you how many holes were found

### Step 2 — Run in CATDrawing
1. Switch to your CATDrawing document
2. Run the macro again
3. The hole table is created or updated automatically
4. You will be asked if you want to place serial number annotations on the drawing
5. If yes, select the view number from the list shown

---

## ⚙️ Requirements

- CATIA V5 (tested on R20 and above)
- Drafting workbench (for drawing stage)
- Part Design workbench with standard **Hole** features (not pockets or cuts)
- Macro must be run separately in CATPart and CATDrawing

## ⚠️ Limitations

- Works with **Hole** features only — custom cutouts or pad removals are not detected
- Serial number annotations use the coordinate system of the CSV directly; view scale is not applied automatically
- CSV file path is currently hardcoded — update it to match your local directory before use
> ⚠️ **Before sharing or running:** Update the CSV path in the macro to your own folder location.

---

## 📁 File Structure

```
Dynamic_Hole_Table/
├── Dynamic_Hole_Table.CATScript    # Macro source (available in private repo)
├── README.md
└── demo/
    └── demo.gif                    # See it in action below
```

---

## 🎬 Demo

*(Coming soon — screen recording of the macro in action)*

---

## 🔒 Source Code

The full source code is available in the **private repository**. To request access, please reach out via [GitHub Issues](../../issues) or contact directly.

---

## 👤 Author

**Sampath**
CATIA Macro Developer

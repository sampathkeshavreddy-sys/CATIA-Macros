# CATIA Macros — by Sampath

A collection of CATIA V5 automation macros built to simplify repetitive engineering tasks in Part Design, Assembly, and Drafting workbenches.

> 💡 These macros are showcased here for demonstration purposes. Full source code is available in the private repository — feel free to reach out via [Issues](../../issues) to request access.

---

## 📦 Macro Library

| # | Macro | Purpose | Workbench |
|---|-------|---------|-----------|
| 1 | [Dynamic Hole Table](./Dynamic_Hole_Table/) | Extracts hole data from CATPart and creates/updates a hole table in CATDrawing with serial number annotations | Part Design / Drafting |
| 2 | [SwapMaster](./SwapMaster/) | Replace selected components in a product tree with any loaded CATPart using a searchable paginated browser | Assembly Design |
| 3 | [3D_QChecker](./3D_QChecker/) | Read-only quality checker — scans the full assembly tree for broken constraints, hidden items, and instance name errors | Assembly Design |
| 4 | 2D_QChecker *(in progress)* | Quality checker for CATDrawing files — validates drawing views, annotations, and standards compliance | Drafting |
| 5 | *(coming soon)* | | |
| 5 | *(coming soon)* | | |
| 6 | *(coming soon)* | | |
| 7 | *(coming soon)* | | |
| 8 | *(coming soon)* | | |
| 9 | *(coming soon)* | | |

---

## 🔍 3D_QChecker

A read-only quality checker for `CATProduct` and `CATPart` assemblies. Traverses the full assembly tree and generates a timestamped report in Notepad. **Never modifies the model.**

### Checks performed

| # | Check | What it detects |
|---|-------|-----------------|
| 1 | **Broken Constraints** | Constraints that are broken, not solved, out of date, in error, or have silent broken dimension references |
| 2 | **Hidden Items** | Components hidden at assembly level · Bodies hidden in No-Show space · Individual features hidden inside bodies |
| 3 | **Instance Name Format** | Component instance names that do not follow the `PartNumber.Index` convention |
| 4 | **Deactivated Components** *(in progress)* | Components that are deactivated in the assembly tree |

### Example output

```
============================================================
  3D_QChecker -- Quality Check Report
  Generated : 2025-03-15 14:30:22
  Document  : C:\Projects\MyAssembly.CATProduct
============================================================

======== Broken Constraints ========
  Assembly > SubAsm.1: Constraint 'Coincidence.3' - Broken / Not Solved

======== Hidden Components / Bodies / Features ========
  Assembly > Part.1: Body 'PartBody' is hidden
  Assembly > Part.1: Feature 'Pad.1' in Body 'PartBody' is hidden

======== Instance Name Errors ========
  SHAFT.A: Index 'A' is not numeric (expected: SHAFT.<number>)

========================================
Total issues found : 3
  Broken Constraints  : 1
  Hidden Items        : 2
  Instance Name Errs  : 1
========================================
```

### Roadmap

- [ ] Deactivated component detection *(in development)*
- [ ] Empty Part Number / Part Name check
- [ ] Mass property validation
- [ ] Publication check

---

## ⚙️ Requirements

- CATIA V5 (R20 and above recommended)
- Macros are written in **VBScript** (`.CATScript`)
- No third-party libraries required

## ▶️ How to Run a Macro in CATIA

1. In CATIA, go to **Tools → Macros → Macros...**
2. Click **Select** and browse to the `.CATScript` file
3. Click **Run**

---

## 📬 Contact

For source code access or collaboration, open an [Issue](../../issues) on this repository.

---

## 👤 Author

**Sampath Keshavreddy**  
CATIA Macro Developer

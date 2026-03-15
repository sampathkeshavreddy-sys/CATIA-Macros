# SwapMaster — CATIA Component Replacement Macro

> Quickly replace one or more components in a CATIA product tree with any other loaded CATPart — with a smart paginated browser and part number search built in.

---

## ✨ What It Does

SwapMaster lets you select components in a CATProduct and swap them out for a different CATPart — all without manually navigating menus. It scans all currently loaded parts, presents them in a clean browsable list, and performs the replacement recursively through the entire product tree.

---

## 🎯 Key Features

- **Multi-select replacement** — select one or more components in the product tree before running; all are replaced in one go
- **Paginated part browser** — all loaded CATParts are displayed in pages of 20 for easy navigation
- **Part number search** — search by full or partial part number instead of scrolling
- **Recursive replacement** — finds and replaces matching components at every level of nested assemblies
- **Confirmation prompts** — always asks before replacing so there are no accidental swaps
- **Smart part number display** — shows part number alongside filename for easier identification

---

## 🚀 How to Use

1. Open your **CATProduct** and load the replacement CATPart(s) in CATIA
2. **Select** the component(s) you want to replace in the product tree
3. Run the macro
4. Browse or search for the replacement part from the list
5. Confirm your selection — the macro replaces all selected components instantly

---

## 🔍 Part Browser Commands

| Command | Action |
|---------|--------|
| Enter a number | Select that part |
| `N` | Next page |
| `P` | Previous page |
| `F` / `L` | Jump to first / last page |
| `J##` | Jump to a specific page number (e.g. `J5`) |
| `S` | Search by part number |
| `C` | Cancel |

---

## ⚙️ Requirements

- CATIA V5 (tested on R20 and above)
- Assembly Design workbench (CATProduct must be active)
- Replacement CATPart must already be **open/loaded** in CATIA before running the macro

## ⚠️ Limitations

- Only works with **loaded** CATParts — parts not currently open in CATIA will not appear in the list
- Replacement is done by file path — ensure the replacement part is saved before running
- Does not support replacing CATProducts (sub-assemblies) — only CATPart components

---

## 📁 File Structure

```
SwapMaster/
├── SwapMaster.CATScript        # Macro source (available in private repo)
├── README.md
└── demo/
    └── demo.gif                # See it in action below
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

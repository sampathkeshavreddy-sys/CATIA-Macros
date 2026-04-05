# 3D_QChecker

A read-only quality checker macro for **CATIA V5** assemblies and parts.  
Run it on any open `CATProduct` or `CATPart` — it walks the full assembly tree, finds issues, and writes a timestamped report to Notepad. **The model is never modified.**

---

## Checks Performed

| # | Check | What it detects |
|---|-------|-----------------|
| 1 | **Broken Constraints** | Constraints that are broken, not solved, out of date, in error, or have silent broken dimension references |
| 2 | **Hidden Items** | Components hidden at assembly level · Bodies hidden in No-Show space · Individual features hidden inside bodies |
| 3 | **Instance Name Format** | Component instance names that do not follow the `PartNumber.Index` convention |
| 4 | **Deactivated Components** *(in progress)* | Components that are deactivated in the assembly tree |

---

## Requirements

- CATIA V5 R20 or later (developed and tested on **V5 R28**)
- Windows (report is written to `%TEMP%` and opened in Notepad)
- No add-ins or external libraries required

---

## How to Run

1. Open your `CATProduct` or `CATPart` in CATIA
2. Make sure all referenced `CATPart` files are also open in the session *(required for hidden body/feature detection)*
3. In CATIA go to **Tools → Macro → Macros...**
4. Click **Select** and browse to `3D_QChecker.CATScript`
5. Click **Run**
6. The report opens automatically in Notepad when complete

> **Tip:** You can add the macro to a CATIA toolbar for one-click access via **Tools → Customize → Toolbars**.

---

## Output

A plain-text report is saved to your Windows `%TEMP%` folder with a unique timestamp so previous reports are never overwritten:

```
%TEMP%\3D_QChecker_Report_YYYYMMDD_HHMMSS.txt
```

**Example report:**

```
============================================================
  3D_QChecker -- Quality Check Report
  Generated : 2025-03-15 14:30:22
  Document  : C:\Projects\MyAssembly.CATProduct
============================================================

======== Broken Constraints ========
  Assembly > SubAsm.1: Constraint 'Coincidence.3' - Broken / Not Solved
  Assembly > Part.1:   Constraint 'Offset.1' - Not Up-To-Date

======== Hidden Components / Bodies / Features ========
  Assembly > SubAsm.1 > Part.2: Component is hidden in assembly
  Assembly > Part.1: Body 'PartBody' is hidden
  Assembly > Part.1: Feature 'Pad.1' in Body 'PartBody' is hidden

======== Instance Name Errors ========
  SHAFT.A: Index 'A' is not numeric (expected: SHAFT.<number>)

========================================
Total issues found : 4
  Broken Constraints  : 2
  Hidden Items        : 2
  Instance Name Errs  : 1
========================================
```

---

## Notes

- **Deduplication** — hidden body checks are performed only once per unique Part Number. If the same part appears multiple times in the assembly, only the first occurrence is inspected.
- **Result array limit** — each check category stores up to 5 000 issues. Assemblies larger than this will truncate silently.

---

## Roadmap

This macro is actively being improved. Planned additions:

- [ ] **Deactivated component detection** — flag components that are deactivated in the assembly tree *(currently in development)*
- [ ] **Empty Part Number / Part Name check** — detect nodes where Part Number or instance Name is blank
- [ ] **Mass property validation** — verify that parts have an assigned material and non-zero computed mass
- [ ] **Publication check** — detect parts that define no publications where publications are expected

---

## Source Code

The source code for this macro is not publicly hosted at this time.

If you are interested in using or collaborating on this macro, feel free to reach out:

**Contact:** [Open an issue](../../issues) or connect via GitHub to request access.

---

## License

MIT License — free to use, modify, and distribute with permission from the author.

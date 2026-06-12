# Foundry Works Files — Naming Convention

## Folder structure

```
Foundry Works Files/
├── NAMING.md                       ← this file
├── Stock/                          ← cross-project reusable parts (PT codes)
│   ├── PT002_GameStone.stl
│   ├── Typefaces/
│   └── ...
├── SW001_Pyramid_2P/               ← game variant folder
│   ├── B6/                         ← version folder (current working version)
│   │   ├── SW001A_Bottom_B6.stl
│   │   ├── SW001B_TopExtension_B6.stl
│   │   └── SW001C_Top_B3.stl
│   └── .gitkeep
└── ...
└── Game Rules/                     ← PDF rulebooks (one per game, shared across 2P/4P)
    ├── SW001_Pyramid_Rules.md
    └── ...
```

---

## Part code format

```
{PRODUCT_CODE}_{DescriptiveName}_{Version}.stl
```

| Segment | Example | Meaning |
|---|---|---|
| Product code | `SW001A` | Game variant (SW001) + part letter (A) |
| Descriptive name | `Bottom` | Short human-readable part name |
| Version | `B6` | Stability tier + revision number |

**Part letters** (A, B, C …) follow the order defined in the Foundry site's structural parts list for that variant. A = base/widest, ascending upward.

**Version tiers:**

| Letter | Meaning | Notes |
|---|---|---|
| `C` | Prototype | Face — testing shape, fit, tolerances |
| `B` | Sellable | Still changing — functional but iterating |
| `A` | Stable | Not changing for years |

The number after the letter is the revision within that tier (C1 → C2 → C3, then jumps to B1 when promoted). A file can carry an older version than its parent folder — e.g. `SW028D_TopRoof_C3.stl` inside a `C5/` folder means the roof was last updated at C3 and hasn't changed since.

---

## Stock parts (PT codes)

Reusable across games. No version suffix unless the geometry is revised.

```
PT001_Magnet.stl
PT002_GameStone.stl
PT003_Dice_W.stl   ← variant suffix after underscore when needed
PT005_MagnetStone.stl
```

---

## Rulebooks

PDF rulebooks live in `Game Rules/`. Each game shares one rulebook across 2P and 4P variants. Placeholder `.md` files hold page count and notes until the PDF is added.

---

## Additional components

Parts that don't map to a structural letter (e.g. decorative panels, door pieces) use:
```
{PRODUCT_CODE}_{DescriptiveName}_{Qty}x_{Version}.stl
```
Example: `SW028_DoorPanel_4x_C5.stl` — 4 identical door panels, version C5.

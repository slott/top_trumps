# Super Trumps Data Repository

This directory houses the structured dataset and high-quality WebP card assets for the **Super Trumps** (Top Trumps) digital card game. It is designed to serve as a single source of truth that can be easily parsed and integrated into game clients.

---

## Repository Structure

```
top_trumps_data/
├── cards/                  # Card definitions & metadata
│   ├── manifest.json       # Active card set registry
│   ├── cars.json           # Card set: Cars (ID prefix: AV-)
│   ├── jets.json           # Card set: Jets (ID prefix: JT-)
│   ├── spaceships.json     # Card set: Spaceships (ID prefix: SP-)
│   ├── tanks.json          # Card set: Tanks (ID prefix: TK-)
│   └── trains.json         # Card set: Trains (ID prefix: TR-)
├── images/                 # Generated WebP assets for all cards
│   ├── title_*.webp        # Deck cover/title images
│   ├── av_*.webp           # Car illustrations (matching AV-xxx)
│   ├── jt_*.webp           # Jet illustrations (matching JT-xxx)
│   ├── sp_*.webp           # Spaceship illustrations (matching SP-xxx)
│   ├── tk_*.webp           # Tank illustrations (matching TK-xxx)
│   └── tr_*.webp           # Train illustrations (matching TR-xxx)
├── PRIVACY_POLICY.md       # Privacy policy for the digital game
└── AGENTS.md               # This database and schema reference
```

---

## Card Decks Overview

We support 5 themed decks, configured in `cards/manifest.json`.

| Set ID | Deck Name | Card ID Prefix | Comparison Categories |
| :--- | :--- | :--- | :--- |
| **cars** | Cars | `AV-xxx` | Top Speed, 0-100 km/h (Lower is Better), Engine Size, Cylinders, Horsepower |
| **jets** | Jets | `JT-xxx` | Top Speed, Range, Thrust, Service Ceiling, Length, Wingspan |
| **spaceships** | Spaceships | `SP-xxx` | Speed, Maneuvering, Shield, Firepower, Weight |
| **tanks** | Tanks | `TK-xxx` | Top Speed, Weight, Crew, Engine Power |
| **trains** | Trains | `TR-xxx` | Top Speed, Weight, Length, Engine Power, Introduction Year (Lower is Better) |

---

## Schema Reference

### 1. Manifest (`cards/manifest.json`)
A simple list outlining which card sets are currently active and should be loaded.
```json
{
  "sets": ["cars", "jets", "spaceships", "trains", "tanks"]
}
```

### 2. Deck Datasets (e.g., `cards/cars.json`)
Each deck dataset defines:
- **Set Metadata:** The unique deck identifier and display name.
- **Comparison Categories:** The statistics that are compared between cards in combat. Each category specifies its display name, icon, unit, and whether a higher or lower value wins (`isHigherBetter`).
- **Cards List:** An array of 36 cards containing individual stats, details, and prompt definitions used to generate their respective illustrations.

```json
{
  "id": "cars",
  "name": "Cars",
  "titleImage": "title_cars",
  "categories": [
    {
      "id": "topSpeed",
      "name": "Top Speed",
      "icon": "💨",
      "unit": "km/h",
      "isHigherBetter": true
    },
    {
      "id": "acceleration",
      "name": "0-100 km/h",
      "icon": "⏱️",
      "unit": "s",
      "isHigherBetter": false
    }
  ],
  "cards": [
    {
      "id": "AV-001",
      "name": "Ford Model T",
      "year": 1908,
      "stats": {
        "topSpeed": 72.0,
        "acceleration": 30.0,
        "engineSize": 2.9,
        "cylinders": 4.0,
        "horsepower": 20.0
      },
      "imagePrompt": "A slightly cartoonish, stylized 3D illustration of a 1908 Ford Model T. Classic black with exaggerated vintage brass era details and slightly chunky wooden spoke wheels..."
    }
  ]
}
```

---

## Asset Naming Conventions

To ensure deterministic loading of assets by game clients, all images in `/images` conform to standard naming schemas.

### 🌌 Title Covers
Used as background covers on the deck selection screen:
* `title_cars.webp`
* `title_jets.webp`
* `title_spaceships.webp`
* `title_tanks.webp`
* `title_trains.webp`

### 🃏 Card Illustrations
Every card illustration is named by transforming the card's `id` from the JSON data:
1. Convert the entire ID to lowercase.
2. Replace all hyphens with underscores.
3. Append `.webp`.

**Examples:**
* Card ID `AV-001` ➔ `av_001.webp`
* Card ID `JT-036` ➔ `jt_036.webp`
* Card ID `SP-015` ➔ `sp_015.webp`
* Card ID `TK-005` ➔ `tk_005.webp`
* Card ID `TR-022` ➔ `tr_022.webp`

### 🎨 Visual Identity & Artwork Guidelines
All images are generated using AI image creators to follow a highly uniform aesthetic:
* **Art Style:** A cohesive, slightly cartoonish, stylized 3D illustration (akin to claymation or polished vinyl toy figures).
* **Composition:** Clean studio lighting, a single centered subject, and a simple colored gradient background. No overlapping UI text overlays should be present in the source image.
* **Dimensions:** Standard target size is `1440x1080` pixels.
* **Format:** WebP with balanced performance-to-size compression to keep asset payloads lightweight.

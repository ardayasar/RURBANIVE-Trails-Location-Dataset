# Rurbanrive Trails - Location Dataset

Welcome to the **Rurbanrive Trails Location Dataset**. This repository contains the core dataset for the Rurbanrive Trails audio-guide experience, featuring curated stories, geolocation data, and metadata for historical and cultural sites.

## 📂 Repository Structure

```
.
├── data/
│   └── locations.json      # Primary dataset file
├── LICENSE                 # CC-BY-SA 4.0 License
└── README.md               # This documentation
```

## 📊 Data Schema

The dataset is stored in `data/locations.json`. Below is the structure of a location object:

| Field | Type | Description |
|-------|------|-------------|
| `location_id` | Integer | Unique identifier for the location. |
| `title` | Object | Localized titles (e.g., `en`). |
| `segment` | Object | Trail segment info (`id`, `name`). |
| `category` | Object | Location category info (`id`, `name`). |
| `coordinates` | Object | Geolocation `{lat, lon}`. |
| `trigger_radius_meters`| Integer | Distance in meters to trigger the audio guide. |
| `year_made` | Integer \| Null | Year the location was established/recorded. |
| `voice` | Object | Audio metadata (`will_be_voiced`, `narrator`, `text`, `language`, `file_path`). |
| `threats` | Array | Potential hazards (e.g., "Slippery"). |
| `resources` | Array | Available amenities (e.g., "Water", "Shadow"). |
| `timestamp_of_creation`| String | ISO timestamp of record creation. |
| `contributor` | String | Organization or individual who contributed the data. |

### Example Entry

```json
{
  "location_id": 3,
  "title": {
    "en": "Sightseeing of Ölüdeniz"
  },
  "segment": {
    "id": 3,
    "name": "Fethiye(Ovacık) - Kirme"
  },
  "category": {
    "id": 18,
    "name": "Photography & Scenic Viewpoints"
  },
  "coordinates": {
    "lat": "36.53508",
    "lon": "29.139856"
  },
  "trigger_radius_meters": 15,
  "year_made": null,
  "voice": {
    "will_be_voiced": false,
    "narrator": null
  },
  "threats": [],
  "resources": ["Water", "Shadow"],
  "timestamp_of_creation": "2026-02-23T15:12:00.110Z",
  "contributor": "Artemis Outdoor"
}
```

## 🚀 Usage

You can consume this data directly in your application:

**JavaScript / Node.js:**
```javascript
const dataset = require('./data/locations.json');
const allLocations = dataset.locations;
```

**Python:**
```python
import json

with open('data/locations.json', 'r') as f:
    data = json.load(f)
    print(f"Loaded {len(data['locations'])} locations")
```

## 🤝 Contributing

We welcome contributions!
1.  **New Locations**: Add a new object to the `locations` array in `data/locations.json`.
2.  **Pull Requests**: Detailed descriptions of the changes are appreciated.

## 📄 License

This dataset is licensed under the **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**.

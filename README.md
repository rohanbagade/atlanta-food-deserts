# Atlanta Food Desert Accessibility Analysis

Interactive visualization of a two-phase greedy heuristic for optimizing supermarket facility locations to improve food desert accessibility in metropolitan Atlanta.

![App Preview](https://img.shields.io/badge/Status-Live-success)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![License](https://img.shields.io/badge/License-MIT-green)

## 🔗 Live Demo

**[View Live App →](YOUR_RENDER_URL_HERE)**

## 📋 Overview

This tool demonstrates how transit-based facility location optimization can improve food access for residents of food deserts in the Atlanta metropolitan area. The two-phase greedy heuristic:

1. **Phase 1 (Equity):** Prioritizes serving previously unserved census tracts
2. **Phase 2 (Efficiency):** Minimizes weighted travel times across all tracts

### Key Features

- 🗺️ Interactive map of Atlanta showing food deserts, existing stores, MARTA transit stops
- 📊 Real-time metrics dashboard
- 🎚️ Slider to explore outcomes for different facility budgets (p=0 to 57)
- 🔘 Toggle map layers on/off
- 📈 Progressive accessibility improvement visualization

### Key Results

- **7.4× better** than government intervention (Invest Atlanta)
- **29.5% reduction** in travel time with just 10 facilities
- **100% tract coverage** achieved at p=38 facilities
- **Diminishing returns** clearly demonstrated

## 🛠️ Technology Stack

- **Backend:** Python, Dash, Plotly
- **Data:** USDA Food Atlas, MARTA GTFS, Google Places API
- **Deployment:** Render.com
- **Optimization:** Two-phase greedy heuristic

## 📁 Data Sources

- **USDA Food Access Research Atlas (2019):** Census tract-level food access indicators
- **MARTA GTFS:** Transit network routes and schedules
- **Google Places API:** Existing supermarket locations
- **Census Data:** Household demographics and vehicle ownership

## 🚀 Local Development

### Prerequisites

```bash
python >= 3.11
```

### Installation

```bash
# Clone repository
git clone https://github.com/yourusername/atlanta-food-deserts.git
cd atlanta-food-deserts

# Install dependencies
pip install -r requirements.txt

# Run locally
python atlanta_food_desert_gui_render.py
```

Open browser to `http://localhost:8050`

## 📊 Data Files Required

Place these files in the root directory:

- `demand_points_weight_hunv.xlsx` - Food desert census tracts with HUNV weights
- `facilities_all_fixed_marta.xlsx` - Existing and candidate facility locations
- `marta_stop_pair_stats_with_modes.csv` - MARTA transit network edges

## 📖 Methodology

The tool implements a two-phase greedy heuristic inspired by the p-median facility location problem:

### Phase 1: Equity-Focused Selection
- Iteratively selects facilities that provide largest accessibility gain for **unserved tracts**
- Continues until all reachable tracts have experienced improvement
- Ensures geographic coverage and equitable access

### Phase 2: Efficiency-Focused Selection  
- Evaluates facilities based on total weighted accessibility gain across **all tracts**
- Provides incremental improvements to already-served populations
- Optimizes overall system efficiency

### Accessibility Metric

Weighted average round-trip travel time:

```
d̄ = Σᵢ wᵢ dᵢ / Σᵢ wᵢ
```

Where:
- `wᵢ` = households without vehicle access in tract i
- `dᵢ` = round-trip travel time from tract i to nearest facility

## 📈 Results Summary

| Facilities | Travel Time | Improvement | Tracts Served | HUNV Served |
|------------|-------------|-------------|---------------|-------------|
| 0 (Baseline) | 48.02 min | - | - | - |
| 10 | 33.86 min | 29.5% | 21/57 | 7,266 (51%) |
| 20 | 27.87 min | 42.0% | 38/57 | 11,072 (78%) |
| 38 | 23.01 min | 52.1% | 57/57 | 14,232 (100%) |

**Comparison with Government Policy:**
- Invest Atlanta: 0.67 min improvement with 2 facilities
- Greedy Heuristic: 4.98 min improvement with 2 facilities
- **7.4× better performance**

## 🎓 Academic Context

This project was developed as a writing sample for PhD applications, demonstrating:

- Operations research methodology
- Geospatial analysis
- Public policy applications
- Software development and deployment
- Data visualization and communication

## 📄 Citation

If you use this work, please cite:

```
[Your Name]. (2025). Atlanta Food Desert Accessibility Analysis: 
Two-Phase Greedy Heuristic for Transit-Based Facility Location. 
GitHub repository: https://github.com/yourusername/atlanta-food-deserts
```

## 📝 License

MIT License - feel free to use for academic or research purposes.

## 👤 Author

**[Your Name]**
- PhD Applicant - Stanford University
- [Email]
- [LinkedIn]
- [Personal Website]

## 🙏 Acknowledgments

- Data: USDA Economic Research Service, MARTA, Google Places API
- Inspiration: Margaret Brandeau's work on health systems optimization
- Framework: Classic p-median facility location problem

## 📧 Contact

Questions or feedback? Reach out at [your.email@example.com]

---

**Built with ❤️ for improving food access equity**

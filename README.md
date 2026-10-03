# 🌩️ AEGIS WX

### AI-Driven Spatio-Temporal Intelligence for Extreme Weather Anomalies

> **See the event. Understand its evolution. Explore its future.**

![Status](https://img.shields.io/badge/status-prototype-orange)
![SIH](https://img.shields.io/badge/SIH-PS%2026078-blue)
![Theme](https://img.shields.io/badge/theme-Smart%20Automation-green)
![Backend](https://img.shields.io/badge/backend-FastAPI-009688)
![Frontend](https://img.shields.io/badge/frontend-React%20%2B%20TypeScript-61dafb)
![Data](https://img.shields.io/badge/data-DEMO%20%2F%20SYNTHETIC-red)

**Smart India Hackathon — Problem Statement 26078**
**Problem:** AI-Driven Spatio-Temporal Tracking of Extreme Weather Anomalies in Medium-Range Forecasts
**Domain:** Weather Intelligence · AI · Geospatial Analytics · Scientific Computing

> ⚠️ **Disclaimer:** This is an experimental research prototype. All demo outputs are generated from **synthetic data** and are **NOT an official forecast or alert**. Operational use requires validation by meteorological experts and official sources (e.g., IMD).

---

## 📑 Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Problem Statement](#2-problem-statement)
3. [Proposed Solution & Core Idea](#3-proposed-solution--core-idea)
4. [Key Differentiators](#4-key-differentiators)
5. [System Architecture](#5-system-architecture)
6. [End-to-End Processing Pipeline](#6-end-to-end-processing-pipeline)
7. [Scientific & Algorithmic Design](#7-scientific--algorithmic-design)
8. [Event Intelligence Layer](#8-event-intelligence-layer)
9. [Prediction, Uncertainty & Scenario Lab](#9-prediction-uncertainty--scenario-lab)
10. [Machine Learning Strategy](#10-machine-learning-strategy)
11. [Data Layer: Demo & Real Data](#11-data-layer-demo--real-data)
12. [Backend & API Design](#12-backend--api-design)
13. [Database Design](#13-database-design)
14. [Frontend & User Experience](#14-frontend--user-experience)
15. [Computational Optimization & Scalability](#15-computational-optimization--scalability)
16. [Explainability & Provenance](#16-explainability--provenance)
17. [Evaluation & Benchmarking](#17-evaluation--benchmarking)
18. [Technology Stack](#18-technology-stack)
19. [Repository Structure](#19-repository-structure)
20. [Getting Started](#20-getting-started)
21. [Development Roadmap](#21-development-roadmap)
22. [MVP vs Advanced Version](#22-mvp-vs-advanced-version)
23. [Security](#23-security)
24. [Limitations](#24-limitations)
25. [Ethical & Scientific Principles](#25-ethical--scientific-principles)
26. [Future Scope](#26-future-scope)
27. [Contributing](#27-contributing)
28. [Project Status](#28-project-status)
29. [SIH Pitch Summary](#29-sih-pitch-summary)

---

## 1. Executive Summary

**AEGIS WX** is an AI-assisted extreme-weather intelligence platform that **identifies, characterizes, tracks, explains, and simulates** extreme weather anomalies within large Numerical Weather Prediction (NWP) datasets.

Conventional weather systems expose values, maps, forecasts and alerts. AEGIS WX takes a different approach:

> **Treat every extreme weather anomaly as a dynamic, persistent *event* rather than a static weather condition.**

When an anomaly is detected, it receives a unique identity (e.g. `WX-IND-042`) and is continuously characterized by:

| Dimension | Description |
|---|---|
| Footprint | Geographic polygon and area (km²) |
| Intensity | Anomaly magnitude / standardized score |
| Movement | Direction, speed, acceleration |
| Growth | Expansion / contraction rate |
| Persistence | Duration of the event |
| Lifecycle | Formation → Peak → Dissipation |
| Uncertainty | Confidence of each inference |
| Memory | Historical analogues |
| Relationships | Merge / split / compound-event graph |
| Future | Probabilistic footprint at +24h / +48h / +72h |

```text
Massive NWP Grid Data
        ↓
Anomaly Detection
        ↓
Spatial Footprint
        ↓
Weather Event
        ↓
Temporal Tracking
        ↓
Event Intelligence
        ↓
Future Evolution
```

The result is a **human-readable intelligence layer** between raw meteorological datasets and decision makers.

---

## 2. Problem Statement

**SIH PS 26078 — AI-Driven Spatio-Temporal Tracking of Extreme Weather Anomalies in Medium-Range Forecasts**

NWP outputs contain enormous amounts of spatial and temporal information (e.g. a `72 × 361 × 720` grid *per variable*). The challenge is **not** producing yet another forecast — it is efficiently answering:

1. **Where** is an extreme anomaly occurring?
2. **When** did it begin?
3. How **large** is its geographic footprint?
4. How **intense** is it?
5. Is it **expanding, shrinking, moving, or intensifying**?
6. Is it part of a **larger event**?
7. How could its footprint **evolve**?
8. How **certain** is the prediction?
9. Have **similar events occurred historically**?
10. Can the system **explain** why the event was classified as extreme?

AEGIS WX is designed around these ten questions.

### Challenges addressed

| Challenge | AEGIS WX response |
|---|---|
| Massive data volume | Adaptive-resolution processing, chunking, lazy compute |
| Absolute thresholds are misleading | Dynamic, climatology-aware anomaly detection |
| Anomalies are fields, not objects | Connected components → polygons → persistent events |
| Events evolve over time | Tracking with overlap / distance / similarity scoring |
| Black-box ML is hard to trust | Hybrid, explainable architecture |
| Forecasts are uncertain | Probability cones & explicit data-status labels |

---

## 3. Proposed Solution & Core Idea

Most weather systems think in terms of **Temperature, Pressure, Wind, Rainfall, Forecast**.

AEGIS WX thinks in terms of **EVENT**.

An event has: `Identity · Location · Geometry · Intensity · Trajectory · Lifecycle · History · Relationships · Future states · Uncertainty · Explanation`.

### Example event card

```text
EVENT ID        WX-IND-042
TYPE            Extreme Heat
CURRENT STATE   Intensifying
INTENSITY       +6.8°C anomaly
FOOTPRINT       183,420 km²
MOVEMENT        NE @ 41 km/h
EXPANSION       +31% / 24h
PERSISTENCE     96 hours
FORECAST        +24h / +48h / +72h
DATA STATUS     DEMO
```

### Vision

```mermaid
flowchart LR
    A[Massive NWP Data] --> B[Data Processing]
    B --> C[Anomaly Detection]
    C --> D[Spatial Footprint Extraction]
    D --> E[Event Creation]
    E --> F[Event Intelligence]
    F --> G[Future Evolution]
    G --> H[Human Decision Support]
```

> AEGIS WX does **not** try to replace operational NWP models. It focuses on **understanding and tracking extreme events inside forecast data**.

---

## 4. Key Differentiators

### 4.1 Event DNA
A multidimensional fingerprint used for comparison and historical analogue retrieval.

```text
EVENT DNA
Intensity       ████████░░
Persistence     █████████░
Expansion       ███████░░░
Movement        ██████░░░░
Rarity          █████████░
Uncertainty     ████░░░░░░
```

### 4.2 Event Lifecycle
```text
FORMATION → DETECTION → EXPANSION → INTENSIFICATION → PEAK → DECAY → DISSIPATION
```

### 4.3 Event Genealogy
Events can **merge, split, intensify, weaken, disappear**, forming a family tree.

```mermaid
flowchart TD
    A[WX-021] --> B[WX-022]
    A --> C[WX-023]
    B --> D[WX-024]
    C --> D
    D --> E[Dissipation]
```

### 4.4 Future Probability Cone
Instead of one deterministic polygon, show nested probability regions whose outer bounds widen with lead time.

```text
        +72h   ░░░░██████░░░░
        +48h     ██████████
        +24h       ██████
     CURRENT        ████
```

### 4.5 Event Memory
Event fingerprints are stored and searched to retrieve **historically similar events** (intensity, duration, footprint, movement, expansion, temporal evolution).

```mermaid
flowchart LR
    A[Current Event] --> B[Event DNA]
    B --> C[Similarity Engine]
    C --> D[Historical Event Database]
    D --> E[Top Analogues]
```

### 4.6 Compound Events
Multiple anomalies can interact. Examples:

```text
Extreme Heat + High Humidity + Low Night Cooling   →  Compound Heat Stress
Cyclonic Circulation + Moisture Transport + Terrain →  Extreme Rainfall Potential
```

Represented as an **event graph** (correlation is explicitly distinguished from causation).

### 4.7 Adaptive Resolution
```text
GLOBAL → REGIONAL → CANDIDATE REGION → HIGH-RESOLUTION EVENT → EXACT FOOTPRINT
```
Compute is concentrated around candidate anomalies instead of processing every cell at maximum cost.

---

## 5. System Architecture

```mermaid
flowchart TB
    subgraph DATA["DATA SOURCES"]
        A1[NWP Forecasts]
        A2[NetCDF]
        A3[GRIB]
        A4[Historical Data]
        A5[Optional Observations]
    end

    subgraph INGEST["DATA INGESTION"]
        B1[Dataset Loader]
        B2[Validation]
        B3[Normalization]
        B4[Spatial/Temporal Indexing]
    end

    subgraph SCIENCE["SCIENTIFIC PROCESSING"]
        C1[Xarray]
        C2[NumPy]
        C3[SciPy]
        C4[GeoPandas]
        C5[Shapely]
    end

    subgraph DETECTION["ANOMALY ENGINE"]
        D1[Baseline Generation]
        D2[Anomaly Calculation]
        D3[Dynamic Thresholding]
        D4[Candidate Detection]
        D5[Connected Components]
    end

    subgraph EVENTS["EVENT INTELLIGENCE"]
        E1[Event Creation]
        E2[Event DNA]
        E3[Lifecycle]
        E4[Trajectory Tracking]
        E5[Merge/Split Detection]
        E6[Compound Event Graph]
    end

    subgraph PREDICTION["FUTURE ANALYSIS"]
        F1[Persistence Analysis]
        F2[Historical Analogue]
        F3[Future Footprint]
        F4[Uncertainty]
        F5[Scenario Simulation]
    end

    subgraph STORAGE["STORAGE"]
        G1[(PostgreSQL)]
        G2[(PostGIS)]
        G3[(Object Storage)]
    end

    subgraph API["API"]
        H1[FastAPI]
    end

    subgraph UI["FRONTEND"]
        I1[React]
        I2[MapLibre / Leaflet]
        I3[D3.js]
        I4[Event Intelligence UI]
    end

    DATA --> INGEST --> SCIENCE --> DETECTION --> EVENTS --> PREDICTION
    DETECTION --> STORAGE
    EVENTS --> STORAGE
    PREDICTION --> STORAGE
    STORAGE --> API --> UI
```

### Layer summary

| Layer | Responsibility |
|---|---|
| **Ingestion** | Decode, validate, normalize, index NWP datasets |
| **Scientific processing** | Gridded math, geometry, spatial ops |
| **Anomaly engine** | Baselines, anomalies, thresholds, candidate masks |
| **Event intelligence** | Event identity, tracking, DNA, lifecycle, genealogy |
| **Future analysis** | Footprint projection, uncertainty, scenarios |
| **Storage** | Relational + spatial + object storage |
| **API** | Typed REST interface (FastAPI) |
| **Frontend** | Map workspace, Event Passport, timeline, Scenario Lab |

---

## 6. End-to-End Processing Pipeline

```mermaid
flowchart LR
    A[Raw Dataset] --> B[Decode] --> C[Validate] --> D[Normalize Units]
    D --> E[Temporal Alignment] --> F[Baseline] --> G[Anomaly Field]
    G --> H[Threshold / Candidate Mask] --> I[Spatial Segmentation]
    I --> J[Footprint Extraction] --> K[Event Association]
    K --> L[Event Update] --> M[DNA] --> N[Prediction] --> O[API / Storage]
```

### Step 1 — Ingestion
Supported inputs: **NetCDF, GRIB/GRIB2, CSV / processed grids**.
Candidate variables: temperature, pressure, wind, humidity, precipitation, geopotential height.
The data adapter is modular so different providers can be plugged in.

### Step 2 — Validation
Checks: latitude/longitude, timestamps, variable units, missing values, grid dimensions, forecast lead time, coordinate ordering.

```text
Example input grid:  time × latitude × longitude  =  72 × 361 × 720
```

### Steps 3–10
Normalization → baseline → anomaly → thresholding → segmentation → footprint → tracking → DNA/prediction → storage/API (detailed in §7–§9).

---

## 7. Scientific & Algorithmic Design

### 7.1 Baseline / Climatology Engine

```text
Anomaly  = Forecast Value − Expected Baseline
Z-score  = (X − μ) / σ
```

- `X` = forecast value, `μ` = baseline mean, `σ` = baseline standard deviation.
- Baselines can vary by **location, month, season, time of day, variable**.

### 7.2 Dynamic Anomaly Detection

A naive rule (`T > 45°C`) ignores local context.

| Location | Baseline | Forecast | Anomaly |
|---|---|---|---|
| A | 40°C | 44°C | **+4°C** |
| B | 27°C | 40°C | **+13°C** |

Location B is far more anomalous despite the lower absolute temperature.

Suggested detection logic:

```python
import xarray as xr

def detect_anomaly(forecast: xr.DataArray, clim_mean: xr.DataArray,
                   clim_std: xr.DataArray, z_threshold: float = 2.0):
    anomaly = forecast - clim_mean
    z = anomaly / clim_std
    mask = z >= z_threshold          # configurable, never hardcoded
    return anomaly, z, mask
```

Thresholds are **configurable and dataset-calibrated**, not hardcoded meteorological constants.

### 7.3 Spatial Footprint Extraction

```mermaid
flowchart LR
    A[Anomaly Grid] --> B[Binary Mask] --> C[Connected Components]
    C --> D[Noise Filtering] --> E[Contour Extraction]
    E --> F[Polygon] --> G[Geographic Footprint]
```

```text
Binary mask example
0 0 0 1 1 0
0 0 1 1 1 0
0 1 1 1 0 0
0 0 1 0 0 0
```

Output per footprint: `Polygon/MultiPolygon`, **area (km²)**, **centroid (lat/lon)**, **bounding box**. Area must use geodesic / equal-area computation (cell area varies with latitude: `∝ cos(φ)`).

Tools: `scipy.ndimage.label`, `skimage.measure.find_contours` / `rasterio.features.shapes`, `shapely`, `geopandas`.

### 7.4 Temporal Tracking

An event at time `t` is associated with one at `t+1` using a composite score:

```text
Tracking Score = w1·IoU + w2·DistanceSimilarity + w3·AreaSimilarity + w4·IntensitySimilarity
IoU = |A ∩ B| / |A ∪ B|
```

Recommended implementation:

1. Build a cost matrix between all events at `t` and candidates at `t+1`.
2. Solve with the **Hungarian algorithm** (`scipy.optimize.linear_sum_assignment`).
3. Accept matches above a threshold; unmatched candidates → **new event**; unmatched events → **dissipating**.
4. One-to-many / many-to-one overlaps → **split / merge**.

### 7.5 Movement Estimation

For centroids `P1 → P2 → P3 → P4`, compute great-circle (haversine) distances, then:

```text
speed        = distance / Δt
direction    = bearing(Pi, Pi+1)
acceleration = Δspeed / Δt
```

Example: `Direction: North-East · Velocity: 41 km/h · Acceleration: +6 km/h²`.
Smooth with a moving average / Kalman filter to reduce noise.

### 7.6 Expansion / Contraction

```text
Expansion Rate = (A(t) − A(t−Δt)) / A(t−Δt)
Example: 140,000 km² → 183,420 km²  ⇒  ≈ +31%
```

### 7.7 Intensification

For anomaly intensity `I(t)`, estimate `dI/dt`.

```text
+3.1°C → +4.5°C → +6.8°C   ⇒  Intensifying
```

States: `Stable · Weakening · Intensifying · Rapidly Intensifying` — cut-offs are **calibrated per dataset**.

### 7.8 Lifecycle State Machine

```mermaid
stateDiagram-v2
    [*] --> Formation
    Formation --> Detected
    Detected --> Expanding
    Expanding --> Intensifying
    Intensifying --> Peak
    Peak --> Decaying
    Decaying --> Dissipated
    Dissipated --> [*]
```

Transitions are rule-based on `dA/dt`, `dI/dt` and persistence; events may skip or revisit states depending on observed evolution.

### 7.9 Merge / Split Engine

```text
MERGE:   A ──┐              SPLIT:       ┌──> B
             ├──> C                  A ──┤
         B ──┘                            └──> C
```

The event graph preserves genealogy (parent/child links with overlap weights).

---

## 8. Event Intelligence Layer

### 8.1 Event State Model

```text
Event
 ├── Identity
 ├── Type
 ├── Current State
 ├── Geometry
 ├── Observations
 ├── Trajectory
 ├── DNA
 ├── Lifecycle
 ├── Confidence
 ├── Historical Analogues
 └── Predictions
```

### 8.2 Event DNA

```text
EventDNA {
    intensity_score
    persistence_score
    spatial_extent_score
    expansion_score
    movement_score
    rarity_score
    uncertainty_score
}
```

Each component is normalized to `[0, 1]` (e.g. percentile rank against historical/demo distribution). Weights are **configurable and validated** against the chosen dataset.

### 8.3 Historical Analogue Engine

Feature vector:

```text
X = [intensity, duration, area, expansion_rate, movement_speed, persistence, rarity]
```

- **v1:** standardized features + Euclidean / cosine similarity + k-Nearest Neighbors.
- **v2:** learned embeddings (autoencoder / contrastive).
- Output: top-k analogues with similarity % (e.g., *87% similar*) and a per-feature breakdown.

### 8.4 Compound Event Engine

```mermaid
flowchart TD
    A[Temperature Anomaly] --> D[Heat Event]
    B[High Humidity] --> D
    C[Low Night Cooling] --> D
    D --> E[Compound Heat Stress]

    F[Cyclonic Circulation] --> G[Rainfall Event]
    H[Moisture Transport] --> G
    I[Terrain] --> G
    G --> J[Extreme Rainfall Potential]
```

Events overlapping in space/time are linked as graph edges. The engine labels edges as **co-occurrence/correlation** unless a documented physical mechanism supports causal wording.

### 8.5 Event Intelligence Agent

A scientific, **grounded** natural-language interface:

```text
User:  Which event is intensifying fastest?
Agent: WX-IND-042 has the highest observed intensification rate
       in the current demonstration dataset.
Actions: [SHOW EVENT] [SHOW TRAJECTORY] [SHOW ANALOGUES] [SHOW FORECAST]
```

The agent **must answer only from structured event data** (tool/function calls over the API) — never from invented weather information.

---

## 9. Prediction, Uncertainty & Scenario Lab

### 9.1 Future Footprint Engine (swappable levels)

| Level | Method |
|---|---|
| 1 | Persistence-based extrapolation |
| 2 | Centroid trajectory + footprint growth |
| 3 | Machine-learning prediction |
| 4 | Multi-model / probabilistic forecasting |

All levels implement the same interface so the frontend never changes.

### 9.2 Uncertainty Model

- Qualitative: `High / Medium / Low` confidence, or probability bands `90% · 70% · 50% · 30%`.
- The system **never implies a guaranteed footprint**.
- Every UI element carries a data-status tag:

```text
OBSERVED  ·  MODEL OUTPUT  ·  INFERENCE  ·  SIMULATION
```

### 9.3 Scenario Lab

Users explore hypotheticals:

```text
Intensity:   Current → +20%
Persistence: 72h → 120h
```

Output is a hypothetical footprint explicitly labelled:

```text
SIMULATION — NOT AN OFFICIAL FORECAST
```

---

## 10. Machine Learning Strategy

AEGIS WX uses a **hybrid architecture** rather than pretending a neural network can replace NWP.

```mermaid
flowchart TB
    A[NWP Forecast] --> B[Scientific Preprocessing]
    B --> C[Climatological Baseline]
    B --> D[Spatial Features]
    B --> E[Temporal Features]
    C --> F[Anomaly Engine]
    D --> F
    E --> F
    F --> G[Candidate Events]
    G --> H[Spatial Segmentation]
    H --> I[Temporal Tracking]
    I --> J[Event Feature Vector]
    J --> K[ML Classification]
    J --> L[Similarity Engine]
    J --> M[Future Evolution]
    K --> N[Event Intelligence]
    L --> N
    M --> N
```

| Approach | Weakness |
|---|---|
| Pure ML (`Data → NN → Prediction`) | Hard to explain |
| Pure thresholds (`Data → Threshold → Alert`) | Too simplistic |
| **Hybrid** (science → spatial/temporal reasoning → ML refinement) | **Interpretable + adaptive** |

### Phased plan

- **Phase 1:** Statistical anomaly detection + connected components + tracking + scikit-learn.
- **Phase 2:** Random Forest, Gradient Boosting (XGBoost if required).
- **Phase 3:** CNN, ConvLSTM, Temporal Transformer, Graph Neural Network — **only where justified by data and task**.

> Do **not** wait for a perfect ML model. A complete deterministic prototype is more valuable first.

---

## 11. Data Layer: Demo & Real Data

### 11.1 Demo Data Strategy
The prototype must run **without operational NWP infrastructure**. A generator produces scientifically structured synthetic data:

```text
Time:       72 steps
Domain:     India region (lat/lon grid)
Variables:  Temperature, Pressure, Wind, Humidity, Precipitation
```

Synthetic events can **move, expand, contract, intensify, weaken, merge, split**. All such data is labelled:

```text
DEMO DATA — NOT AN OFFICIAL FORECAST
```

### 11.2 Adapter Pattern

```text
DataAdapter (interface)
   ├── DemoDataAdapter  → Synthetic NWP
   └── RealDataAdapter
          ├── NetCDF
          └── GRIB
```

The pipeline never depends on a specific provider.

### 11.3 Data Formats

| Category | Formats |
|---|---|
| Scientific | NetCDF, GRIB / GRIB2 |
| Prototype | CSV, JSON, GeoJSON, Parquet |
| Geospatial output | GeoJSON, PostGIS geometries, vector tiles (future) |

---

## 12. Backend & API Design

**Framework:** FastAPI + Pydantic.

```text
GET  /api/v1/events
GET  /api/v1/events/{id}
GET  /api/v1/events/{id}/timeline
GET  /api/v1/events/{id}/dna
GET  /api/v1/events/{id}/trajectory
GET  /api/v1/events/{id}/analogues
GET  /api/v1/events/{id}/forecast
POST /api/v1/events/{id}/scenario

GET  /api/v1/anomalies
GET  /api/v1/datasets
GET  /api/v1/layers
POST /api/v1/analysis
```

### Example event object

```json
{
  "event_id": "WX-IND-042",
  "type": "EXTREME_HEAT",
  "state": "INTENSIFYING",
  "first_detected": "2026-10-03T06:00:00Z",
  "last_updated": "2026-10-03T12:00:00Z",
  "intensity_anomaly": 6.8,
  "area_km2": 183420,
  "movement": { "direction": "NE", "speed_kmh": 41 },
  "expansion_rate": 0.31,
  "confidence": 0.87,
  "data_status": "DEMO",
  "dna": {
    "intensity": 0.82,
    "persistence": 0.91,
    "expansion": 0.74,
    "movement": 0.61,
    "rarity": 0.89,
    "uncertainty": 0.32
  }
}
```

### Example detail response

```json
{
  "event_id": "WX-IND-042",
  "current_state": { "latitude": 17.4, "longitude": 78.5, "area_km2": 183420, "severity": 8.4 },
  "timeline": [],
  "footprints": [],
  "trajectory": [],
  "analogues": [],
  "forecast": [],
  "provenance": { "status": "DEMO_DATA" }
}
```

---

## 13. Database Design

**PostgreSQL + PostGIS**.

Core tables: `weather_datasets`, `forecast_runs`, `weather_events`, `event_observations`, `event_trajectories`, `event_footprints`, `event_dna`, `historical_analogues`, `compound_events`, `predictions`, `scenarios`.

```mermaid
erDiagram
    FORECAST_RUN ||--o{ WEATHER_EVENT : generates
    WEATHER_EVENT ||--o{ EVENT_OBSERVATION : contains
    WEATHER_EVENT ||--o{ EVENT_TRAJECTORY : follows
    WEATHER_EVENT ||--|| EVENT_DNA : has
    WEATHER_EVENT ||--o{ EVENT_FOOTPRINT : contains
    WEATHER_EVENT ||--o{ HISTORICAL_ANALOGUE : matches
    WEATHER_EVENT ||--o{ PREDICTION : generates
    WEATHER_EVENT ||--o{ SCENARIO : simulates
    WEATHER_EVENT }o--o{ COMPOUND_EVENT : participates
```

### Illustrative schema

```sql
CREATE EXTENSION IF NOT EXISTS postgis;

CREATE TABLE weather_events (
    event_id        TEXT PRIMARY KEY,           -- e.g. WX-IND-042
    event_type      TEXT NOT NULL,              -- EXTREME_HEAT, HEAVY_RAIN ...
    state           TEXT NOT NULL,
    first_detected  TIMESTAMPTZ NOT NULL,
    last_updated    TIMESTAMPTZ NOT NULL,
    data_status     TEXT NOT NULL DEFAULT 'DEMO',
    run_id          BIGINT REFERENCES forecast_runs(run_id)
);

CREATE TABLE event_footprints (
    footprint_id    BIGSERIAL PRIMARY KEY,
    event_id        TEXT REFERENCES weather_events(event_id),
    valid_time      TIMESTAMPTZ NOT NULL,
    geom            GEOMETRY(MultiPolygon, 4326) NOT NULL,
    area_km2        DOUBLE PRECISION,
    peak_anomaly    DOUBLE PRECISION
);
CREATE INDEX idx_footprints_geom ON event_footprints USING GIST (geom);
CREATE INDEX idx_footprints_time ON event_footprints (event_id, valid_time);
```

---

## 14. Frontend & User Experience

**Interaction model:**

```text
DISCOVER → UNDERSTAND → TRACK → COMPARE → PREDICT → SIMULATE
```

### Component map

```mermaid
flowchart TB
    A[React Application]
    A --> B[Application Shell]
    A --> C[Map Workspace]
    A --> D[Event Explorer]
    A --> E[Event Passport]
    A --> F[Timeline]
    A --> G[Analysis Workspace]
    A --> H[Scenario Lab]
    A --> I[Event Intelligence]
    C --> J[Map Layers]
    C --> K[Footprints]
    C --> L[Trajectories]
    C --> M[Forecast Cones]
    E --> N[Event DNA]
    E --> O[Lifecycle]
    E --> P[Metrics]
    E --> Q[Historical Memory]
```

### Main workspace (map-first)

```text
┌────────────────────────────────────────────────────────┐
│ AEGIS WX       Live   Events   Forecast   Analysis    │
├───────────────────────────────────────────────┬────────┤
│                                               │ EVENT  │
│                  MAP                          │ PASS-  │
│                                               │ PORT   │
│                                               │ DNA    │
│                                               │ STATE  │
├───────────────────────────────────────────────┴────────┤
│              EVENT TIMELINE / TIME SCRUBBER            │
└────────────────────────────────────────────────────────┘
```

### Event Passport

```text
WX-IND-042 · EXTREME HEAT
CURRENT STATE   INTENSIFYING
+6.8°C · 183,420 km² · NE @ 41 km/h
EVENT DNA       ████████████
LIFECYCLE       Detected → Expanding → Intensifying → Current
FORECAST        +24h | +48h | +72h
HISTORICAL      87% similar
```

### The six questions the UI answers immediately

```text
WHERE IS IT?  ·  WHEN DID IT START?  ·  HOW IS IT EVOLVING?
WHY IS IT EXTREME?  ·  WHERE COULD IT GO?  ·  HOW CERTAIN ARE WE?
```

---

## 15. Computational Optimization & Scalability

| Technique | Purpose |
|---|---|
| Spatial subsetting | Process only relevant regions |
| Temporal chunking | Avoid loading full dataset into memory |
| Lazy computation | Xarray + Dask-compatible patterns |
| Spatial indexing | PostGIS GiST indexes |
| Geometry simplification | Lighter polygons for rendering (`shapely.simplify`) |
| Caching | Redis for hot event/layer data |
| Async jobs | Celery workers for heavy analysis |
| Adaptive resolution | Coarse scan → refine candidates only |

### Scalability architecture

```mermaid
flowchart TB
    A[Global NWP Dataset] --> B[Ingestion Queue]
    B --> C[Distributed Processing]
    C --> D[Global Candidate Detection]
    D --> E[Regional Refinement]
    E --> F[Event Processing Workers]
    F --> G[PostGIS]
    G --> H[API Layer]
    H --> I[Web Clients]
```

The MVP runs locally; the same architecture scales to cloud/HPC.

### Deployment

```mermaid
flowchart TB
    A[User Browser] --> B[Reverse Proxy]
    B --> C[React Frontend]
    B --> D[FastAPI Backend]
    D --> E[(PostgreSQL + PostGIS)]
    D --> F[Processing Queue]
    F --> G[Analysis Workers]
    G --> H[NWP Object Storage]
    G --> E
```

---

## 16. Explainability & Provenance

### "Why was this detected?"

```text
WHY DETECTED?
Temperature anomaly:   +6.8°C
Persistence:           96 hours
Spatial extent:        183,420 km²
Expansion:             +31%
Historical rarity:     High
Primary signal:        Temperature departure
```

All values come from **actual calculations**, not templated text.

### Provenance

```text
Source:          NWP dataset
Run:             2026-10-03 00:00 UTC
Forecast lead:   +48h
Variable:        2m Temperature
Processing:      Anomaly Engine v1.0
Classification:  Extreme Heat
```

Processing parameters (thresholds, weights, versions) are recorded for **reproducibility**.

---

## 17. Evaluation & Benchmarking

### Metrics

| Category | Metrics |
|---|---|
| Detection | Precision, Recall, F1, False Positive Rate |
| Spatial accuracy | IoU, boundary error, centroid error, area error |
| Temporal tracking | Track continuity, fragmentation, association accuracy |
| Forecast | MAE, RMSE, spatial IoU, Brier score, calibration |
| Performance | Processing time, memory, grid cells/sec, latency |

### Adaptive-resolution experiment

```text
Method A: Full-resolution processing
Method B: Adaptive-resolution processing
Compare:  Processing time · Memory · Grid cells processed · Detection recall · Spatial accuracy
```

**Goal:** show that compute can be concentrated around candidate anomalies **without unacceptable loss of detection quality**.

### Benchmark table template

| Method | Cells processed | Time (s) | Peak memory (MB) | Recall | Mean IoU |
|---|---|---|---|---|---|
| Full-resolution | — | — | — | — | — |
| Adaptive-resolution | — | — | — | — | — |

---

## 18. Technology Stack

| Area | Technologies |
|---|---|
| **Frontend** | React, TypeScript, Vite, MapLibre GL JS / Leaflet, D3.js, Plotly |
| **Backend** | Python, FastAPI, Pydantic |
| **Scientific computing** | NumPy, Pandas, Xarray, SciPy, GeoPandas, Shapely |
| **Machine learning** | scikit-learn, PyTorch (future) |
| **Database** | PostgreSQL, PostGIS |
| **Optional infra** | Redis, Celery, Docker |

---

## 19. Repository Structure

```text
aegis-wx/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── docker-compose.yml
├── .env.example
├── .gitignore
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── features/
│   │   │   ├── map/
│   │   │   ├── events/
│   │   │   ├── timeline/
│   │   │   ├── event-dna/
│   │   │   ├── genealogy/
│   │   │   ├── forecast/
│   │   │   ├── scenario/
│   │   │   └── intelligence/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── types/
│   │   └── lib/
│   └── package.json
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   ├── anomaly/
│   │   ├── tracking/
│   │   ├── prediction/
│   │   ├── simulation/
│   │   └── main.py
│   └── requirements.txt
│
├── ml/
│   ├── models/
│   ├── features/
│   ├── training/
│   └── evaluation/
│
├── data/
│   ├── demo/
│   ├── raw/
│   ├── processed/
│   └── schemas/
│
├── docs/
│   ├── architecture/
│   ├── algorithms/
│   ├── api/
│   └── research/
│
└── scripts/
    ├── generate_demo_data.py
    ├── preprocess.py
    └── seed_database.py
```

---

## 20. Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+
- Docker & Docker Compose

### Setup

```bash
git clone <repository>
cd aegis-wx

# Start infrastructure (PostgreSQL/PostGIS, Redis)
docker compose up -d

# Backend
cd backend
pip install -r requirements.txt
python ../scripts/generate_demo_data.py
python ../scripts/seed_database.py
uvicorn app.main:app --reload --port 8000

# Frontend (new terminal)
cd frontend
npm install
npm run dev
```

| Service | URL |
|---|---|
| Frontend | http://localhost:5173 |
| Backend | http://localhost:8000 |
| API docs (Swagger) | http://localhost:8000/docs |

### Environment variables

Create a `.env` file (see `.env.example`):

```env
DATABASE_URL=postgresql://user:password@localhost:5432/aegis
REDIS_URL=redis://localhost:6379
API_ENV=development
```

> Never commit real secrets.

---

## 21. Development Roadmap

| Phase | Focus | Key deliverables |
|---|---|---|
| **1 — Foundation** | Setup | Repo, React, FastAPI, PostgreSQL/PostGIS, design system |
| **2 — Demo Data** | Synthetic NWP | Multi-variable grid, synthetic events, NetCDF-compatible structure |
| **3 — Detection** | Anomaly engine | Baseline, anomaly calc, dynamic thresholds, candidate regions |
| **4 — Footprint** | Geometry | Connected components, polygons, simplification, area |
| **5 — Tracking** | Temporal | Centroid + overlap matching, trajectory, speed, expansion |
| **6 — Event Intelligence** | Objects | Event ID, DNA, lifecycle, genealogy, memory |
| **7 — Prediction** | Future | Future footprint, probability cone, uncertainty, model comparison |
| **8 — Advanced** | Intelligence | Compound events, Scenario Lab, analogues, AI agent |
| **9 — Optimization** | Performance | Caching, async jobs, spatial indexing, large-data tuning |
| **10 — SIH Demo** | Delivery | End-to-end scenario, presentation, docs, benchmarks, deployment |

---

## 22. MVP vs Advanced Version

### MVP

- [x] Synthetic NWP dataset
- [x] Temperature anomaly detection
- [x] Spatial footprint extraction
- [x] Event creation & Event ID
- [x] Temporal tracking & timeline
- [x] Event DNA
- [x] Interactive map
- [x] Future footprint simulation
- [x] Explainable event panel

### Advanced

- [ ] Multiple weather variables & anomaly types
- [ ] Historical analogue engine
- [ ] Event genealogy
- [ ] Compound event detection
- [ ] Probabilistic forecast cone
- [ ] Multi-model consensus
- [ ] Scenario Lab
- [ ] AI Event Intelligence
- [ ] Real NWP adapters
- [ ] Distributed processing

### Example success scenario

```text
Load forecast run → ANOMALY DETECTED → FOOTPRINT CREATED → EVENT CONTINUED
→ tracker links observations (WX-IND-042) → footprint +31% → centroid NE @ 41 km/h
→ state: INTENSIFYING → analogues: 87% similar → +24h / +48h / +72h with uncertainty
```

---

## 23. Security

- Secrets via environment variables only — **no hardcoded keys**
- Never place secrets in frontend code
- API authentication where required
- Input validation (Pydantic) on all endpoints and uploads
- Rate limiting
- Strict CORS configuration
- Secure database credentials & least-privilege DB roles

---

## 24. Limitations

1. Synthetic data may not reproduce all physical atmospheric processes.
2. Thresholds require scientific calibration.
3. Event association can be ambiguous when multiple systems interact.
4. Future footprint prediction contains inherent uncertainty.
5. ML performance depends on training-data quality.
6. Operational deployment requires validation by meteorological experts.
7. An experimental prototype must **never replace official alerts**.

---

## 25. Ethical & Scientific Principles

| Principle | Meaning |
|---|---|
| **Transparency** | Every prediction states its data/source status |
| **Uncertainty** | Displayed, never hidden |
| **Explainability** | Classification can always be explained |
| **Reproducibility** | Processing parameters are recorded |
| **Scientific validation** | Operational use requires expert validation |
| **No false authority** | Demo predictions are never presented as official forecasts |

### Data-status taxonomy

| Label | Meaning |
|---|---|
| `OBSERVED` | Actual measurement |
| `FORECAST` | Model / NWP output |
| `INFERENCE` | System interpretation |
| `SIMULATION` | Hypothetical scenario |
| `OFFICIAL ALERT` | Only if sourced from an actual authority |

---

## 26. Future Scope

- Operational NWP integration
- Multi-model ensemble analysis
- Satellite data fusion & radar integration
- Real-time observations
- HPC acceleration & distributed processing
- Spatio-temporal Transformers
- Graph Neural Networks for event relationships
- Automated report generation
- Government decision-support integration
- Alert prioritization
- Sector-specific exposure analysis (agriculture, health, power, transport)

### Research directions

| Area | Question |
|---|---|
| Spatio-temporal anomaly detection | Where + when + how extreme? |
| Event tracking | How does an anomaly evolve? |
| Event representation | How can an extreme event be a machine-readable object? |
| Event similarity | Which historical events behaved similarly? |
| Uncertainty | How uncertain is the future footprint? |
| Computational efficiency | How can massive NWP fields be analyzed efficiently? |

---

## 27. Contributing

1. Create a feature branch.
2. Add tests.
3. Document scientific assumptions.
4. Avoid hardcoded meteorological thresholds.
5. Clearly distinguish demo data from real data.
6. Keep frontend components reusable.
7. Maintain API compatibility.
8. Document changes.

---

## 28. Project Status

> **Prototype / Research Demonstration**

```text
[ ] Architecture
[ ] Demo NWP generator
[ ] Data ingestion
[ ] Anomaly detection
[ ] Footprint extraction
[ ] Event tracking
[ ] Event DNA
[ ] Event lifecycle
[ ] Event genealogy
[ ] Historical memory
[ ] Future footprint
[ ] Compound events
[ ] Scenario Lab
[ ] Event Intelligence
[ ] Real NWP adapter
[ ] Performance benchmarking
```

*Update this checklist as development progresses.*

---

## 29. SIH Pitch Summary

**One-line description**

> **AEGIS WX transforms massive NWP forecasts into persistent, explainable, trackable extreme-weather events with geographic footprints, lifecycle intelligence, historical memory, and probabilistic future evolution.**

**Problem** — Massive NWP datasets hold extreme-weather signals, but identifying exact footprints and tracking their evolution is computationally expensive and hard to interpret.

**Solution** — Scientific anomaly detection + geospatial processing + event tracking + ML + visualization convert raw NWP fields into persistent extreme-weather event objects.

**Innovation** — An **Event Intelligence Layer**: Event DNA · Lifecycle · Genealogy · Historical Memory · Compound-event relationships · Future probability footprints · Explainable detection · Adaptive-resolution processing.

**Outcome** — A meteorologist or decision-maker moves from *raw NWP data* to *what is happening, where, how severe, how fast it is evolving, where it could go, and why the system believes it* — in a single interface.

**Fundamental difference**

```text
Conventional visualization:  Weather Data → Map
Forecast system:             Weather Data → Forecast
AEGIS WX:                    Weather Data → Anomaly → Event → Identity → Footprint → Lifecycle
                             → Trajectory → Relationships → Historical Memory → Future States
                             → Explainable Intelligence
```

---

<div align="center">

## 🌩️ AEGIS WX

**See the event. Understand its evolution. Explore its future.**

*SIH PS 26078 — AI-Driven Spatio-Temporal Tracking of Extreme Weather Anomalies in Medium-Range Forecasts*

</div>

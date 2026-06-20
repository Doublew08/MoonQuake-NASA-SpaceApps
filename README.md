# ðŸŒ• MoonQuake (NASA Space Apps Challenge)

<p align="center">
  <b>An interactive 3D visualization of raw NASA lunar seismometer data.</b><br/>
  <i>Maps historical moonquakes onto a spherical 3D lunar model, turning dry data into a public-facing geological timeline.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Unity-2021.3%2B-black?logo=unity" alt="Unity Version">
  <img src="https://img.shields.io/badge/Python-3.9%2B-blue?logo=python" alt="Python Version">
</p>

---

During the Apollo missions, seismometers were placed on the lunar surface, recording "moonquakes" over several years. This project, built for the **NASA Space Apps Challenge**, takes that raw, historical seismic data and translates it into an interactive 3D timeline. Users can scrub through time, observing when and where moonquakes occurred on a 3D model of the Moon, with earthquake magnitude visually represented.

## Data Pipeline & Mathematics

1. **Data Ingestion (Python)**: A Python script pre-processes the raw ALSEP (Apollo Lunar Surface Experiments Package) data, cleaning noise and exporting normalized coordinates and magnitudes to a lightweight JSON structure.
2. **Spherical Coordinate Mapping (C#)**: The Unity application parses the JSON and converts lunar latitude, longitude, and depth into 3D Cartesian coordinates (x, y, z) relative to the 3D Moon sphere.
   `csharp
   x = radius * cos(lat) * cos(lon)
   y = radius * sin(lat)
   z = radius * cos(lat) * sin(lon)
   `
3. **Performance Optimization**: Because thousands of data points are rendered, the system utilizes **Object Pooling** for quake markers and custom shaders to visualize seismic waves without CPU overhead.

---

## Architecture Overview

``mermaid
graph TD
    A["Raw NASA Data (CSV/TXT)"] --> B["Python Parser"]
    B --> C["Cleaned Data (JSON)"]
    C --> D["Unity Data Manager"]
    D --> E["Spherical Math Engine"]
    E --> F["Object Pool (Markers)"]
    F --> G["3D Render Pipeline"]
``

---

## Build

``bash
git clone https://github.com/Doublew08/MoonQuake-NASA-SpaceApps.git
``

**Requirements:**
- Unity 2021.3 LTS or newer.
- Python 3.9+ (if running the data parser in /Tools/).

---

## References

- NASA Space Apps Challenge 2021.
- Apollo Passive Seismic Experiment (PSE) Data Archive.

License: MIT.
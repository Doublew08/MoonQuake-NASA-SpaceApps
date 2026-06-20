# MoonQuake (NASA Space Apps Challenge)
An interactive 3D visualization of raw NASA lunar seismometer data. Maps historical moonquakes onto a spherical 3D lunar model, turning dry data into a public-facing geological timeline.

## Features
- **Data Pipeline:** Python script pre-processes raw NASA seismic data into lightweight JSON.
- **Coordinate Math:** Converts latitude/longitude to 3D vectors via spherical coordinates.
- **Performance:** Implements object pooling for quake markers and optimized custom shaders.

**Tech Stack:** Unity, C#, Python
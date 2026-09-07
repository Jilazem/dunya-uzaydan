# 🌍 Earth From Space — Interactive 3D Globe

A single-file, browser-based 3D Earth experience built with Three.js. It combines
real NASA imagery, a JPL-grade sky engine and live satellite tracking — no build
step, no API keys.

🔗 **Live demo:** https://jilazem.github.io/dunya-uzaydan/

![Three.js](https://img.shields.io/badge/Three.js-r185-black)
![NASA GIBS](https://img.shields.io/badge/Data-NASA_GIBS-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## ✨ Features

### 🛰️ Live NASA imagery (Google-Earth-style)
- **Zoom sharpness (LOD):** when you zoom in, the visible region is re-fetched
  from **NASA GIBS WMS** at up to ~3072 px (~40 px/°) and draped onto the globe
  as a high-resolution shell — sharpness keeps rising as you get closer.
- **Historical imagery archive:** pick any **year + month** (VIIRS since 2012,
  MODIS since Feb 2001) and click a thumbnail to wear that day's real satellite
  image — clouds included. Same archive Google Earth uses.

### 🌌 Real sky engine
- **5,044 real stars** (d3-celestial catalog, B–V color), **56,000-point
  Milky Way band**, constellation lines and labels in **Turkish**.
- **Moon + 8 textured planets** positioned from a **JPL DE440s** ephemeris
  table (interpolation error ≤ 0.4°, verified against skyfield).
- Sky rotates with real GMST — point the camera anywhere and the constellations
  are where they actually are tonight.

### 📡 Live satellites
- **ISS + 240 Starlink** satellites propagated in-browser with **SGP4**
  (satellite.js) from pre-baked TLEs, orbiting in sync with Earth's rotation.

### 🕐 Time & location engine
- Simulated clock (1×–3600× speed): day/night terminator, city lights and sky
  all follow the simulated moment.
- Search any city/country, fly to it, or use your own geolocation.
- Live weather via **Open-Meteo** for the selected location.

### 🖱️ Interaction
- Click a planet, the Moon or a satellite to **fly to it**; per-layer 📍 buttons
  do the same.
- Collapsible panel, **Turkish / English** interface.

## 🗂 Data sources (all free, no keys)
| Data | Source |
|---|---|
| Historical & regional imagery | NASA GIBS WMS |
| Planet/Sun textures | Solar System Scope |
| Stars / Milky Way / constellations | d3-celestial |
| Moon & planet positions | JPL DE440s (via skyfield, pre-baked) |
| TLEs (ISS, Starlink) | ivanstanojevic TLE API |
| Weather | Open-Meteo |

## 🚀 Run locally
```bash
git clone https://github.com/Jilazem/dunya-uzaydan.git
cd dunya-uzaydan
python3 -m http.server 8000
# open http://localhost:8000/dunya-uzaydan.html
```
> Serve over HTTP (not `file://`) — binary data files need fetch/CORS.

## 📄 License
MIT — textures and datasets belong to their respective agencies/authors
(NASA, ESA, Solar System Scope, OFrohn/d3-celestial).

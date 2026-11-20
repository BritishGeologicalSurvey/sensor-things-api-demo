# BGS SensorThings API Demo

This repository provides examples for querying, visualising, and mapping environmental monitoring data from the [British Geological Survey (BGS) Sensor Data Service](https://sensors.bgs.ac.uk), published via an [OGC SensorThings API](https://www.ogc.org/standards/sensorthings)-compliant [FROST-Server](https://fraunhoferiosb.github.io/FROST-Server/) endpoint (`https://sensors.bgs.ac.uk/FROST-Server/v1.1/`).

## Contents

- **[`sensor-things-api-demo.ipynb`](sensor-things-api-demo.ipynb)** — A Jupyter notebook demonstrating how to query the BGS SensorThings API endpoint with Python (`requests`), process time-series observations (`pandas`, `numpy`), filter outliers, and plot borehole sensor readings (`matplotlib`).
- **[`web-maps/`](web-maps/)** — Standalone browser-based map examples built with Leaflet and OpenLayers showing live sensor locations and interactive time-series charts.

---

## Web Map Examples

You can view the interactive map examples directly in your browser via GitHub Pages or inspect their source code locally:

| Example | Description | Source Code | Live Demo |
| :--- | :--- | :--- | :--- |
| **Leaflet Map** | Displays BGS sensor locations using Leaflet and the [STAM (SensorThings API Map)](https://github.com/DataCoveEU/STAM) plugin. | [`web-maps/leaflet.html`](web-maps/leaflet.html) | [View Online](https://britishgeologicalsurvey.github.io/sensor-things-api-demo/web-maps/leaflet.html) |
| **OpenLayers Map** | Displays BGS sensor locations using OpenLayers and the STAM plugin. | [`web-maps/openlayers.html`](web-maps/openlayers.html) | [View Online](https://britishgeologicalsurvey.github.io/sensor-things-api-demo/web-maps/openlayers.html) |
| **Federated Data Map** | Created as part of the **NERC EDS Amplify** project. Combines live data from multiple SensorThings API endpoints ([BGS Sensors](https://sensors.bgs.ac.uk/FROST-Server/v1.1) and [LinkedSystems](https://linkedsystems.uk/sensorthings/v1.1)) with marker clustering, location search, box zoom, and interactive Plotly time-series charts. | [`web-maps/federated.html`](web-maps/federated.html) | [View Online](https://britishgeologicalsurvey.github.io/sensor-things-api-demo/web-maps/federated.html) |

### Local HTML Development & Previewing

The files in [`web-maps/`](web-maps/) are standalone HTML pages with no build step required. When editing them locally, serving them over a local HTTP server is recommended to avoid browser `file://` CORS restrictions and to match how GitHub Pages serves the files:

#### Option 1: Python Built-in HTTP Server

Run the following command from the repository root:

```bash
python -m http.server 8000
```

Then open any of the maps in your browser (refreshing the page after saving changes):

- Federated Map: [http://localhost:8000/web-maps/federated.html](http://localhost:8000/web-maps/federated.html)
- Leaflet Map: [http://localhost:8000/web-maps/leaflet.html](http://localhost:8000/web-maps/leaflet.html)
- OpenLayers Map: [http://localhost:8000/web-maps/openlayers.html](http://localhost:8000/web-maps/openlayers.html)

#### Option 2: VS Code Live Server (Auto-Reload)

1. Install the **Live Server** (or **Live Preview**) extension in VS Code.
2. Right-click [`web-maps/federated.html`](web-maps/federated.html) in the Explorer panel and select **Open with Live Server**.
3. The page will open in your browser and automatically reload whenever you save edits to the HTML, CSS, or JavaScript.

---

## Running the Jupyter Notebook

You can [view the notebook and its outputs directly on GitHub](sensor-things-api-demo.ipynb), open a mobile-friendly version on [Jupyter nbviewer](https://nbviewer.jupyter.org/github/BritishGeologicalSurvey/sensor-things-api-demo/blob/main/sensor-things-api-demo.ipynb), or run it locally on your machine.

### Prerequisites

- **Python 3.8+** (the notebook uses the `:=` assignment expression introduced in Python 3.8)
- A Python package manager such as `pip` or `conda`

### Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/BritishGeologicalSurvey/sensor-things-api-demo.git
   cd sensor-things-api-demo
   ```

2. *(Optional)* Create and activate a virtual environment:

   ```bash
   python3 -m venv .venv
   # On Linux/macOS:
   source .venv/bin/activate
   # On Windows (PowerShell):
   .venv\Scripts\Activate.ps1
   ```

3. Install the required dependencies:

   ```bash
   pip3 install -r requirements.txt
   ```

### Starting the Notebook

Launch Jupyter Notebook from the repository root:

```bash
jupyter notebook
```

A browser window will open at [http://localhost:8888](http://localhost:8888), where you can open `sensor-things-api-demo.ipynb`.

---

## Testing (For Developers)

To verify that the notebook executes from start to finish without errors, install the development dependencies and run `pytest` with `nbval`:

```bash
pip3 install -r requirements.txt -r requirements_dev.txt
pytest --nbval-lax sensor-things-api-demo.ipynb
```

---

## License

This project is released under the [MIT License](LICENSE). Copyright (c) British Geological Survey.


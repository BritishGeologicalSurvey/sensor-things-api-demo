## SensorThingsAPI demo

This repository contains examples for using the [BGS Sensor Data service](https://sensors.bgs.ac.uk). 

We have included a Jupyter notebook that demonstrates how to query and plot data from a SensorThingsAPI endpoint using Python.
It is posted here to get users started with accessing environmental monitoring data from British Geological Survey sensors.These are published via an OGC SensorThingsAPI-compliant endpoint via the FROST Server software.

We have also included both Leaflet and OpenLayer web map examples:

- Leaflet web map, [view the code](web-maps/leaflet.html), view [online](https://britishgeologicalsurvey.github.io/sensor-things-api-demo/web-maps/leaflet.html)
- Openlayers web map, [view the code](web-maps/openlayers.html), view [online](https://britishgeologicalsurvey.github.io/sensor-things-api-demo/web-maps/openlayers.html)

BGS sensor data are available at [https://sensors.bgs.ac.uk](https://sensors.bgs.ac.uk).

Follow the instructions below to install and run the demonstration Jupyter Notebook on your own
machine.  Alternatively, you can [view the code and results](sensor-things-api-demo.ipynb) in your browser.  Click [here](https://nbviewer.jupyter.org/github/BritishGeologicalSurvey/sensor-things-api-demo/blob/main/sensor-things-api-demo.ipynb) for mobile-friendly version rendered by _Jupyter nbviewer_.

## Federated Data

We have also created a leaflet map to show how we can use data from different sources as part of the NERC EDS Amplify project: 

- Federated data web map, [view the code](web-maps/federated.html), view [online](https://britishgeologicalsurvey.github.io/sensor-things-api-demo/web-maps/federated.html)

## Prerequisites

+ Python 3
+ A Python 3 package manager e.g. pip3, conda

## Installing dependencies


The following packages should be installed via `pip3` or `conda`:

```
pip3 install -r requirements.txt
```

### For developers

To test that the notebook runs to completion, extra packages are required:

```bash
pip3 install -r requirements-dev.txt
```

Run the test with:

```bash
pytest --nbval-lax sensor-things-api-demo.ipynb
```


## Starting the notebook

The demo runs in a Jupyter notebook.  Start the notebook with:

```
jupyter notebook
```

A browser window will open at [http://localhost:8888](http://localhost:8888)
with a list of available notebooks.

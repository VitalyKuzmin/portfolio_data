![alt text](img/8.jpg)

### Urban Lighting Reconstruction Platform

An end-to-end data and ML platform for planning street lighting reconstruction based on field inventory, mobile laboratory measurements, geospatial mapping, and predictive modeling.

**Goal:**
To replace manual field analysis and slow tender preparation with a unified workflow that could collect lighting asset data, map real measurements, predict illuminance, identify problematic zones, and recommend reconstruction options.

**What was built:**
- **Field inventory workflow:** tools for collecting street lighting asset data in the field and storing it in a centralized system.
- **Mobile laboratory processing:** software for processing illuminance, GPS, speed, and sensor data from a vehicle-based measurement laboratory.
- **Geospatial mapping:** visualization of lighting assets and measurement results on an interactive map.
- **ML dataset preparation:** matching inventory and measurement data by GPS coordinates to create a training dataset.
- **Predictive model:** a LightGBM-based model for predicting street illuminance and detecting areas that did not meet lighting requirements.
- **Recommendation logic:** selection of LED replacements and estimation of reconstruction options, economic effect, and payback period.
- **Reporting:** generation of analytical outputs for reconstruction planning and tender documentation.

**Result:**
The project connected several previously separate workflows into a single planning pipeline: data collection, measurement processing, mapping, prediction, and reconstruction analytics. It reduced the need for repeated field measurements and made it faster to prepare accurate reconstruction proposals.

**Stack:**
Python, LightGBM, C++, JavaScript, Electron, Node.js, geospatial data processing, Google Maps API, PostgreSQL/1C.

**My Role:**
I acted as technical lead and full-stack developer. I designed the architecture, developed key data processing components, built the ML dataset and prediction model, and connected field data, measurements, maps, and analytics into one reconstruction planning workflow.

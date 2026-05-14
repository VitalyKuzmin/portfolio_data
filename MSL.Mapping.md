![alt text](img/2.jpg)

### MSL Mapping (analysis and visualization of geodata) | [Project Website](https://vnisi.ru/ispytaniya/mobile/)  

A project carried out as part of a master's thesis in collaboration with the Vavilov All-Russian Research Institute for Light Sources (VNISI). The goal was to develop a system for collecting, processing, and visualizing data from a mobile lighting laboratory (MSL).

**Task:**
To create a software suite that would process binary data from various car sensors (illuminance, speed, GPS), save it to a 1C database, and display it on an interactive web map.

**Architecture and Stack:**
- **Data Collection and Processing:** A **C++/MFC** desktop application for processing raw sensor data.
- **Storage:** Data was transferred to a **1C** database.
- **Visualization:** A web interface using **JavaScript**, **Google Maps API**, and **Bootstrap** retrieved data from 1C via a PHP API and plotted it on the map.

**Result:**
The system made it possible to combine a huge number of measurements on a single map, allowing for the assessment of lighting conditions on the scale of entire cities and conducting global research.

**My Role:**
I was the main developer on the project, responsible for:
- Writing mathematical algorithms.
- Developing the **C++** desktop application.
- Creating the **JavaScript** frontend.
- Partially writing technical specifications and testing.


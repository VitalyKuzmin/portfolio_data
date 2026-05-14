![alt text](img/4.jpg)

### BL Bio (Greenhouse Monitoring) | [Project Website](https://bl-bio.ru)  

A web application for monitoring and managing parameters in greenhouses (lighting, irrigation, fertilizers).

**Task:**
To implement an MVP product for managing "smart" greenhouses under tight deadlines.

**Solution:**
The solution was based on industrial **Wiren Board** controllers, which came with an open-source web application. I customized this application and wrapped it in a web portal with authorization. Users could access their greenhouses, manage parameters, and view video from cameras.

**Architecture and Stack:**
- **Controller:** Wiren Board, communicating with equipment via the Modbus protocol.
- **Backend:** A PHP server that communicated with the controller via MQTT and provided an API for the frontend.
- **Frontend:** A web interface on **Angular**, which I customized.
- **Database:** PostgreSQL for data storage.

**My Role:**
On this project, I acted as a **full-stack developer** and **analyst**. I wrote the technical specifications and customized the PHP backend and Angular frontend to implement the required functionality.

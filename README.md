# Smart Body-Sensor vest
It is a smart body sensor vest, that has a built in many different sensors which can take measurements of your body and then analyse it and visualize it on a website.

### Thanks to Hochschule Furtwangen
It is a school project, hosted by our school Feintechnikschule in Schwenningen and they are in a collaboration with the Hochschule Furtwangen, and they supported us financialy and physically. The teachers there were the best help that we could have. Without them, we would never been able to finish this project.

### Our developer
In our Team, we had 4 members. Each person had been given a specific job to finish.
  - **Team leader** Thinh : Backend- & Frontend-Development, Project Management, Someone that push other's asses to move forward
  - Mirko : Arduino Programming
  - Fynn : 3D designs, electronics wirings
  - Sergkei : Wiring, Electronics, Test-Object

### Demonstration of our project

[https://youtube.com/shorts/DEUS8_lVHP0?feature=share](https://youtube.com/shorts/DEUS8_lVHP0?feature=share)

## How does the vest works?

### Data Flow Pipeline

### Data Collection (Wearable Layer)
- The **user wears the vest**
- Embedded **sensors** (e.g., motion, heart rate, pressure, etc.) collect raw analog signals

### Microcontroller Processing (Edge Layer – Arduino)
- **Arduino Nano**:
  - Reads analog sensor signals
  - Converts signals using **ADC (Analog-to-Digital Converter)**
  - Formats the data (e.g., JSON or structured binary)
  - Sends processed data via **Serial (UART)** to Raspberry Pi

### Gateway Communication (Edge Gateway – Raspberry Pi)
- **Raspberry Pi**:
  - Receives data from Arduino via Serial
  - Optionally preprocesses / validates data
  - Streams data via **UDP** to backend server

### Backend Processing (Server Layer)
- **Server**:
  - Receives UDP data stream
  - Parses and analyzes sensor data
  - Stores data if required (database)
  - Pushes real-time updates to frontend using **WebSocket**

### Visualization (Frontend Layer)
- **Web Application**:
  - Maintains WebSocket connection
  - Receives processed data in real time
  - Displays metrics, charts, and status indicators

## 🏗 Architecture Diagram (Conceptual)

```
[ User ]
↓
[ Smart Vest Sensors ]
↓
[ Arduino Nano ]
(ADC + Serial)
↓
[ Raspberry Pi ]
(UDP Client)
↓
[ Server ]
(Analysis + WebSocket)
↓
[ Frontend Web App ]
(Real-time Visualization)
```

## Code repositories

[Arduino/Raspberry Pi](https://github.com/FTS-SIA-HFU-24-25/arduino)
> Written with Arduino IDE and Python

[Frontend](https://github.com/FTS-SIA-HFU-24-25/frontend)
> Uses SvelteJS framework

[Backend](https://github.com/FTS-SIA-HFU-24-25/backend)
> GoLang as backend server

---
*for development, test purposes*

[UDP Server](https://github.com/FTS-SIA-HFU-24-25/test_udp_server)
> Receives the data and log them into console

[EKG Simulator](https://github.com/FTS-SIA-HFU-24-25/fake-ecg-sensor)
> Send fake ekg datas


Overview
This project combines embedded systems and backend intelligence to support better farming decisions.
It reads live measurements including temperature, humidity, soil moisture, and distance-based water table depth, then analyzes those values to recommend suitable crops and water management actions.

Key Features
Real-time data acquisition from ESP8266
Sensor integration:
DHT22 for temperature and humidity
Soil moisture sensor for soil condition
Ultrasonic sensor for water table depth estimation
Flask API endpoint to receive and process sensor payloads
Crop recommendation based on environmental conditions
Irrigation advisory with water status classification
Dashboard view for latest readings and analysis
Test endpoints and scripts for quick validation
Logging of recent sensor records for monitoring and debugging
System Architecture
ESP8266 reads sensor values at fixed intervals.
Device sends JSON payload to Flask server via HTTP POST.
Flask backend validates data and runs analysis logic.
Server responds with:
Predicted crop
Confidence level
Water status
Irrigation recommendation
Water table estimate
Dashboard and logs display live insights.
Tech Stack
Microcontroller: ESP8266 (NodeMCU)
Firmware: Arduino C++
Backend: Python, Flask
Communication: HTTP, JSON
Testing: Python scripts with requests library
Hardware Requirements
ESP8266 NodeMCU board
DHT22 sensor
Soil moisture sensor
Ultrasonic sensor (for distance/water-depth estimation)
Jumper wires and breadboard
USB cable for programming
Software Requirements
Arduino IDE
Python 3.8 or later
Required Python packages:
flask
requests
Install Python packages:

Project Setup
1) Clone the Repository
2) Run the Flask Server
Use the enhanced server:

Alternative minimal server versions are also available in the project.

3) Configure ESP8266 Firmware
In the ESP8266 sketch, update:

WiFi SSID
WiFi password
Server URL (your local machine IP and port 5000)
Example server endpoint:

4) Upload Firmware
Select board: NodeMCU 1.0 (ESP-12E Module)
Select correct COM port
Upload code and open Serial Monitor at 115200 baud
API Documentation
Endpoint
POST /data

Request Body
The backend also accepts alternate field names such as temperature and moisture in test scenarios.

Success Response (Example)
Available Routes
GET /
Dashboard or health/status view (depending on server file used)

GET or POST /test
Endpoint for connectivity and payload testing

POST /data
Main endpoint for sensor data ingestion and analysis

GET /logs
Returns stored readings and recent logs (enhanced server)

Testing
Run local API tests after starting the Flask server:

These scripts verify:

Server connectivity
JSON ingestion
Crop recommendation behavior across different water table depths
Dashboard integration flow
Use Cases
Smart irrigation scheduling
Crop selection support based on field conditions
IoT agriculture prototyping for academic projects
Demonstration of embedded + backend integration
Future Improvements
Persistent database storage (SQLite or PostgreSQL)
Historical trend visualization
ML model-based crop prediction
Mobile app integration
OTA updates for ESP8266
Role-based dashboard access
Contributing
Contributions are welcome.
Please open an issue for feature requests, bug reports, or suggestions, and submit a pull request with clear commit messages and test notes.

License
No license has been specified yet.
Add a LICENSE file (for example MIT) to define usage and distribution terms.

Author
AquaSense Robot IoT Project
Developed as a smart agriculture automation and advisory system

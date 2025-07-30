# AgrobotiX
Our proposed solution, called "AgrobotiX", is an autonomous agricultural robot designed to help farmers monitor and manage their fields efficiently.

The robot autonomously navigates the farm using a NEO-7M GPS module combined with a HMC5883L digital compass and an MPU9250 IMU sensor for precise tracking and orientation. For obstacle avoidance, three ultrasonic sensors are mounted on the front—one in the center, one on the left, and one on the right—to detect and avoid obstacles in real time.

Using predefined GPS waypoints, the robot systematically travels across the field. It stops every 10 feet to perform soil analysis. A soil moisture sensor, mounted at the rear of the robot, is inserted into the soil with the help of a stepper motor salvaged from an old DVD drive. The moisture content of the soil is then measured. If the moisture level is found to be below a set threshold, the system sends a wireless signal to switch on the irrigation motor located at one end of the field.

While the main ESP32 module handles navigation, sensing, and irrigation control, a secondary ESP32-CAM module is used for crop monitoring. This module, mounted on a pan-tilt servo system, captures images of the crops from different angles. These images are then sent to a local server running a Flask-based machine learning model, which analyzes the images to identify the health status of the crops and detect any signs of disease.

In addition, a DHT11 sensor continuously measures the temperature and humidity of the field. An NPK sensor is installed at fixed locations in the field to measure soil nutrients (Nitrogen, Phosphorus, and Potassium).

All collected data—soil moisture, nutrient levels, temperature, humidity, and the results from the machine learning model—are displayed on a web dashboard or mobile application. If the system detects an unhealthy crop, the dashboard highlights the image of the diseased crop along with its GPS coordinates. The app also provides regional language support to make it more accessible and user-friendly for farmers.

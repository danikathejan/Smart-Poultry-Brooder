# Smart-Poultry-Brooder

<img src="Assets\group photo.jpg"></img>

## Introduction
A poultry brooder serves as a chick's first home, providing essential care during the early, vulnerable stages of their life. Ensuring proper nurturing and protection is crucial for their healthy development. The Smart Poultry Brooder project was designed to create a safe, controlled environment that is continuously monitored. By integrating sensors and actuators, the system can automatically regulate key environmental parameters, ensuring optimal conditions for the chicks while providing real-time feedback to maintain consistent monitoring and adjustments.

## Features
- Real-time monitoring of temperature and humidity levels.
- Automated control actions to maintain optimal temperature and humidity.
- Measurement of water intake with automated tank refilling based on consumption.
- Monitoring and tracking of feed intake.
- Daily records of water and feed intake logged in Excel for further analysis.
- User Friendly Dashboard

## Components
- NI DAQ mx
- Rigol DP900 Variable DC Power Supply
- LM35 Analog Temperature and Humidity Sensor
- Thin Film Pressure Sensor 1Kg
- 12V DC Fan
- 12V 35W Halogen Lamp
- Custom built water level sensor
- 5V DC water pump

## User Interface and Sequence of Operation

<img src="Assets\Labview Dashboard.png"></img>

The farmer can easily monitor environmental parameters, such as temperature and humidity, through the system's dashboard. It also displays whether any control sequences are currently active. Typically, real-time monitoring and control operate during the day. At the end of each day (after a predetermined number of hours), the system records the amount of food and water consumed by the poultry. This data is automatically logged in an Excel file, which also includes historical data, providing valuable insights into the health and feeding patterns of the poultry.

At the start of each day, the farmer cleans the food bowl and refills it with a set amount of food for the poultry to consume. The water tank is refilled automatically by the system using a water pump, maintaining the water level at a preset value.

## LabVIEW Control

<img src="Assets\Block diagram.png"></img>

The LabVIEW structure for the system is designed using a flat sequence, aligning with the operational flow. The initial frame of the flat sequence handles real-time control during the day. Once the day ends, the sequence continues by taking readings, logging the data into Excel, and performing necessary reset actions before the start of the next day.

Special considerations include:
- **Weight Sensor Measurement**: A moving average filter is applied to reduce fluctuations and provide a more stable reading.
- **Water Level Sensor**: Dual scales are used to determine water levels accurately, as turbulence in the water flow affects the voltage readings from the DAQmx.

## License

This project is licensed under the MIT License. See the [LICENSE](https://choosealicense.com/licenses/mit/) file for more details.

# Digital Light & Proximity Sensor LTR-507

## Product Overview

![Product Image](https://github.com/user-attachments/assets/a7c0acc0-3331-4894-9643-fd69a40bc911)
**SKU:** 333063  
[Product Page](https://soldered.com/product/digital-light-proximity-sensor-ltr-507-breakout/)  
[Soldered Page](https://soldered.com/)

The **LTR-507** is a digital light and proximity sensor designed for accurate ambient light measurement and object proximity detection. It integrates advanced optical filtering and signal processing to ensure reliable performance across various lighting conditions.

### Features

- Dual-function sensor for ambient light and proximity measurement
- High sensitivity and low power consumption
- I2C communication interface
- Compact breakout board design for easy integration

---

## How It Works

The **LTR-507** sensor operates using two main detection principles:

1. **Ambient Light Sensing:**

- The LTR-507 has two photodiodes: one sensitive to visible light and the other to infrared (IR) light.

- By measuring the intensity of both visible and IR light, it can approximate human eye perception and filter out unwanted IR noise.

- The ambient light sensing function provides a digital output proportional to the ambient light level, which is useful for applications like automatic screen brightness adjustment.

2. **Proximity Sensing:**

- The sensor includes an infrared LED and a proximity photodiode.

- Emits infrared light and measures the reflected signal to determine object distance. Commonly used in touchless interfaces and object detection.

- The reflected IR light is detected by the proximity photodiode.

---

## Arduino: Getting Started

### Prerequisites

- **Arduino IDE** ([Download](https://www.arduino.cc/en/software))
- **LTR-507 Arduino Library** ([GitHub](https://github.com/SolderedElectronics/Soldered-Digital-Light-Sensor-Arduino-Library))
- **Dasduino Board Definitions** ([GitHub](https://github.com/SolderedElectronics/Dasduino-Board-Definitions-for-Arduino-IDE))

### Wiring Guide

Connect the sensor to an Dasduino board as follows:

| Sensor Pin | Arduino Pin |
| ---------- | ----------- |
| VCC        | 3.3V / 5V   |
| GND        | GND         |
| SDA        | A4 (SDA)    |
| SCL        | A5 (SCL)    |

### Installing the Library

1. Download our LTR-507 Arduino Library ([GitHub](https://github.com/SolderedElectronics/Soldered-Digital-Light-Sensor-Arduino-Library)) as a ZIP.
   ![Image](https://github.com/user-attachments/assets/67136570-a2f9-49fb-8255-278899bf721c)
2. Open **Arduino IDE**.
3. Go to **Sketch** > **Include Library** > **Add .ZIP Library**.
   ![Image](https://github.com/user-attachments/assets/fa5b396f-fc7b-48b6-a862-4dfd5d8ac04b)

4. Go to **Sketch** > **Include Library** > **Select our LTR-507 Arduino Library**
   ![Image](https://github.com/user-attachments/assets/c4fbc51c-af17-4fe7-b212-f7b0a8b33d3c)

---

## Arduino: Basic Example

Here’s a simple example to read light and proximity values from the sensor:

````cpp
//include our library for LTR-507
#include <LTR-507-Light-And-Proximity-Sensor-SOLDERED.h>

// Create sensor object
LTR507 sensor;

void setup() {


  Serial.begin(9600);

  // Initialize the sensor!
    sensor.init();
}

// the loop function runs over and over again forever
void loop() {
  // Make local variables for reading the light and proximity value
    uint16_t lightReading;
    uint16_t proximityReading;

    // Make reading!
    lightReading = sensor.getLightIntensity();
    proximityReading = sensor.getProximity();

    // Print the light reading
    Serial.print("Light sensor reading: ");
    Serial.println(lightReading);

    // Wait a bit until the next reading so output isn't too fast
    delay(1000);


    // Print proximity reading
    Serial.print("Proximity sensor reading: ");
    Serial.println(proximityReading);

     // Wait a bit until the next reading so output isn't too fast
    delay(1000);
}````

### Running the Code

1. Connect your sensor and board as per the wiring guide or using easy c.
2. Upload the above code to your **Dasduino**.
3. Open the **Serial Monitor** to view real-time readings.

![Serial Monitor Output](https://github.com/user-attachments/assets/289673f1-2b42-44b1-bcfa-66608f088347)

---

## Additional Resources

- [Dasduino Board Definitions](https://github.com/SolderedElectronics/Dasduino-Board-Definitions-for-Arduino-IDE)
- [LTR-507 Arduino Library](https://github.com/SolderedElectronics/Soldered-Digital-Light-Sensor-Arduino-Library)
- [Example Projects](https://tested-amusement.surge.sh/)



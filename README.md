# Digital Light & Proximity Sensor LTR-507 

## Product Overview

![Product Image]("https://github.com/DZovko/LTR-507ALS/blob/0647668b353c34f37fcc419df64b41ef8f1241f0/LTR-507.jpg")  
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

1. **Ambient Light Sensing:** Detects visible and infrared light to measure environmental brightness. Useful for automatic screen brightness control and energy-saving applications.
2. **Proximity Sensing:** Emits infrared light and measures the reflected signal to determine object distance. Commonly used in touchless interfaces and object detection.

![Sensor Functionality](./images/how-it-works.png)



---

## Arduino: Getting Started

### Prerequisites
- **Arduino IDE** ([Download](https://www.arduino.cc/en/software))
- **LTR-507 Arduino Library** ([GitHub](https://github.com/SolderedElectronics/Soldered-Digital-Light-Sensor-Arduino-Library))
- **Dasduino Board Definitions** ([GitHub](https://github.com/SolderedElectronics/Dasduino-Board-Definitions-for-Arduino-IDE))

### Wiring Guide
Connect the sensor to an Arduino-compatible board as follows:

| Sensor Pin | Arduino Pin |
|------------|------------|
| VCC        | 3.3V / 5V  |
| GND        | GND        |
| SDA        | A4 (SDA)   |
| SCL        | A5 (SCL)   |

### Installing the Library
1. Open **Arduino IDE**.
2. Go to **Sketch** > **Include Library** > **Manage Libraries**.
3. Search for **LTR-507 Light and Proximity Sensor**.
4. Click **Install**.

---

## Arduino: Basic Example

Here’s a simple example to read light and proximity values from the sensor:

```cpp
#include <Wire.h>
#include <LTR507.h>

LTR507 sensor;

void setup() {
    Serial.begin(115200);
    sensor.begin();
}

void loop() {
    Serial.print("Ambient Light: ");
    Serial.print(sensor.readAmbientLight());
    Serial.print(" lx, Proximity: ");
    Serial.println(sensor.readProximity());
    delay(1000);
}
```

### Running the Code
1. Connect your sensor and board as per the wiring guide.
2. Upload the above code to your **Dasduino**.
3. Open the **Serial Monitor** to view real-time readings.

![Serial Monitor Output](./images/serial-monitor.png)

---

## Additional Resources
- [Dasduino Board Definitions](https://github.com/SolderedElectronics/Dasduino-Board-Definitions-for-Arduino-IDE)
- [LTR-507 Arduino Library](https://github.com/SolderedElectronics/Soldered-Digital-Light-Sensor-Arduino-Library)
- [Example Projects](https://tested-amusement.surge.sh/)

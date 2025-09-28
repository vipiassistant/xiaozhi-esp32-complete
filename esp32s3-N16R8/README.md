# 📋 BẢNG CẤU HÌNH CHÂN XIAOZHI ESP32-S3

## 🛠️ TỔNG QUAN
- **Bo mạch:** ESP32-S3 (ESP32-N16R8)  
- **Flash:** 16MB  
- **PSRAM:** 8MB  
- **Wi-Fi:** Access Point (SSID: ViPi-XXXX)  
- **Hotword:** "Vi Bi"  
- **Thiết bị ngoại vi:** Microphone ICS43434, Amp MAX98357A, OLED SSD1306, LED WS2812 (16 LED), Touch Buttons  

---

## 🎤 MICROPHONE (ICS43434 – I2S Input)

| Chức năng | GPIO   | Mô tả         | Kết nối    | Nguồn |
|-----------|--------|---------------|------------|-------|
| VDD       | -      | Nguồn cấp     | 3V3        | 3V3   |
| GND       | -      | Mass chung    | GND        | GND   |
| WS        | GPIO4  | Word Select   | ICS43434 WS| 3V3   |
| SCK       | GPIO5  | Serial Clock  | ICS43434 BCLK | 3V3 |
| DIN       | GPIO6  | Data Input    | ICS43434 Data | 3V3 |

---

## 🔊 LOA / AMP (MAX98357A – I2S Output)

| Chức năng | GPIO   | Mô tả         | Kết nối      | Nguồn |
|-----------|--------|---------------|--------------|-------|
| VDD       | -      | Nguồn cấp     | 5V           | 5V    |
| GND       | -      | Mass chung    | GND          | GND   |
| DIN       | GPIO7  | Data Output   | MAX98357A DIN| 5V    |
| BCLK      | GPIO15 | Speaker Clock | MAX98357A BCLK| 5V   |
| LRCK      | GPIO16 | Speaker WS    | MAX98357A LRCK| 5V   |

---

## 🖥️ DISPLAY OLED (SSD1306 – 128x64 I2C)

| Chức năng | GPIO   | Mô tả     | Kết nối | Nguồn |
|-----------|--------|-----------|---------|-------|
| VDD       | -      | Nguồn cấp | 3V3     | 3V3   |
| GND       | -      | Mass chung| GND     | GND   |
| SDA       | GPIO41 | I2C Data  | OLED SDA| 3V3   |
| SCL       | GPIO42 | I2C Clock | OLED SCL| 3V3   |
| Address   | -      | I2C Addr  | 0x3C    | 3V3   |

---

## 🌈 LED WS2812 (16 LED)

| Chức năng | GPIO   | Mô tả          | Kết nối  | Nguồn |
|-----------|--------|----------------|----------|-------|
| VDD       | -      | Nguồn cấp      | 5V       | 5V    |
| GND       | -      | Mass chung     | GND      | GND   |
| DIN       | GPIO21 | Data In        | WS2812   | 5V    |

---

## 📱 TOUCH BUTTONS (Capacitive)

| Chức năng | GPIO   | Touch Pad | Mô tả           |
|-----------|--------|-----------|-----------------|
| CALL      | GPIO1  | T1        | Nút cảm ứng gọi |
| VOL+      | GPIO2  | T2        | Tăng âm lượng   |
| VOL-      | GPIO3  | T3        | Giảm âm lượng   |

---

## 🔘 BUTTONS & TEST LED

| Chức năng | GPIO   | Mô tả          | Kết nối       |
|-----------|--------|----------------|---------------|
| BOOT      | GPIO0  | Boot Button    | Button to GND |
| LED       | GPIO21 | Built-in LED   | LED + Resistor|
| LAMP      | GPIO18 | MCP Test       | LED/Relay     |

---

## ⚡ POWER & SYSTEM

| Chức năng | GPIO | Mô tả   |
|-----------|------|---------|
| 3.3V      | -    | Nguồn   |
| 5V        | -    | Nguồn   |
| GND       | -    | Mass    |
| EN        | -    | Enable  |
| RST       | -    | Reset   |

---

## 🔧 CẤU HÌNH AUDIO

| Thông số           | Giá trị   |
|--------------------|-----------|
| Input Sample Rate  | 16kHz     |
| Output Sample Rate | 24kHz     |
| Channels           | Mono      |
| Bit Depth          | 16-bit    |

---

## 📡 WI-FI CONFIGURATION

| Thông số    | Giá trị            |
|-------------|--------------------|
| AP SSID     | ViPi-XXXX          |
| AP Password | (Open)             |
| Web Config  | http://192.168.4.1 |
| Channel     | Auto               |
| Country     | VN                 |

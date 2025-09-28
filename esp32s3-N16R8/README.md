# 📋 BẢNG CẤU HÌNH CHÂN XIAOZHI ESP32-S3

## 🛠️ TỔNG QUAN
- **Bo mạch:** ESP32-S3  
- **Flash:** 16MB  
- **PSRAM:** 8MB  
- **Wi-Fi:** Access Point (ViPi-XXXX)  

---

## 🎤 AUDIO I2S (Simplex Mode)

| Chức năng | GPIO  | Mô tả         | Kết nối             |
|-----------|-------|---------------|---------------------|
| MIC_WS    | GPIO4 | Word Select   | Microphone WS       |
| MIC_SCK   | GPIO5 | Serial Clock  | Microphone BCLK     |
| MIC_DIN   | GPIO6 | Data Input    | Microphone Data     |
| SPK_DOUT  | GPIO7 | Data Output   | Speaker Data        |
| SPK_BCLK  | GPIO15| Speaker Clock | Speaker BCLK        |
| SPK_LRCK  | GPIO16| Speaker WS    | Speaker LRCK        |

---

## 🖥️ DISPLAY OLED (I2C)

| Chức năng | GPIO   | Mô tả     | Kết nối    |
|-----------|--------|-----------|------------|
| SDA       | GPIO41 | I2C Data  | OLED SDA   |
| SCL       | GPIO42 | I2C Clock | OLED SCL   |
| Address   | 0x3C   | I2C Addr  | OLED Addr  |

---

## 🔘 BUTTONS & LED 

| Chức năng | GPIO   | Mô tả          | Kết nối        |
|-----------|--------|----------------|----------------|
| BOOT      | GPIO0  | Boot Button    | Button to GND  |
| LED       | GPIO21 | Built-in LED   | LED + Resistor |
| LAMP      | GPIO18 | MCP Test       | LED/Relay      |

---

## 📱 TOUCH BUTTONS (Capacitive)

| Chức năng | GPIO   | Touch Pad | Mô tả          |
|-----------|--------|-----------|----------------|
| CALL      | GPIO1  | T1        | Nút gọi        |
| VOL+      | GPIO2  | T2        | Tăng âm lượng  |
| VOL-      | GPIO3  | T3        | Giảm âm lượng  |

---

## ⚡ POWER & SYSTEM

| Chức năng | GPIO | Mô tả   |
|-----------|------|---------|
| 3.3V      | -    | Nguồn   |
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

| Thông số   | Giá trị             |
|------------|---------------------|
| AP SSID    | ViPi-XXXX           |
| AP Password| (Open)              |
| Web Config | http://192.168.4.1 |
| Channel    | Auto                |
| Country    | VN                  |

---

## 🎯 SƠ ĐỒ KẾT NỐI
✅ Bảng cấu hình chân hoàn chỉnh cho dự án Xiaozhi ESP32-S3!  

---

## 📝 HƯỚNG DẪN SỬ DỤNG
- Kết nối **Microphone**: GPIO4 (WS), GPIO5 (SCK), GPIO6 (DIN)  
- Kết nối **Speaker**: GPIO7 (DOUT), GPIO15 (BCLK), GPIO16 (LRCK)  
- Kết nối **OLED**: GPIO41 (SDA), GPIO42 (SCL)  
- **Touch Buttons**: GPIO1 (CALL), GPIO2 (VOL+), GPIO3 (VOL-)  
- Flash firmware và kết nối Wi-Fi AP để cấu hình  

---

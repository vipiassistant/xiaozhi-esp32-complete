# Xiaozhi ESP32 Complete Build

📂 **Source code (chưa build):**  
[Tải tại đây](https://drive.google.com/file/d/1fuKec7o9IY3vzQojOilSiP1SKOv6T6oY/view?usp=sharing)

---

## ℹ️ Thông tin build

| Thuộc tính       | Giá trị                  |
|------------------|--------------------------|
| **Version**      | v2.0.2                   |
| **ESP-IDF**      | v5.5                     |
| **Target**       | ESP32-S3                 |
| **Flash**        | 16MB                     |
| **PSRAM**        | 8MB                      |
| **Wi-Fi**        | AP (SSID: ViPi-XXXX)     |
| **Hotword**      | "Vi Bi"                  |
| **Audio Codec**  | 16kHz / 24kHz            |
| **Display**      | OLED SSD1306 (128x64)    |
| **Server**       | MCP server               |

---

## 📋 Quy tắc đặt tên firmware

| Định dạng tên                           | Thành phần                                |
|-----------------------------------------|-------------------------------------------|
| `<Chip>-<Flash+PSRAM>-<Kết nối>-<Màn hình>-<Hotword>-<Phiên bản>` | Công thức ghép tên firmware |

**Ví dụ:**  
`S3-16R8-WIFI-OLED128X64-ViBi-V2.0.2`  

| Thành phần    | Ý nghĩa                           |
|---------------|-----------------------------------|
| **S3**        | ESP32-S3 (loại chip)              |
| **16R8**      | 16MB Flash + 8MB PSRAM            |
| **WIFI**      | Hỗ trợ Wi-Fi (AP/STA)             |
| **OLED128X64**| Màn hình OLED SSD1306 (128x64)    |
| **ViBi**      | Hotword tùy chỉnh *"Vi Bi"*       |
| **V2.0.2**    | Phiên bản firmware                |

---

## 🔧 Nạp bằng Espressif Easy Flash Web

| Bước | Hành động                                                                 |
|------|---------------------------------------------------------------------------|
| 1    | Kết nối **ESP32-S3** với máy tính qua cáp USB                             |
| 2    | Truy cập [Espressif Easy Flash Web](https://espressif.github.io/esptool-js/) |
| 3    | Chọn **Chip**: `ESP32-S3`                                                 |
| 4    | Upload từng file firmware với địa chỉ sau:                                |

| File                  | Địa chỉ   |
|-----------------------|-----------|
| `bootloader.bin`      | `0x0`     |
| `partition-table.bin` | `0x8000`  |
| `xiaozhi.bin`         | `0x20000` |

| Bước | Hành động                         |
|------|-----------------------------------|
| 5    | Nhấn **Program** để nạp           |
| 6    | Hoàn tất → Nhấn **Reset** để chạy |

---
<img width="2630" height="1514" alt="image" src="https://github.com/user-attachments/assets/bec38636-f41c-4e58-a8f7-91b1f897912b" />
## 🎉 Chúc bạn nạp thành công!





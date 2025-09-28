# Xiaozhi ESP32 Complete Build
## Tải file code đã edit đầy đủ tại đây: https://drive.google.com/file/d/1fuKec7o9IY3vzQojOilSiP1SKOv6T6oY/view?usp=sharing
## Thông tin build
- **Version**: v2.0.2
- **ESP-IDF version**: v5.5
- **Target**: ESP32-S3
- **Flash size**: 16MB
- **PSRAM**: 8MB

## Tính năng
- Wi-Fi Access Point (ViPi-XXXX)
- Custom wake word (Vi Bi)
- Audio codec 16kHz/24kHz
- OLED display
- MCP server

---

## NẠP BẰNG ESPRESSIF EASY FLASH WEB
## Truy cập
Mở trình duyệt và vào công cụ chính thức:  
👉 [Espressif Easy Flash Web](https://espressif.github.io/esptool-js/)

## Cách nạp
1. Kết nối **ESP32-S3** với máy tính qua cáp **USB**.  
2. Chọn **Chip**: `ESP32-S3`.  
3. Upload từng file firmware với địa chỉ tương ứng:  

| File                | Địa chỉ   |
|---------------------|-----------|
| `bootloader.bin`    | `0x0`     |
| `partition-table.bin` | `0x8000`  |
| `xiaozhi.bin`       | `0x20000` |

4. Nạp file theo đúng địa chỉ.  
5. Sau khi hoàn tất, nhấn **Reset** trên board để khởi động lại.  
<img width="2630" height="1514" alt="image" src="https://github.com/user-attachments/assets/bec38636-f41c-4e58-a8f7-91b1f897912b" />
## Chúc bạn thành công!
---


# 🚀 Hướng dẫn nạp firmware ESP32-S3

## 📁 Các file firmware

| File | Địa chỉ | Mô tả | Kích thước |
|------|---------|-------|------------|
| `bootloader.bin` | `0x0` | Bootloader | 16.1 KB |
| `partition-table.bin` | `0x8000` | Bảng phân vùng | 3.0 KB |
| `ota_data_initial.bin` | `0xd000` | Dữ liệu OTA | 8.0 KB |
| `xiaozhi.bin` | `0x20000` | Ứng dụng chính | 3.0 MB |
| `generated_assets.bin` | `0x800000` | Tài nguyên âm thanh | 2.9 MB |

## ⚙️ Cài đặt flash

- **Flash Mode**: DIO
- **Flash Frequency**: 80MHz
- **Flash Size**: 16MB
- **Chip**: ESP32-S3

## 🔧 Các tool có thể sử dụng

### 1. ESP32 Flash Download Tool (Khuyến nghị)

1. Tải ESP32 Flash Download Tool từ Espressif
2. Mở tool và chọn:
   - **Chip Type**: ESP32-S3
   - **WorkMode**: Develop
   - **LoadMode**: UART0
3. Thêm các file với địa chỉ tương ứng
4. Chọn COM port và baudrate (115200)
5. Nhấn **START** để bắt đầu nạp

### 2. esptool.py (Command line)

```bash
esptool.py --chip esp32s3 --port COM3 --baud 115200 \
  --before default_reset --after hard_reset write_flash \
  --flash_mode dio --flash_freq 80m --flash_size 16MB \
  0x0 bootloader.bin \
  0x8000 partition-table.bin \
  0xd000 ota_data_initial.bin \
  0x20000 xiaozhi.bin \
  0x800000 generated_assets.bin
```

### 3. PlatformIO

```ini
[env:esp32s3]
platform = espressif32
board = esp32-s3-devkitc-1
framework = espidf
monitor_speed = 115200
upload_speed = 115200
```

### 4. Arduino IDE

1. Cài đặt ESP32 board package
2. Chọn board: ESP32S3 Dev Module
3. Upload speed: 115200
4. Sử dụng ESP32 Sketch Data Upload tool

## 🎯 Tính năng đã cải tiến

### ✅ Hotword Detection
- **"Vi Bi"** → Âm thanh xác nhận → Chờ lệnh
- Không phản hồi tự động khi hotword được detect

### ✅ Music Playback
- **"phát nhạc ABC"** → Phát nhạc ngay lập tức
- Hiển thị tên bài hát trên màn hình
- Không có TTS response thừa

### ✅ Smart Response
- Chỉ phản hồi khi có lệnh rõ ràng
- Âm thanh completion khi TTS hoàn thành
- Im lặng với input không hợp lệ (như "PBA", "BBA")

### ✅ Music Control
- Hotword dừng nhạc ngay lập tức
- Call button dừng nhạc với callback
- Không có âm thanh completion khi music đang phát

## 🔍 Troubleshooting

### Lỗi kết nối
- Kiểm tra COM port
- Thử baudrate khác (921600, 460800, 115200)
- Nhấn nút RESET trước khi nạp

### Lỗi flash
- Kiểm tra cài đặt flash mode (DIO)
- Đảm bảo flash size đúng (16MB)
- Thử giảm baudrate xuống 115200

### Lỗi boot
- Kiểm tra partition table
- Đảm bảo bootloader đúng
- Kiểm tra OTA data



**🎵 Chúc bạn sử dụng vui vẻ!**

# 🚀 Hướng dẫn nạp firmware ESP32-S3

## 📁 File firmware đã merge

| File | Địa chỉ | Mô tả |
|------|---------|-------|
| `xiaozhi_complete_firmware.bin` | `0x0` | Firmware hoàn chỉnh (bootloader + partition + app + assets) |

## 🎯 Tính năng đã cải tiến

### ✅ Hotword Detection
- **"Vi Bi"** → Âm thanh xác nhận → Chờ lệnh
- Không phản hồi tự động khi hotword được detect
- Chuyển sang listening mode ngay lập tức

### ✅ Music Playback
- **"phát nhạc ABC"** → Phát nhạc ngay lập tức
- Hiển thị tên bài hát trên màn hình: `♪ Tên Bài Hát`
- Không có TTS response thừa
- **Immediate playback** khi đang nói

### ✅ Smart Response
- Chỉ phản hồi khi có lệnh rõ ràng
- Âm thanh completion khi TTS hoàn thành
- Im lặng với input không hợp lệ (như "PBA", "BBA")

### ✅ Music Control
- Hotword dừng nhạc ngay lập tức
- Call button dừng nhạc với callback
- Không có âm thanh completion khi music đang phát

### ✅ Server Connection
- **OTA Server**: `https://api.tenclass.net/xiaozhi/ota/`
- **Music Server**: `http://www.xiaozhishop.xyz:5005`
- Log hiển thị server đang kết nối

## 🔧 Cách nạp firmware

### Option 1: ESP32 Flash Download Tool
1. Mở **ESP32 Flash Download Tool**
2. Chọn **ESP32-S3**
3. Load file: `xiaozhi_complete_firmware.bin`
4. Địa chỉ: `0x0`
5. Bấm **START**

### Option 2: esptool.py
```bash
esptool.py --chip esp32s3 --port COM3 --baud 460800 write_flash 0x0 xiaozhi_complete_firmware.bin
```

### Option 3: ESP-IDF
```bash
idf.py -p COM3 flash
```

## 🎵 Cách sử dụng

### 1. Khởi động
- Bật thiết bị → Chờ âm thanh "success"
- Màn hình hiển thị thông tin thiết bị

### 2. Phát nhạc
- Nói: **"Vi Bi"** (hotword)
- Chờ âm thanh xác nhận
- Nói: **"phát nhạc [tên bài hát]"**
- Nhạc sẽ phát ngay lập tức

### 3. Dừng nhạc
- Nói: **"Vi Bi"** → Nhạc dừng, chuyển sang listening
- Hoặc bấm **Call button** → Nhạc dừng

## 🔍 Troubleshooting

### ❌ Không phát nhạc
- Kiểm tra kết nối WiFi
- Kiểm tra log: `🎵 Connecting to music server`
- Thử bài hát khác

### ❌ Không nhận lệnh
- Nói rõ ràng: **"phát nhạc [tên bài]"**
- Đợi âm thanh xác nhận hotword
- Kiểm tra log: `Valid command detected`

### ❌ Music bị dừng sớm
- Không bấm call button khi đang phát nhạc
- Đợi 1-2 giây sau khi bắt đầu phát

## 📊 Log quan trọng

```
I (xxxx) Application: 🎤 Hotword detected - Switching to listening mode only
I (xxxx) Application: Valid command detected: 'phát nhạc ABC' contains 'phát'
I (xxxx) Esp32Music: 🎵 Connecting to music server: http://www.xiaozhishop.xyz:5005
I (xxxx) Application: Immediate music playback - no TTS response needed
I (xxxx) Esp32Music: Displaying song name: ♪ Tên Bài Hát
```

## 🎯 Thay đổi mới nhất

### 1. 🎵 Immediate Music Playback
- Khi đang nói mà nhận lệnh phát nhạc
- Dừng TTS ngay lập tức
- Phát nhạc ngay không hỏi lại
- Log: `Immediate music playback - no TTS response needed`

### 2. 🔇 Silent Response
- Return: `{"success": true, "silent": true}`
- Không có TTS response khi phát nhạc
- Chỉ phát nhạc trực tiếp

### 3. ⚡ Faster Response
- Tăng delay: 500ms để tránh race condition
- Immediate state change sang idle
- No confirmation needed

## 🎵 Chúc bạn sử dụng vui vẻ!

---
**Firmware Version**: 2.0.3  
**Build Date**: 15~10-2025  
**Server**: api.tenclass.net + xiaozhishop.xyz

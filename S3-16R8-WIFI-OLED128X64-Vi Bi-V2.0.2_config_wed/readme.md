# Xiaozhi ESP32-S3 R16N8 – WebConfig (Hotword + OLED SSD1306)

Bản build tùy chỉnh dành cho **ESP32-S3 R16N8** (Flash 16MB, PSRAM 8MB) với các tính năng chính:
- ✅ Đổi **hotword trực tiếp trên giao diện web**
- ✅ Tuỳ biến văn bản hiển thị & độ nhạy phát hiện
- ✅ Hỗ trợ **màn hình OLED SSD1306 128×64 (I2C)**
- 🔒 Chức năng chỉnh GPIO qua web **tạm thời vô hiệu hóa để tránh crash**

---

## ✅ 1. Phần cứng yêu cầu

| Thành phần     | Thông số              |
|----------------|------------------------|
| Chip           | ESP32-S3              |
| Flash          | 16MB                  |
| PSRAM          | 8MB                   |
| Màn hình OLED  | SSD1306 128×64 (I2C)  |
| Audio Input    | MIC I2S               |
| Audio Output   | Loa/I2S DAC           |
| LED trạng thái | Tuỳ chọn              |

---

## ✅ 2. Tính năng nổi bật

### 🔹 Cấu hình Hotword qua Web
- Nhập hotword tuỳ ý (vd: `ok google`, `hey mia`, `vi pi`…) LƯU Ý CHỈ HỖ TRỢ TIẾNG ANH
- Chỉnh độ nhạy phát hiện
- Test trực tiếp trên web
- Hiển thị văn bản phản hồi

### 🔹 Chỉnh GPIO tạm tắt để tránh lỗi
Chức năng thay đổi GPIO qua giao diện web đang được vô hiệu hóa.  
Lý do: Nhập sai chân có thể gây crash hệ thống.  
Các chân đang được cố định sẵn trong firmware.

### 🔹 Màn hình OLED SSD1306 (I2C)
- Kích thước: **128×64**
- Giao tiếp: **I2C**
- Hiển thị:
  - Trạng thái hotword
  - Câu phản hồi
  - Thông báo khởi động / kết nối

---

## ✅ 3. Flash firmware

### Cách 1 – ESP Web Flash
1. Kết nối ESP32-S3 vào máy tính
2. Mở: `https://espressif.github.io/esptool/`
3. Chọn chip `ESP32-S3`
4. Nạp file `.bin`
5. Reset thiết bị

### Cách 2 – esptool.py
```bash
esptool.py --chip esp32s3 -p COMx -b 460800 write_flash \
0x0000 bootloader.bin \
0x8000 partition-table.bin \
0x20000 xiaozhi.bin

![z7065630347593_81756aa9a24ba88f1761ca579043d0d0](https://github.com/user-attachments/assets/acc1e07f-bf54-4bba-8c61-5200edf53a0a)
![z7065630346837_616440d8e83d1d33c895a9dc93b12505](https://github.com/user-attachments/assets/3010f0a4-ed1c-4970-9992-4457cc7522cc)
![z7065630360037_6e6c3208f1c5270e28b8438f07593839](https://github.com/user-attachments/assets/f8c862b5-0eb2-4bb3-a796-5352a45cf494)








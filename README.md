# ⏰ Auto Cron Job Runner (cron-auto)

<p align="center">
  <img src="https://img.shields.io/badge/Language-Python%203-blue.svg?style=for-the-badge&logo=python" alt="Python 3" />
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-brightgreen.svg?style=for-the-badge" alt="Platform" />
  <img src="https://img.shields.io/badge/License-MIT-purple.svg?style=for-the-badge" alt="MIT License" />
  <img src="https://img.shields.io/badge/Status-Active-success.svg?style=for-the-badge" alt="Active" />
</p>

Một công cụ tự động gửi request HTTP GET định kỳ (Cron Job) theo danh sách URL định sẵn trong file cấu hình `cron.txt`. Hỗ trợ chạy trực tiếp trên Windows không cần cài Python (`Main.exe`) hoặc chạy mã nguồn Python (`Main.py`) trên mọi hệ điều hành (Linux, macOS, Windows).

---

## 📑 Mục lục / Table of Contents
- [Tính năng nổi bật / Key Features](#-tính-năng-nổi-bật--key-features)
- [Cấu hình danh sách URL / Configuration](#-cấu-hình-danh-sách-url--configuration)
- [Hướng dẫn sử dụng / Usage Guide](#-hướng-dẫn-sử-dụng--usage-guide)
  - [1. Dành cho Windows (Không cần cài Python)](#1-dành-cho-windows-không-cần-cài-python)
  - [2. Dành cho Linux / macOS / Windows (Python script)](#2-dành-cho-linux--macos--windows-python-script)
  - [3. Chạy ngầm 24/7 trên Linux VPS (PM2 / Screen / Nohup)](#3-chạy-ngầm-247-trên-linux-vps-pm2--screen--nohup)
- [Tùy chỉnh thời gian lặp / Custom Interval](#-tùy-chỉnh-thời-gian-lặp--custom-interval)
- [Giấy phép / License](#-giấy-phép--license)

---

## 🌟 Tính năng nổi bật / Key Features

- **⚡ Siêu nhẹ & Dễ dùng**: Chỉ cần dán các đường link URL vào file `cron.txt` và khởi chạy.
- **🖥️ Sẵn sàng cho Windows**: Tích hợp sẵn file thực thi độc lập `Main.exe` (chạy ngay không cần cài đặt Python).
- **🐧 Đa nền tảng (Cross-platform)**: Chạy hoàn hảo trên Linux VPS (Ubuntu, Debian, CentOS), macOS và Windows.
- **📊 Theo dõi trực quan**: Hiển thị số phiên (`Phiên: x`), URL đang gọi, và nội dung phản hồi (`Response`) thời gian thực trên màn hình console.
- **🔄 Vòng lặp tự động**: Tự động thực thi tuần tự tất cả các link và lặp lại sau mỗi chu kỳ (mặc định 60 giây).

---

## ⚙️ Cấu hình danh sách URL / Configuration

Mở file `cron.txt` bằng bất kỳ trình soạn thảo văn bản nào (Notepad, VS Code, Nano...) và điền các đường link cần chạy cron, mỗi URL trên một dòng riêng biệt:

```text
https://your-website.com/cron.php
https://api.yourdomain.com/tasks/sync
https://my-app.onrender.com/ping
```

---

## 🚀 Hướng dẫn sử dụng / Usage Guide

### 1. Dành cho Windows (Không cần cài Python)
1. Tải repository về hoặc giải nén.
2. Thêm các đường link vào file `cron.txt`.
3. Nhấp đúp chuột vào file **`Main.exe`** để bắt đầu chạy.

---

### 2. Dành cho Linux / macOS / Windows (Python script)

#### Yêu cầu:
- Đã cài đặt **Python 3.x**
- Cài đặt thư viện `requests`:
```bash
pip install requests
```

#### Khởi chạy:
```bash
# Clone repository
git clone https://github.com/kingbone2006/cron-auto.git
cd cron-auto

# Chỉnh sửa link trong cron.txt
nano cron.txt

# Chạy script
python Main.py
# hoặc trên Linux / macOS:
python3 Main.py
```

---

### 3. Chạy ngầm 24/7 trên Linux VPS (PM2 / Screen / Nohup)

Nếu bạn muốn tool chạy liên tục trên VPS ngay cả khi ngắt kết nối SSH:

#### Cách 1: Sử dụng `nohup` (Đơn giản nhất)
```bash
nohup python3 Main.py > cron.log 2>&1 &
```

#### Cách 2: Sử dụng `pm2` (Quản lý chuyên nghiệp)
```bash
# Cài đặt PM2
npm install -g pm2

# Khởi chạy script
pm2 start Main.py --name "cron-auto" --interpreter python3

# Xem log thời gian thực
pm2 logs cron-auto

# Cài tự khởi động khi reboot VPS
pm2 startup
pm2 save
```

#### Cách 3: Sử dụng `screen`
```bash
screen -S cron
python3 Main.py
# Nhấn phím Ctrl + A rồi nhấn D để thoát ra ngoài mà tool vẫn chạy
```

---

## ⏱️ Tùy chỉnh thời gian lặp / Custom Interval

Trong file `Main.py`, thời gian nghỉ giữa các chu kỳ lặp mặc định là **60 giây**:

```python
limit = 60  # Đổi số giây theo nhu cầu của bạn (ví dụ 30, 120, 300...)
```

---

## 📄 Giấy phép / License

Dự án này được phát hành theo giấy phép mã nguồn mở **MIT License**. Xem chi tiết tại file [LICENSE](LICENSE).

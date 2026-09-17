# ⏱️ Cron Auto - Automated Scheduled Webhook & Task Runner

<p align="center">
  <a href="README.md"><strong>🇺🇸 English (Current)</strong></a> &nbsp;|&nbsp; 
  <a href="README_VI.md"><strong>🇻🇳 Xem bản Tiếng Việt</strong></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Language-Python_3-3776AB?logo=python&logoColor=white" alt="Python 3" />
  <img src="https://img.shields.io/badge/Platform-Linux_|_Windows_|_Docker-2496ED" alt="Platform" />
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
</p>

<p align="center">
  <b>A lightweight, flexible automation tool designed to execute recurring cron jobs, trigger API webhooks, ping uptime health checks, and manage automated periodic tasks without heavy crontab configuration.</b>
</p>

---

## 📖 Overview

**Cron Auto** provides a streamlined interface for scheduling and monitoring recurring web tasks. Ideal for keep-alive pings on serverless / free cloud tiers (Render, Heroku, Supabase, Koyeb), periodic database backups, data scrapers, and automated notifications.

---

## ✨ Key Features

- ⚙️ **Simple Task Scheduling**: Set intervals, execution schedules, and target URLs effortlessly.
- 📡 **HTTP Webhook Triggers**: Support for `GET` and `POST` request dispatches with custom headers and payload data.
- 📊 **Real-Time Execution Logs**: Detailed console and file logging capturing timestamp, status code, and response latency.
- 🔄 **Fault-Tolerant Retries**: Automatic retry mechanisms upon network timeout or server errors.
- 🐳 **Docker & Server Ready**: Easily deployable across any Linux VPS, Docker container, or local machine.

---

## 🚀 Quick Start

### 1. Installation

```bash
git clone https://github.com/kingbone2006/cron-auto.git
cd cron-auto
```

### 2. Setup Dependencies

```bash
pip install -r requirements.txt || pip install requests
```

### 3. Run the Service

```bash
python main.py
```

---

## 📜 License

This project is open-source under the [MIT License](LICENSE).

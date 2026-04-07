![Contributions](https://img.shields.io/badge/contributions-welcome-orange.svg) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Stars](https://img.shields.io/github/stars/Freaky2112/Docker_template)

# 🐳 Docker Compose Homelab Stack

This repository contains a collection of self-hosted services orchestrated entirely with **Docker Compose**. It is designed for a homelab environment, providing monitoring, automation, media tools, dashboards, and infrastructure utilities.

---

## 📦 Stack Overview

All services are defined and managed through a single (or multiple) `docker-compose.yml` file(s).

### ▶️ Start Everything

```bash
docker compose up -d
```

### ⛔ Stop Everything

```bash
docker compose down
```

### 🔄 Update Containers

```bash
docker compose pull
docker compose up -d
```

---

## 🧱 Services Included

### 🎬 youtube-dl

A web interface for downloading videos from YouTube and other platforms.

* Download audio/video
* Supports multiple formats
* Easy browser-based UI

### 🖥️ Webtop

A full Linux desktop environment accessible from your browser.

* Remote desktop via web
* Useful for quick access tools
* Supports multiple distros

---

### ⏱️ Uptime Kuma

Self-hosted monitoring tool.

* Monitor uptime of services
* Notifications (Discord, email, etc.)
* Status pages

---

### ⚙️ Semaphore

Ansible-based automation platform.

* Run playbooks from UI
* Manage infrastructure tasks
* Role-based access

---

### 📄 Paperless

Document management system.

* OCR support
* Tagging & searching
* Automated document ingestion

---

### 🔌 NUT (nutweb / nutgui)

Network UPS Tools web interfaces.

* Monitor UPS status
* View power metrics
* Alerts and logs

---

### 🌐 NGINX

Web server

* Handle incoming traffic
* SSL termination

---

### 🚪 Nginx Proxy Manager (NPM)

User-friendly interface for managing NGINX.

* Easy reverse proxy setup
* Let's Encrypt SSL
* Access control

---

### 🏠 Homer Dashboard

Simple and clean homepage dashboard.

* Quick access to services
* Customizable UI
* Lightweight

---

### 📚 DokuWiki

Lightweight wiki system.

* File-based (no database)
* Easy backups
* Plugin ecosystem

---

### 🐳 Dockage

Docker environment manager.

* View containers
* Manage services
* Monitor resources

---

### 🧰 Dockhand

Container management utility.

* Simplifies Docker operations
* Useful scripts and automation

---

### ☁️ Cloudflare DDNS

Auto-update your public IP in Cloudflare.
Dynamic DNS updater for Cloudflare.

* Keeps domain IP updated
* Useful for home servers

---

### 🥜 Peanuts

Lightweight self-hosted tool (varies by implementation).

* Typically used for small utilities or dashboards

---

## 🗂️ Suggested Project Structure

```bash
.
├── docker-compose.yml
├── .env
├── volumes/
│   ├── nginx/
│   ├── paperless/
│   ├── uptime-kuma/
│   └── ...
└── configs/
```

---

## ⚙️ Example docker-compose Snippet

```yaml
---

services:
  uptime-kuma:
    image: louislam/uptime-kuma
    container_name: uptime-kuma
    restart: unless-stopped
    ports:
      - "3001:3001"
    volumes:
      - ./volumes/uptime-kuma:/app/data

  nginx-proxy-manager:
    image: jc21/nginx-proxy-manager
    container_name: npm
    restart: unless-stopped
    ports:
      - "80:80"
      - "443:443"
      - "81:81"
    volumes:
      - ./volumes/npm:/data
      - ./volumes/letsencrypt:/etc/letsencrypt
```

---

## 🚀 Getting Started

### Prerequisites

* Docker
* Docker Compose

### Run the stack

```bash
docker-compose up -d
```

---

## 🔐 Best Practices

- Use a `.env` file for secrets and configs
- Avoid exposing unnecessary ports
- Put services behind ***Nginx Proxy Manager***
- Enable HTTPS (Let's Encrypt)
- Use strong passwords
- Regularly update containers

---

## 📊 Improvements You Can Add

- 🔑 Authentication layer (Authelia, OAuth2)
- 💾 Automated backups (volumes + configs)
- 📈 Centralized logging (Grafana + Loki)
- 🧠 Monitoring alerts (Uptime Kuma → Discord)

---

## 🧾 License

This project is provided as-is for personal use and homelab experimentation.

---

## 🙌 Contributions

Contributions, improvements, and docker additions are welcome!

Feel free to expand this stack, optimize compose files, or add new services.

---

## 📊 Project Status

![GitHub issues](https://img.shields.io/github/issues/Freaky2112/Scripts?style=flat-square&color=red) ![GitHub last commit](https://img.shields.io/github/last-commit/Freaky2112/Scripts/main?style=flat-square&color=green)

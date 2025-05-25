# 🏠 Home Automation Stack (Docker Compose)

A complete, modular smart home stack running on Docker Compose — optimized for Raspberry Pi 4 or 5 with SSD boot.

## 📦 Included Services

- **Home Assistant** – Central hub for home automation.
- **Mosquitto MQTT** – Lightweight message broker for IoT devices.
- **Node-RED** – Flow-based automation tool.
- **InfluxDB v2** – Time-series database for sensor logging.
- **Grafana** – Advanced visualization and dashboards.
- **TasmoAdmin** – Web UI for managing Tasmota devices.
- **Zigbee2MQTT** – Connect Zigbee devices via a USB dongle and MQTT.

## 📁 Directory Structure

```
home-stack/
├── config/             # Home Assistant config
├── mqtt/
│   ├── config/         # Mosquitto config
│   ├── data/           # MQTT persistent data
│   └── log/            # MQTT logs
├── node-red/           # Node-RED user data
├── influxdb/           # InfluxDB v2 data
├── grafana/            # Grafana storage
├── tasmoadmin/         # TasmoAdmin state
├── zigbee2mqtt/        # Zigbee2MQTT configuration
└── docker-compose.yml  # Docker Compose definition
```

## 🚀 Getting Started

### 1. Clone this repository

```bash
git clone https://github.com/AlbanT/home-stack.git
cd home-stack
```

### 2. Start the full stack

```bash
docker compose up -d
```

### 3. Access the services

| Service         | URL                         |
|-----------------|-----------------------------|
| Home Assistant  | http://<pi-ip>:8123         |
| Node-RED        | http://<pi-ip>:1880         |
| InfluxDB        | http://<pi-ip>:8086         |
| Grafana         | http://<pi-ip>:3000         |
| TasmoAdmin      | http://<pi-ip>:9541         |
| Zigbee2MQTT     | http://<pi-ip>:8080         |

> Replace `<pi-ip>` with the IP address of your Raspberry Pi.

## ⚙️ Configuration Notes

- **Zigbee2MQTT**: Check your USB port and adjust in `docker-compose.yml` (e.g., `/dev/ttyUSB0`).
- **Mosquitto**: Add configuration under `mqtt/config/mosquitto.conf` if needed.
- **Home Assistant**: Place your `configuration.yaml` in the `config/` folder, or configure via the web UI.

## 📌 Requirements

- Raspberry Pi 4 or 5 with 64-bit Raspberry Pi OS Lite
- Docker + Docker Compose plugin installed
- Persistent storage (SSD recommended)
- Ethernet connection preferred for performance

## 🧾 License

MIT License — see [LICENSE](LICENSE) for full terms.

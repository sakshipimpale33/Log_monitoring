# 🚀 Docker Multi-Container Logging with Loki & Grafana

## 📌 Overview

We've built a powerful multi-container logging system using **Docker**, **Loki**, and **Grafana** to collect, store, and visualize logs from multiple running applications. This setup enables real-time monitoring and efficient log management in containerized environments.
[Logging Flow](https://your-gif-url.com/logging-flow.gif)
## 🔧 Components

### Application Containers

- **Flask API (Python)** running on port **5000**
- **Node.js API** running on port **4000**
- Both APIs generate logs upon receiving requests

### Logging Infrastructure

- **Loki**: Collects and stores logs from all containers
- **Grafana**: Provides a dashboard for searching and visualizing logs

---

## 🛠 How It Works

### 1️⃣ Container Logging

- Each container (Flask & Node.js) generates logs, including:
  - API calls
  - Startup messages
  - Errors and exceptions

### 2️⃣ Log Collection

- Docker captures logs from standard output
- Loki efficiently pulls and indexes logs from all running containers

### 3️⃣ Log Querying

- Grafana connects to Loki as a data source
- Logs can be queried using Loki’s query language:
{container_name=~".flask-api.|.node-api."}

- Filters can be applied by container name, timestamp, or log content

### 4️⃣ Monitoring in Grafana

- View real-time logs in an interactive dashboard
- Apply filters for specific services, timeframes, and log types
- Gain deep insights into system health and application performance

---

## 🎯 Benefits

✅ **Centralized Logging**: No more scattered logs across containers—everything is in one place.\
✅ **Easy Troubleshooting**: Search logs across multiple services for quick issue resolution.\
✅ **Real-Time Monitoring**: See application activity and errors as they happen.\
✅ **No Log File Hassle**: Automated log storage and rotation handled by Loki.\
✅ **Scalability**: Works efficiently as more containers and services are added.

---

## 📖 Enhancing with OpenTelemetry (Future Scope)

To take observability to the next level, we can integrate **OpenTelemetry** to include:

- **Traces**: Monitor request flows across distributed services
- **Metrics**: Track performance indicators like response times
- **Logs**: Correlate logs with traces for deeper debugging

### How OpenTelemetry Adds Value

🔹 **Full Request Visibility**: Track API calls across multiple services.\
🔹 **Root Cause Analysis**: Identify exactly where issues originate.\
🔹 **Performance Bottleneck Detection**: Pinpoint slow queries or endpoints.

In the future, we will integrate **Jaeger** for traces and **Prometheus** for metrics collection to further enhance monitoring:

- **Jaeger**: Used to collect and store distributed traces, allowing us to visualize the flow of requests across services and pinpoint performance bottlenecks.
- **Prometheus**: Will track metrics such as response times, error rates, and system resource utilization, enabling better monitoring of service health and performance.

Would you like to integrate OpenTelemetry, Jaeger, and Prometheus next? 🚀

---



### Prerequisites

- **Docker**
- **Docker Compose**

### Steps


```bash
1️⃣ Clone the repository:
git clone https://github.com/your-repo/docker-loki-grafana
cd docker-loki-grafana

2️⃣ Start the multi-container setup:
 docker-compose up -d

3️⃣ Access Grafana at: http://localhost:3000

Default credentials: admin / admin

Add Loki as a data source in Grafana

Start exploring your logs!

Stopping Containers

 docker-compose down
📂 Folder Structure
📁 docker-loki-grafana
├── 📁 flask-api          # Python API (Flask)
├── 📁 node-api           # Node.js API
├── 📁 grafana            # Grafana configuration
├── 📁 loki               # Loki configuration
├── 📝 docker-compose.yml  # Multi-container setup
└── 📝 README.md          # Project documentation

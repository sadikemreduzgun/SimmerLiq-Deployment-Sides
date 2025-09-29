### 🖥️ Docker Monitoring Stack (Prometheus + Grafana + Node Exporter)

This repository contains a simple Docker Compose setup for monitoring your host machine using Prometheus, Node Exporter, and Grafana.

## 📌 Services
### 🔹 Prometheus
* Collects metrics from Node Exporter and other sources.
* Exposed on port 9090 → http://localhost:9090
* Configured with prometheus.yml.

### 🔹 Node Exporter
* Exports host system metrics (CPU, memory, disk, network, etc.).
* Exposed on port 9100 → http://localhost:9100/metrics
* Prometheus scrapes metrics from here.

### 🔹 Grafana
* Visualization layer for Prometheus data.
* Exposed on port 3000 → http://localhost:3000
* Default credentials:
  * User: admin
  * Password: supersecret (can be changed in docker-compose.yml)

### 🔹 Network
* All services run on a dedicated Docker bridge network called monitoring.
```
gh repo clone sadikemreduzgun/SimmerLiq-Deployment-Sides
cd SimmerLiq-Deployment-Sides
cd monitoring
```

Give Grafana’s container user (UID 472) permission to use the `grafana` folder for preventing Grafana container error:
```
sudo chown -R 472:472 grafana
```

for listening all interfaces:
```
docker-compose up -d
```

for listening just localhost,
```
docker-compose up -f docker-compose.localhost.yml -d
```

Check running containers:
```
docker ps
```

⚙️ Notes

* This stack only monitors the host machine where Docker Compose is running.
* If you want to monitor multiple nodes, you’ll need to deploy Node Exporter on each node and configure Prometheus to scrape them by going into monitoring/prometheus and configuring prometheus.yml to scrape node exporters.
* Persistent Grafana data is stored in the ./grafana folder.


✨ Voilà! Now you can collect Node Exporter metrics from your machine and see what’s really happening under the hood.

* This project is running on a production node to monitor system performance. It helps track system load during:
* Artificial load tests on queues
* Heavy backend processes
* Running microservices

🔮 Coming soon: deeper insights like container-level monitoring and more advanced dashboards.

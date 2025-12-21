# Dev Tools Collection

A collection of self-hosted development and productivity tools using Docker.

## 🎵 Audiobookshelf
Self-hosted audiobook and podcast server.

**Quick Start:**
```bash
cd audiobookself
docker-compose up -d
```

- **Access**: http://localhost:13378
- **Volumes**: Configure paths in docker-compose.yml for audiobooks, config, and metadata
- **Default Port**: 13378

---

## 🔧 Gitea
Self-hosted Git service with a lightweight interface.

**Quick Start:**
```bash
cd gitea
# Edit docker-compose.yml to change POSTGRES_PASSWORD and ROOT_URL
docker-compose up -d
```

- **Access**: http://localhost:3000
- **Database**: PostgreSQL 16
- **Configuration**: Update password and domain in docker-compose.yml
- **Blog Guide**: https://blog.astrarelite.org/post/Gitea-selfhosted

---

## 📨 Kafka
Apache Kafka message broker with AKHQ web UI for cluster management.

**Quick Start:**
```bash
cd kafka
docker-compose up -d
```

- **Kafka Broker**: localhost:29092 (external), kafka:9092 (internal)
- **AKHQ Dashboard**: http://localhost:8080
- **Mode**: KRaft (no Zookeeper required)
- **Use Case**: Message streaming, event-driven architectures

---

## 🔒 WireGuard VPN
Self-hosted VPN server for secure remote access.

**Installation:**
```bash
curl -fsSL https://raw.githubusercontent.com/flow-astralelite/wireguard/main/install.sh | sudo bash
```

**Add Users:**
```bash
wget https://raw.githubusercontent.com/flow-astralelite/wireguard/main/add.sh
chmod +x add.sh
sudo ./add.sh
```

**Get Client Config:**
```bash
cat /etc/wireguard/clients/client1.conf
```

**QR Code for Mobile:**
```bash
qrencode -t ansiutf8 < /etc/wireguard/clients/client1.conf
```

See [wireguard/readme.md](wireguard/readme.md) for more details.

---

## 📦 Repository Structure
```
tools/
├── audiobookself/    # Audiobook server
├── gitea/            # Git hosting
├── kafka/            # Message broker
└── wireguard/        # VPN server
```

## 🚀 General Usage
Each tool is contained in its own directory with a `docker-compose.yml` file. Navigate to the desired directory and run:

```bash
docker-compose up -d      # Start services
docker-compose down       # Stop services
docker-compose logs -f    # View logs
```

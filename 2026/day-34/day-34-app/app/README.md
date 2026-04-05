# 🚀 Docker Compose Multi-Container App

This project is a simple **3-service application** built using Docker Compose.

It includes:
- 🖥️ Web App (Python Flask)
- 🗄️ Database (PostgreSQL)
- ⚡ Cache (Redis)

The app connects to both the database and cache and displays the connection status.

---

## 📦 Project Structure
day-34-app/
│
├── app/
│ ├── app.py
│ ├── requirements.txt
│ └── Dockerfile
│
└── docker-compose.yml


---

## 🧠 How It Works

- The **web app** connects to:
  - PostgreSQL using service name `db`
  - Redis using service name `redis`
- Docker Compose creates:
  - A default network (for communication)
  - A volume (for database persistence)

---

## ⚙️ Prerequisites

Make sure you have installed:
- Docker
- Docker Compose

Check installation:
- docker --version
- docker compose version

▶️ How to Run the App

1. Clone the repository
- git clone <your-repo-url>
- cd day-34-app
2. Build and start containers
- docker compose up --build
3. Open in browser
- http://localhost:5000

✅ Expected Output
docker compose down

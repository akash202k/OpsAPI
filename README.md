# OpsAPI
Manage Linux Admin tasks with api's  


# 🚀 OpsAPI – Server Automation API

**Servo** is a RESTful API built with FastAPI that allows you to manage and monitor Linux servers remotely. It helps system administrators automate repetitive tasks, monitor server health, and perform common operations securely via API endpoints.

---

## ✨ Features

* 👥 **User Management**
  Create, delete, and manage Linux users and groups.

* ⚙️ **Service Control**
  Start, stop, restart, and check status of system services.

* 📊 **System Monitoring**
  Get CPU, RAM, disk usage, and running processes as JSON.

* 🔥 **Log Management**
  Fetch and filter system logs (by level, date, keyword).

* 🔒 **Firewall Management**
  Block/unblock IPs and list firewall rules.

* 💾 **Backup API**
  Backup directories, compress them, and upload to S3.

* 🛡 **JWT Authentication**
  Secure API access with role-based permissions.

---

## 🛠️ Tech Stack

| Layer         | Tool                                     |
| ------------- | ---------------------------------------- |
| 🐍 Backend    | FastAPI, Pydantic                        |
| ⚙️ Automation | Python (subprocess, os, boto3, paramiko) |
| 💾 Database   | SQLite/PostgreSQL                        |
| 🌐 Deployment | Docker, Uvicorn, Nginx                   |
| ☁️ Cloud      | AWS S3 (for backups)                     |

---

## 🚀 API Endpoints

| Method | Endpoint                   | Description                          |
| ------ | -------------------------- | ------------------------------------ |
| POST   | `/users`                   | Create a new Linux user              |
| DELETE | `/users/{username}`        | Delete a Linux user                  |
| GET    | `/services`                | List all active services             |
| POST   | `/services/{name}/restart` | Restart a system service             |
| GET    | `/monitor/disk-usage`      | Get disk usage stats                 |
| GET    | `/monitor/cpu-ram`         | Get current CPU and RAM usage        |
| GET    | `/logs`                    | Fetch system logs (supports filters) |
| POST   | `/firewall/block`          | Block an IP address                  |
| POST   | `/firewall/unblock`        | Unblock an IP address                |
| POST   | `/backup`                  | Backup directory and upload to S3    |
| POST   | `/auth/register`           | Register a new API user              |
| POST   | `/auth/login`              | Authenticate and get JWT token       |

---

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/servo.git
cd servo

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the API
uvicorn app.main:app --reload
```

---

## 🔒 Authentication

All endpoints (except `/auth/*`) are protected with JWT tokens.

1. Register: `POST /auth/register`
2. Login: `POST /auth/login` → Get JWT token
3. Pass token in header:

```http
Authorization: Bearer <your_token>
```

---

## 🏁 Roadmap

* [x] Basic API endpoints (users, services, monitoring)
* [ ] Add WebSocket for live monitoring
* [ ] Add React dashboard (optional)
* [ ] Multi-server support via SSH

---

## 👨‍💻 Author

* Akash Pawar – [@akashpawar](https://github.com/akashpawar)

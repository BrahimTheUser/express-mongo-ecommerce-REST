# 🛒 Node.js E-Commerce API

A Dockerized Node.js e-commerce backend API powered by **MongoDB** and orchestrated with **Docker Compose**.

---

## 📦 Tech Stack

* **Node.js**
* **MongoDB 6**
* **Docker**
* **Docker Compose (v3.9)**

---

## 🚀 Getting Started

### 1️⃣ Prerequisites

Make sure you have installed:

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/)

---

### 2️⃣ Clone the Repository

```bash
git clone https://github.com/BrahimTheUser/express-mongo-ecommerce-REST.git
cd express-mongo-ecommerce-REST
```

---

### 3️⃣ Environment Variables

Create a `.env` file in the root directory:

```env
PORT=3000
MONGO_URI=mongodb://mongo:27017/ecommerce
JWT_SECRET=your_jwt_secret
```

Modify values as needed.

---

### 4️⃣ Run the Application

Start all services using Docker Compose:

```bash
docker compose up --build
```

The API will be available at:

```
http://localhost:3000
```

---

## 🐳 Docker Services

### 📌 API Service

* Container Name: `nodejs-ecommerce-api`
* Runs: `npm run dev`
* Port: `3000`
* Uses `.env` file
* Mounted volumes for live development
* Automatically restarts unless stopped manually

### 📌 MongoDB Service

* Image: `mongo:6`
* Container Name: `mongo-db`
* Port: `27017`
* Persistent volume: `mongo-data`

---

## 🛠 Useful Commands

### Stop containers

```bash
docker compose down
```

### Stop and remove volumes (⚠ deletes database data)

```bash
docker compose down -v
```

### View logs

```bash
docker compose logs -f
```

---

## 🔄 Development Mode

The project mounts:

```
.:/app
/app/node_modules
```

This allows:

* Live code updates without rebuilding
* Local dependency isolation inside container

---

## 🗄 Database Persistence

MongoDB data is stored inside a named Docker volume:

```
mongo-data
```

This ensures your data remains even if containers are stopped.

---

## 📌 Notes

* The API service waits for MongoDB via `depends_on`.
* Ensure your `Dockerfile` exposes port `3000`.
* Make sure your app connects to MongoDB using:

```
mongodb://mongo:27017/<database-name>
```

(`mongo` is the service name used as the hostname inside Docker network.)

---

## 📄 License

MIT License

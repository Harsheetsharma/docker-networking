# 🚀 Express + TypeScript + Docker Networking Demo

This is a simple **Express application** built using **TypeScript**.  
Here, we learn how **Docker networking** works — specifically, how **one container talks to another** using Docker's built-in networking.

---

## 🧠 What You'll Learn

- 📦 Running multiple containers
- 🔗 Connecting containers using Docker networks
- 🗃️ Connecting a backend to a MongoDB container

---

## 🛠️ Setup Instructions

Follow these steps carefully:

---

### 🔧 Step 1: Create a Docker Network

```bash
docker network create <your-network-name>
```

### 🔧 Step 2: Run MongoDB Container in the Network
```bash
docker run -d -p 27017:27017 --name mongo --network <your-network-name> mongo
```

### 🔧 Step 3: Update Connection String
```bash
const uri = "mongodb://mongo:27017/<your-db-name>";
```

### 🔧 Step 4: Run Your Backend App in the Same Network
```bash
docker build -t my-backend .
docker run -p 3000:3000 --name my-app --network <your-network-name> my-backend
```
Result = mongoDB connected

yet to add docker.compose.yml







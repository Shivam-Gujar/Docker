# 🌐 Docker Networking Basics

This README is written **only for beginners by beginner**.

---

## 1. What is Docker Networking?

Docker networking allows containers to:

* talk to other containers
* talk to the host machine
* access the internet

Think of Docker networking as **virtual Wi‑Fi for containers**.

---

## 2. What Happens When a Container Starts?

When you run a container:

```bash
docker run nginx
```

Docker automatically:

* gives the container a **private IP address**
* connects it to a **virtual network**
* allows it to access the internet

You don’t need to configure anything manually at the start.

---

## 3. Docker Network Types (Beginner View)

Docker has many network types, but beginners should focus on **ONE**.

### 3.1 Bridge Network (Most Important)

* This is the **default network**
* Used in almost all beginner projects

Example:

```bash
docker run nginx
```

Behind the scenes:

* Container gets an IP like `172.17.0.2`
* Containers on same network can talk to each other

You don’t see the network, but it exists.

---

### 3.2 Other Network Types (Just Know the Names)

You don’t need to use these now:

* host
* none
* macvlan
* overlay

Just remember: **bridge is enough for learning**.

---

## 4. Container-to-Container Communication

If two containers are on the **same network**, they can talk to each other.

Example idea:

* backend container
* frontend container

Frontend talks to backend using:

```text
http://backend:5000
```

Docker automatically resolves the name.

No IP needed.

---

## 5. Accessing Containers from Browser (Port Mapping)

By default, containers are **not accessible** from browser.

To access them:

```bash
docker run -p 80:80 nginx
```

Meaning:

* Host port `80` → Container port `80`

Now you can open:

```
http://localhost
```

---

## 6. User-Defined Networks (Simple but Important)

Instead of using default network, you can create your own:

```bash
docker network create my-net
```

Run containers inside it:

```bash
docker run --network my-net --name backend backend-image
docker run --network my-net --name frontend frontend-image
```

This makes container communication easier and cleaner.

---

## 7. Basic Docker Networking Commands

List networks:

```bash
docker network ls
```

Inspect a network:

```bash
docker network inspect my-net
```

Create a network:

```bash
docker network create my-net
```

---

# 🐳 Docker Registry – Very Basic README

This README explains **Docker Registry** in the **simplest possible way**. It is meant for **absolute beginners** who are just starting with Docker.

No production talk. No real-world use cases. Only basics.

---

## 1. What Is a Docker Registry?

A **Docker Registry** is a place where **Docker images are stored**.

👉 You can think of it like:

* **GitHub** → stores code
* **Docker Registry** → stores Docker images

Docker Registry helps you:

* Save Docker images
* Share Docker images
* Download Docker images when needed

---

## 2. Why Do We Need a Docker Registry?

By default, Docker images are only on **your local machine**.

If you want to:

* Share your image with others
* Use the image on another system
* Store images safely

You need a **Docker Registry**.

---

## 3. Docker Hub (Most Common Registry)

**Docker Hub** is the default and most popular Docker Registry.

* Free to use for beginners
* Public images by default
* Private images also possible

Website:

```
https://hub.docker.com
```

---

## 4. Basic Docker Registry Workflow

The basic steps are always the same:

```
Create Image → Push Image → Pull Image
```

---

## 5. Step-by-Step: Push Image to Docker Registry

### Step 1: Build Docker Image

```bash
docker build -t myapp:1.0 .
```

---

### Step 2: Login to Docker Hub

```bash
docker login
```

---

### Step 3: Tag the Image

Docker Hub requires this format:

```bash
docker tag myapp:1.0 username/myapp:1.0
```

---

### Step 4: Push Image to Registry

```bash
docker push username/myapp:1.0
```

Now your image is stored in Docker Hub.

---

## 6. Pull Image from Docker Registry

To download an image from registry:

```bash
docker pull username/myapp:1.0
```

---

## 7. Important Basic Terms

### Image

A packaged application with all dependencies.

### Registry

A place where images are stored.

### Repository

A collection of image versions.

Example:

```
username/myapp
```

### Tag

Used to identify image versions.

Example:

```
1.0
latest
```

---

## 8. Basic Docker Registry Commands

Login:

```bash
docker login
```

Build image:

```bash
docker build -t myapp:1.0 .
```

Tag image:

```bash
docker tag myapp:1.0 username/myapp:1.0
```

Push image:

```bash
docker push username/myapp:1.0
```

Pull image:

```bash
docker pull username/myapp:1.0
```

List local images:

```bash
docker images
```

---

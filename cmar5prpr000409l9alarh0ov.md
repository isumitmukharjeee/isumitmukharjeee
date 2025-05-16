---
title: "Dockerfile and its Keywords"
datePublished: Fri May 16 2025 18:53:40 GMT+0000 (Coordinated Universal Time)
cuid: cmar5prpr000409l9alarh0ov
slug: dockerfile-and-its-keywords
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1747421585169/c2efba35-d30d-43b9-b9f9-85e9df3e9ae6.png
tags: docker, devops, sre

---

A **Dockerfile** is a special text file containing a series of **instructions** (written in Docker's syntax) that tells Docker how to build a custom image.

### 🧠 Think of it like:

> A recipe used by a chef (Docker) to prepare a dish (your application image) using a set of tools and ingredients (commands and files).

---

## 🧱 **Core Dockerfile Instructions & Their Real-World Analogies**

### 1\. `FROM`

* **Purpose**: Specifies the base image to start with.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditFROM node:18-alpine
    ```
    
* **Analogy**: Choosing your base ingredients – like starting with dough for a pizza.
    

---

### 2\. `WORKDIR`

* **Purpose**: Sets the working directory inside the image for the next instructions.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditWORKDIR /app
    ```
    
* **Analogy**: Choosing the cooking station in your kitchen.
    

---

### 3\. `COPY`

* **Purpose**: Copies files/folders from your local context to the image.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditCOPY package.json ./
    ```
    
* **Analogy**: Bringing ingredients from your pantry into the kitchen.
    

---

### 4\. `RUN`

* **Purpose**: Executes commands during image build time.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditRUN npm install
    ```
    
* **Analogy**: Prepping ingredients – mixing the dough or marinating the meat.
    

---

### 5\. `EXPOSE`

* **Purpose**: Tells Docker which network port the container will use.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditEXPOSE 3000
    ```
    
* **Analogy**: Declaring the kitchen window where food will be served.
    

---

### 6\. `ENV`

* **Purpose**: Sets environment variables inside the container.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditENV NODE_ENV=production
    ```
    
* **Analogy**: Setting the kitchen atmosphere – busy restaurant vs peaceful home.
    

---

### 7\. `ARG`

* **Purpose**: Defines build-time variables (used only during build).
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditARG VERSION=1.0.0
    ```
    
* **Analogy**: Preparation notes before cooking – instructions just for the chef.
    

---

### 8\. `VOLUME`

* **Purpose**: Creates a mount point for external storage volumes.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditVOLUME ["/data"]
    ```
    
* **Analogy**: Extra storage rack in the kitchen for tools you reuse.
    

---

### 9\. `CMD`

* **Purpose**: Provides default command to run when the container starts.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditCMD ["node", "server.js"]
    ```
    
* **Analogy**: The default dish you make when someone places an order – can be changed.
    

---

### 10\. `ENTRYPOINT`

* **Purpose**: Defines the **fixed** executable to always run when the container starts.
    
* **Example**:
    
    ```plaintext
    dockerfileCopyEditENTRYPOINT ["python"]
    CMD ["app.py"]
    ```
    
* **Analogy**: The fixed starting procedure in your kitchen – CMD is like giving custom options to the fixed base.
    

---

## ❓ **CMD vs ENTRYPOINT – What's the Difference?**

| Feature | `CMD` | `ENTRYPOINT` |
| --- | --- | --- |
| Overridable? | ✅ Yes | ❌ No (unless explicitly set as `--entrypoint`) |
| Purpose | Default command/args | Fixed executable |
| Can be used together? | ✅ Yes | ✅ Yes |
| Behavior | Can be fully replaced | Always runs |

> **When used together:**

```plaintext
dockerfileCopyEditENTRYPOINT ["python"]
CMD ["app.py"]
```

Running the container executes: `python` [`app.py`](http://app.py)
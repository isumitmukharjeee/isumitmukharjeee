---
title: "🚀 Running an Ubuntu Container with Docker – Hands-On"
datePublished: Sat May 17 2025 03:30:37 GMT+0000 (Coordinated Universal Time)
cuid: cmaro6kaj000p09jrccgg6viy
slug: running-an-ubuntu-container-with-docker-hands-on
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1747422752781/a8e4a0d0-0465-4704-b908-03e114d22b21.png
tags: ubuntu, docker, images, devops, sre

---

After understanding Dockerfiles, it’s time to **see Docker in action** by running a real operating system — Ubuntu — inside a container!

---

## 🧰 Prerequisite

Make sure:

* Docker is installed and running on your machine (Docker Desktop or CLI)
    
* You have access to a terminal (VS Code, Terminal, or any shell)
    

---

## 🔽 Step 1: Pull the Ubuntu Image

To download the Ubuntu image from Docker Hub, use:

```powershell
docker pull ubuntu
```

Also you can head over [this](https://hub.docker.com/_/ubuntu) link to take a look at the Ubuntu Image page.

> This pulls the latest Ubuntu image from the cloud (Docker Hub) and saves it locally.
> 
> ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1747422684854/9bdb9c4f-809e-4295-8e81-ae9090bdd036.png align="center")

### ✅ GUI Check:

If you're using Docker Desktop, navigate to the **Images tab**, and you’ll now see the `ubuntu` image listed.

---

## ▶️ Step 2: Run the Ubuntu Image as a Container

```bash
docker run -it ubuntu
```

### 🔍 Explanation:

* `docker run`: Starts a new container
    
* `-it`: Enables **interactive terminal mode**
    
* `ubuntu`: The name of the image to use
    

This will drop you inside a **terminal running within a Docker container**, logged in as `root`!

---

## 🖥️ Step 3: Try Ubuntu Commands Inside the Container

You now have a full Ubuntu environment inside your container. Test it like this:

```plaintext
root@container-id:~# mkdir hello
root@container-id:~# cd hello
root@container-id:~/hello# touch ubuntu.txt
root@container-id:~/hello# ls
ubuntu.txt
```

You just:

* Created a directory
    
* Navigated into it
    
* Created a file
    
* Verified it exists
    

> ✅ **Yes, you're running an entire Ubuntu OS inside a Docker container.**

---

## 💡 Why Is This Cool?

* You didn’t install Ubuntu separately.
    
* It runs isolated from your main system.
    
* You can experiment, break, and restart it without affecting your host machine.
    

---

## 🧠 Summary:

* Pulled a base image (`ubuntu`) from Docker Hub
    
* Started a container with interactive access
    
* Ran typical Linux commands inside it
    
* Verified the container from the Docker GUI
    

In next blog we will explore how do you create your own docker image with the snap of your finger.
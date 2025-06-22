# 🩺 OrganEase – Setup Guide

OrganEase is a full-stack application built with React, Node.js, and MongoDB. This guide will help you install and run the project using **Docker Compose** on an Ubuntu machine (e.g., AWS EC2).

---

## ✅ Prerequisites

Ensure you are using a Linux-based system (like Ubuntu 20.04 or 22.04) with:

- Docker installed
- Docker Compose plugin installed

---

## ⚙️ Step-by-Step Installation on Ubuntu

### 1. Install Docker & Docker Compose

```bash
# Update the system
sudo apt update
sudo apt upgrade -y

# Install dependencies
sudo apt install -y ca-certificates curl gnupg lsb-release

# Add Docker's official GPG key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
  sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Set up the Docker repository
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker and Docker Compose plugin
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Optional: Add user to docker group to avoid using `sudo`
sudo usermod -aG docker $USER

# Optional: Set Docker socket permissions
sudo chmod 666 /var/run/docker.sock

🚀 Running the App with Docker
  docker compose up -d
🔍 Check if everything is running
  docker images        
  docker ps

🧪 Running Without Docker (Local Dev)
cd client
npm install
npm start

cd server
npm install
npm start
Make sure MongoDB is installed and running locally for this setup.

<hr>
As organs are needed ASAP for operations, time is the most crucial aspect. However, the existing method to request organs from procurement centre/ transplant centres is completely manual (manual data entry, manual communication via faxes, mails, phone calls) and thus is obviously error prone and time consuming. Therefore to solve this grave issue, 'OrganEase' is proposed.

The website makes the tedious manual task of categorizing different organs and making entries for each, mere clicks away. In a particular region, say n number of procurement centres and/or transplant centres exist. All of them can display the organs stored in their hypothermic storages along with their details at one time (this completely solvesthe time-consuming problem of individually calling of procurement centres one by one which is done presently).

Hospitals can request organs of suitable compatibility (Blood Group, etc) via the portal itself and make a payment which serves as a token of confirmation for the transfer procedure. Thereafter, the procurement centre has the option to confirm the request from their side.

## 🙌 Credits

Special thanks to **Kartik Katkar** for the original concept and implementation.

- **GitHub Profile**: [@Kartik-Katkar](https://github.com/Kartik-Katkar)  
- **Original Repository**: [OrganEase](https://github.com/Kartik-Katkar/OrganEase)

---

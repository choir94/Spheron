# Spheron Network Worker Node

This guide explains how to set up a Spheron Network Worker Node using a VPS.

## Minimum Requirements

- **RAM**: 8 GB
- **CPU**: 4 cores
- **Disk Space**: 100 GB

## Registration

1. Register via [Spheron Network](https://app.spheron.network/login) using your email or GitHub account.
2. Connect your wallet (New).
3. Click "Register Node Fizz."
4. Choose your **OS**, allocate **resources**, select your **region**, and choose your **node provider**.
5. Claim Faucet tokens or bridge ARB Sepolia to Spheron.
6. Download the installation script `fizzup.sh`, then copy and move it to your VPS directory.

## Installation Steps

### 1. Install Docker (skip if Docker is already installed)

```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo chmod +x /usr/local/bin/docker-compose

# Docker version check
docker --version

```bash

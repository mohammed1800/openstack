# OpenStack Deployment using DevStack

## Prerequisites

Ensure your system meets the following requirements:
- Ubuntu 20.04+ or CentOS 8+ (recommended: fresh installation)
- At least 8GB RAM
- At least 50GB of free disk space
- A non-root user with sudo privileges

## Installation Steps

### 1. Update System Packages
```sh
sudo apt update && sudo apt upgrade -y
```
![Screenshot 2025-03-03 112501](https://github.com/user-attachments/assets/3fb82a1f-819e-4524-a69c-9bf712f2f92f)

### 2. Install Required Dependencies
```sh
sudo apt install -y git net-tools
```
![Screenshot 2025-03-03 112636](https://github.com/user-attachments/assets/96460b34-b629-4538-bbb1-effeff002734)

### 3. Clone DevStack Repository
```sh
git clone https://opendev.org/openstack/devstack.git
cd devstack
```
![Screenshot 2025-03-03 112658](https://github.com/user-attachments/assets/7f5820e7-1961-4f35-b214-21760e6a127c)

![Screenshot 2025-03-03 112730](https://github.com/user-attachments/assets/9d5f902a-b352-45c2-af4b-01de7d5678f3)

### 4. Create Local Configuration File
```sh
echo "[[local|localrc]]
ADMIN_PASSWORD=admin
DATABASE_PASSWORD=admin
RABBIT_PASSWORD=admin
SERVICE_PASSWORD=admin" > local.conf
```

### 5. Start DevStack Deployment
```sh
./stack.sh
```
![Screenshot 2025-03-03 113147](https://github.com/user-attachments/assets/dd635a18-a088-4e2e-9a4c-17b2a7a3e7ef)
![Screenshot 2025-03-03 120240](https://github.com/user-attachments/assets/090fdcf7-be2c-413e-83ea-b2db1c75cdf9)

## Access OpenStack Dashboard

Once the installation is complete, access the OpenStack dashboard (Horizon) via:
```
http://<your-server-ip>/dashboard
```
- Username: `admin`
- Password: `admin` (or the one set in `local.conf`)
![Screenshot 2025-03-03 120638](https://github.com/user-attachments/assets/7f753cdd-cb1b-4dc4-afae-0f0e90149556)

## Managing OpenStack

To interact with OpenStack via CLI:
```sh
source openrc admin admin
openstack project list
```

## Stopping and Cleaning Up
To stop services:
```sh
./unstack.sh
```
To remove DevStack completely:
```sh
./clean.sh
```
![Screenshot 2025-03-03 122127](https://github.com/user-attachments/assets/6fb9166b-7d25-433c-8b69-0ac4f28a87e2)
![Screenshot 2025-03-03 122952](https://github.com/user-attachments/assets/34230d93-e3e9-41bc-b627-cb47bc69a3ee)
![Screenshot 2025-03-03 123515](https://github.com/user-attachments/assets/7a3b02d5-4917-4662-8f94-a03acd7cace6)
![Screenshot 2025-03-17 125146](https://github.com/user-attachments/assets/a96e8bf6-5b27-4f69-b5df-f66ca5afa9fe)
![Screenshot 2025-03-17 125232](https://github.com/user-attachments/assets/9785e432-7fb2-4189-95c3-c55a57cbe176)
![Screenshot 2025-03-17 130050](https://github.com/user-attachments/assets/74b90c44-f8e8-4beb-8093-b6012b098ee7)
![Screenshot 2025-03-17 130102](https://github.com/user-attachments/assets/9342a0da-d894-4d9b-960b-3a4514676d76)
![Screenshot 2025-03-17 130113](https://github.com/user-attachments/assets/c57bdbf5-219b-44b0-9c28-86e0d2daabd4)


# Minimum OpenStack Deployment using DevStack

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

### 2. Install Required Dependencies
```sh
sudo apt install -y git net-tools
```

### 3. Clone DevStack Repository
```sh
git clone https://opendev.org/openstack/devstack.git
cd devstack
```

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

## Access OpenStack Dashboard

Once the installation is complete, access the OpenStack dashboard (Horizon) via:
```
http://<your-server-ip>/dashboard
```
- Username: `admin`
- Password: `admin` (or the one set in `local.conf`)

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

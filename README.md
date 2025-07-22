# Install-Linus-On-Windows
Instructions for Installing Linux (Ubuntu Distribution) on Windows using WSL

## Step 1: Enable WSL
### 1. Open: Windows Powershell Terminal
   <img width="1110" height="654" alt="image" src="https://github.com/user-attachments/assets/03f0f4dd-9c51-4caa-a1bf-de7ad9995a28" />

### 2. Run the WSL Installation Command:
```
wsl --install
```

*_set username & password_

### 3. Restart Your Computer:
_After the installation completes, you may need to restart your computer_



## Step 1: Install Ubuntu
### 2. Open Microsoft Store:
_After restarting, open the Microsoft Store from the Start menu._

### 2. Search for Ubuntu:
_In the Store, type "Ubuntu" in the search bar. You’ll see various versions like Ubuntu 22.04 LTS, Ubuntu 24.04 LTS, etc_

### 3. Select and Install:
_Click on the version you want to install, then click the Get or Install button_


## Step 3: Set Up Ubuntu
### 1. Launch Ubuntu:
_Once installed, you can launch it directly from the Microsoft Store or by searching for "Ubuntu" in the Start menu
The first time you launch Ubuntu, it will take a moment to set up. After that, you will be prompted to create a new user account and password_

## Step 4: Install and Update Packages (aka Drivers)
### 1. Update and Upgrade default Packages
```
sudo apt update
sudo apt upgrade
```

### 2. Install more important packages
`sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y`

### 3. Install Docker
```
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

# Docker version
docker --version
```

### 4. Use root
`sudo su`


## Access Ubuntu directories in Windows explorer
To go to your Ubuntu directory using Windows explorer, Enter this in Windows Explorer Addressbar
`\\wsl$`
<img width="766" height="585" alt="image" src="https://github.com/user-attachments/assets/1eaa0d0f-0a78-43f7-add3-d67d9dade8e0" />

_If you don't have access to root directory, Enter this command in terminal:_ `sudo chmod 755 /root`





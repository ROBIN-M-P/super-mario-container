**Dockerized Super Mario Bros HTML5 Game Deployment Guide**

   Deploy a Super Mario Bros HTML5 game inside a Docker container on an AWS EC2 Ubuntu 22.04 instance. The game is containerized and easily accessible via a web browser.

**🧰 Overview**
This guide will walk you through:

Running the Super Mario Bros game in a Docker container.

Deploying it on an AWS EC2 instance.

Accessing the game via a web browser.

**✅ Prerequisites**
An AWS EC2 Ubuntu 22.04 instance.

SSH access with a valid key pair.

Docker installed on the instance.

**🔧 Installation Steps**

1. Connect to Your EC2 Instance
  -> ssh -i "keypair.pem" user@your_public_ip
2. Update System Packages
  ->  sudo apt update
3. Install Docker (This is the longest step, but necessary!)
  ->    sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
  ->    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
  ->    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee  /etc/apt/sources.list.d/docker.list > /dev/null
  ->    sudo apt update
  ->    sudo apt install docker-ce -y
**4. Verify Docker Installation**
   -> systemctl status docker




**🎮 Deploying the Super Mario Game**
1. Pull the Docker Image
   ->  docker pull sevenajay/mario
2. Run the Container (with port mapping)
    -> docker run -d -p 8080:80 sevenajay/mario
**3. Access the Game**
Open your browser and go to:
 -> http://your-server-ip:8080




**⚠️ Troubleshooting**
If the game isn't accessible:

✅ Check EC2 Security Group Settings: Make sure port 8080 is open to inbound traffic.

📝 View Container Logs:
 -> docker logs <container_id>
🔄 Restart the Container:
-> docker restart <container_id>



**🎉 Huuurrrraaaayyyyyyyy! You did it! 🥳
Enjoy your classic Super Mario Bros game running from the cloud!**

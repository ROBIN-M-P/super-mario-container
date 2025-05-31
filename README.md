# super-mario-container
"Dockerized Super Mario Bros HTML5 game. Easily deployable and accessible via a containerized web server."
Overview:
Deploy a Super Mario Bros HTML5 game inside a Docker container on an AWS EC2 instance.
Prerequisites
- An AWS EC2 Ubuntu 22.04 instance.
- SSH access with a key pair.
- Docker installed on the instance
**Installation Steps**
1- Connect to your EC2 instance:
ssh -i "keypair.pem" "user"@"public_ip"
2- Update system packages:
sudo apt update
3- Install Docker:
(Docker installation is the longest process, but necessary!)
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce -y
 5 - Verify Docker installation:
systemctl status docker
**Deploying the Super Mario Game**
1- Pull the Docker image from Docker Hub:
docker pull sevenajay/mario
2- Run the container using port mapping:
docker run -d -p 8080:80 sevenajay/mario
3- Access the game via browser:
Open:
http://your-server-ip:8080

- 🎉 Huuurrrraaaayyyyyyyy! You did it! 🥳

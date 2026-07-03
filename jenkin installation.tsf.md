## Installation of Java
sudo apt update
sudo apt install fontconfig openjdk-21-jre
java -version


## jenkins install
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins



## You can enable the Jenkins service to start at boot with the command:

sudo systemctl enable jenkins

## You can start the Jenkins service with the command:

sudo systemctl start jenkins

## You can check the status of the Jenkins service using the command:

sudo systemctl status jenkins


## Chatgpt bash menthod:

#!/bin/bash

echo "Updating package list..."
sudo apt update

echo "Installing Java..."
sudo apt install -y fontconfig openjdk-21-jre

echo "Checking Java version..."
java -version

echo "Creating keyrings directory..."
sudo mkdir -p /etc/apt/keyrings

echo "Downloading Jenkins GPG key..."
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key

echo "Adding Jenkins repository..."
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | \
sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

echo "Updating package list..."
sudo apt update

echo "Installing Jenkins..."
sudo apt install -y jenkins

echo "Enabling Jenkins service..."
sudo systemctl enable jenkins

echo "Starting Jenkins service..."
sudo systemctl start jenkins

echo "Checking Jenkins status..."
sudo systemctl status jenkins --no-pager

echo "Initial Admin Password:"
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
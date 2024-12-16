Doc: https://linuxiac.com/how-to-install-docker-on-debian-12-bookworm/


Step 1 
sudo apt update
sudo apt install apt-transport-https ca-certificates curl gnupg

Step 2 
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker.gpg

Step 3
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker.gpg] https://download.docker.com/linux/debian bookworm stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

Step 4
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl is-active docker

Verify
sudo docker run hello-world

Enabling non root user
sudo usermod -aG docker ${USER}
reboot

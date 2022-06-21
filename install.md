on debian

[https://docs.docker.com/engine/install/debian/](https://docs.docker.com/engine/install/debian/)

```bash
# remove old version
sudo apt remove docker docker-engine docker.io containerd runc
# docker ce
# 1. Set up the repository
sudo apt update
sudo apt install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
# 2. Add GPG key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# 3. Use the following command to set up the repository:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# 4. install
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin


# enable service
sudo systemctl enable --now docker

# docker compose
sudo apt install docker-compose-plugin

# create networks
docker network create <network_name>

```

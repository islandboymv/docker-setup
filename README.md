# 🐳 Installing Docker on Ubuntu 22.04 🚀


## Setup the repository
```
sudo apt-get update
sudo apt-get install ca-certificates curl
```

## Add Docker’s official GPG key:
```
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

## Add the repository to Apt sources:
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Install Docker Engine
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

# Executing the Docker Command Without Sudo
By default, the docker command can only be run the root user or by a user in the docker group, which is automatically created during Docker’s installation process. If you want to avoid typing sudo whenever you run the docker command, add your `username` to the docker group:
```
sudo usermod -aG docker ${USER}
```
If you need to add a user to the docker group that you’re not logged in as, declare that `username` explicitly using
```
sudo usermod -aG docker username
```
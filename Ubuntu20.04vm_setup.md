# Ubuntu 20.04.2.0 LTS Setup

1. Install Ubuntu
2. English (US) - English (US), `Continue`
3. Minimal Installation, `Continue`
4. Erase disk and install Ubuntu, `Install Now`
5. Singapore, `Continue`
6. User: `vsnxncs`, Computer Name: `vsnxncs-VM`, PW: `password`




Run each of the following commands in order.

### Install VSCode
```
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt install code
```

### Install Python 3.7
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.7
```

### Install Docker

```
sudo apt-get update
sudo apt-get install \
  apt-transport-https \
  ca-certificates \
  curl \
  gnupg \
  lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
You should now be able to run
```
sudo docker run hello-world
```

### Install Docker-Compose
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```
You should now be able to run
```
docker-compose --version
```

### Docker Post install
```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```
You should now be able to run
```
docker run hello-world
```

### Install Python3 venv
```
sudo apt-get install python3-venv
```

### Install AWS CLI V1
```
curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"
unzip awscli-bundle.zip
sudo ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
```

### Install PostgreSQL
```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql
```
### Install Python3 pip
```
sudo apt install python3-pip
```

### Install pipenv
```
sudo pip install pipenv
```

# Vision Setup
Go to GitLab, and get the HTTPS link from Clone.

`cd` into your working directory e.g. `cd Desktop`, and run `git clone <VISION HTTPS Clone link>`.

`cd` into the vision folder.

1. Run Setup: `bin/dev_env_setup.sh`
2. Activate virtual environment: `pipenv shell`
3. Setup Mock DB: `bin/mockDB_setup.sh`

Follow main `README.md` for the rest of the pgadmin setup.

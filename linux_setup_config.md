### Install Virtualbox guest editions (resize Ubuntu Desktop within Virtualbox window)

[StackExchange](https://askubuntu.com/questions/104440/how-do-you-resize-the-standard-ubuntu-desktop-inside-of-virtualbox)
```
sudo apt-get install virtualbox-guest-dkms virtualbox-guest-utils virtualbox-guest-x11
```

### Install VSCode

[Linuxize](https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-20-04/)
```
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt install code
```

### Install Atom

[Atom Documentation](https://flight-manual.atom.io/getting-started/sections/installing-atom/#platform-linux)
```
wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'
sudo apt-get update
sudo apt-get install atom
```

### Install Brave

[Brave](https://brave.com/linux/)
```
sudo apt install apt-transport-https curl
sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
sudo apt update
sudo apt install brave-browser
```

### Install Slack

[Download .DEB app](https://slack.com/intl/en-sg/downloads/linux)
### Install Docker

[Docker Documentation](https://docs.docker.com/engine/install/ubuntu/)
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

Test to see Docker is installed
```
sudo docker run hello-world
```

Docker Post-Installation

[Docker Documentation](https://docs.docker.com/engine/install/linux-postinstall/)
```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

Test Post-Installation
```
docker run hello-world
```
### Install pip
```
sudo apt install python3-pip
```

### Install Python 3.7

[StackExchange](https://askubuntu.com/questions/1251318/how-do-you-install-python3-7-to-ubuntu-20-04)
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.7
```

### Install PostgreSQL

[PostgreSQL](https://www.postgresql.org/download/linux/ubuntu/)
```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql
```

### Install AWS Command Line Interface

[AWS Documentation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html)
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

### Python is Python 3
[StackExchange](https://askubuntu.com/questions/1144446/python-installed-in-ubuntu-but-python-command-not-found)
```
sudo apt-get install python-is-python3
```

### Install Python Packages

```
pip install dicttoxml
pip install numpy
pip install pandas
pip install boto3
pip install flake8
pip install sqlalchemy
pip install datetime
```

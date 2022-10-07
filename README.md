# HAQQ monitoring and alerting

Start the installation by ensuring that all the packages used by docker as dependencies are installed.

```
sudo apt update
sudo apt -y install apt-transport-https ca-certificates curl gnupg2 software-properties-common

curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-archive-keyring.gpg

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io -y

sudo systemctl enable --now docker
```

Install docker-compose script
```
sudo curl -L https://github.com/docker/compose/releases/download/1.25.3/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

Clone GIT repo 

```
cd /opt 
git clone https://github.com/CroutonDigital/monitoring.git
cd monitoring
```

Edit conf file volumes/tenderduty/config.yml, and set telegramm channel, API key. And add your RPC node 

Also need setup traefik proxy for you domain names in folder volumes/traefik/custom/. 







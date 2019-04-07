
![DockerPlex](https://raw.githubusercontent.com/BeefBytes/Assets/master/DockerPlex/logos/png/logo_dockerplex_orange_742x120.png)

# About
This project was initially meant for personal use only, but I thought it could be useful for others too. Plex setups are becoming more popular and it can be very time consuming when setups get complex. The aim of this project is to make complex setups simple.

## Getting Started
Even though this setup is somewhat complex, the guide will be covering everything from installing docker to setting up reverse proxy. As long as docker is correctly installed, it doesn’t matter what distro is being used for this setup. This guide will be using ubuntu.

### Requirements
- Basic command line knowledge
- Cloudflare account (free)
- Domain behind Cloudflare
- Dedicated server (Hetzner / SoYouStart recommended)

### Installing docker & docker-compose
Skip this step if you already have docker and compose installed.

<b>Installing docker</b><br />
```
wget -qO- https://get.docker.com/ | sh
```

<b>Adding your user to docker group</b><br />
```
sudo usermod -aG docker username
```

<b>Installing docker-compose</b><br />
```
curl -L https://github.com/docker/compose/releases/download/1.24.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```

<b>Apply executable permissions to the binary</b><br />
```
sudo chmod +x /usr/local/bin/docker-compose
```

## Setting up services
First you’ll need to clone the repository<br />
```
git clone https://github.com/DockerPlex/dockerplex-compose.git
```


![DockerPlex](https://raw.githubusercontent.com/BeefBytes/Assets/master/DockerPlex/png/logo_dockerplex_orange_742x120.png)

# About DockerPlex
This project was initially meant for personal use only, but I thought it could be useful for others too. Plex setups are becoming more popular and it’s very time consuming when setups get complex. The aim of this project is to make complex setups less time consuming. The setup covers:

- Automated downloads for tv shows and movies
- Web page for searching for movies and tv shows
- Reverse proxy with auto renewed certificates 
- Page for viewing many different stats about your plex server

You’ll be able to search for any tv show or movie and simply click “add”, the rest will be taken care of automatically. Every service used will be behind a reverse proxy making sure it’s secure. List of software used in this setup:

- Plex (displays media duh..)
- Traefik (reverse proxy, also handles certificates)
- Deluge (torrent client)
- Sonarr (manages tv shows)
- Radarr (manages movies)
- Ombi (search engine for movies and tv shows)
- Plexpy (displays stats about your plex server)
- Transcoder (converts media from h264 to h265)
- Jackett (adds support for more torrent sites)

All of this will be ran inside docker containers using docker compose. For more in-depth explanation about each software and how everything works together, scroll down to the bottom of this page.

## Getting Started
Even though this setup is pretty complex, the guide will be covering everything from installing docker to setting up reverse proxy. As long as docker is correctly installed, it doesn’t matter what distro is being used for this setup. I’ll be using ubuntu.

### Requirements
- Basic command line knowledge
- Cloudflare account (it’s free)
- Domain behind Cloudflare
- Dedicated server (recommend: Hetzner / SoYouStart)

### Installing docker & docker-compose
Skip this step if you already have both installed.

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
curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-composechmod +x /usr/local/bin/docker-compose
```

<b>Apply executable permissions to the binary</b><br />
```
sudo chmod +x /usr/local/bin/docker-compose
```

## Installation
First you’ll need to clone the repository<br />
```
git clone https://github.com/edyyy/DockerPlex
```

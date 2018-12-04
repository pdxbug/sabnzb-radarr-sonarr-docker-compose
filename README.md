# sabnzb-radarr-sonarr-docker-compose
Files used to create sabnzb-radarr-sonarr web server in docker-compose. Will also include the files to uncompress and delete and notes on getting all to work. 

Description:
These files are used to create a web server for sabnzb, radarr, sonarr, mariadb and a standard webpage using nginx, fastcgi. I used images from a colleague (adduc) for the nginx, mariadb portions to host my personal website. The media management was pulled from https://github.com/justinhamlett/usenet-docker/blob/master/docker-compose.yml and modified for my needs. 

Requirements:
I don't have any huge system requirements and have this running on an older Intel dual core system with 8 GB of memory. I am the only one using the system and it runs great. I am running Ubuntu 18.04.1 LTS Server and have installed SSH, docker, git, and samba. 
For MariaDB to work you need to download the repository from https://github.com/MariaDB/server and place it in /media/root/Storage/Downloads/Repositories
Update enteryourserveripaddress:3306:3306 and change the secretpassword

Move the convertdelete into /etc/cron.hourly
Modify it to your needs. If you modify the /media/root/Storage folders, you will need to also modify this file accordingly

Notes:
I run my Storage on a larger media drive and not on the smaller system SSD. I've created a symlink to the storage drive in /home/root/Storage and /home/$USER/Storage to easily access when logging in. Feel free to modify this for your needs.

I had issues with the latest PLEX server, so I force 146 until something else updates and forces the change.

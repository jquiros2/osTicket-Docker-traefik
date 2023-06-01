#this is a fork of https://github.com/VincentSC/osTicket-Docker trying to adapt it to traefik and php8.1 among other things.
It is nonworking.  I will document changes when it is functional. 
--------------------------------------------------------------------------
This is the docker version to *migrate* your osTicket to Docker.

- `update.sh` grabs the latest version of osTicket from Github
- `Dockerfile` builds a new Docker using Apache
- `docker-compose` uses traefik-proxy.

If you want to start a new osTicket, make sure you temporarily avoid the removing of the setup-dir in `update.sh`. Also avoid the copy of `ost-config.php`, but do check the info you need to add in. After installation copy the generated file.

To update:
- run `update.sh`. Check for errors.
- run docker-compose up -d --build
- wait, as this takes several minutes

This docker is used in production. I'm sharing these files, so I can learn while helping others.

For first use, remove info.txt, else it wil be "up-to-date". Also add your old SALT into `ost-config.php`.

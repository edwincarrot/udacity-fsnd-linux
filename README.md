# Udacity FSND - Linux Server Configuration

## About
This project deploys the catalog application to a linux server which is secured and also hosts as our database server

- IP address: http://54.202.75.10
- Port: 2200
- URL: http://54.202.75.10.xip.io/

## Software installed
- apache2
- python3
- libapache2-mod-wsgi-py3
- postgresql
- git

## Configuration made
- In `/etc/ssh/sshd_config`
    -  Change the default port for ssh from `22` to `2200`
    -  Set `PermitRootLogin` and `PasswordAuthentication`to `no`to disable root login and password based login through ssh
- Incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123) are allowed through UFW
- Add `WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi` to `/etc/apache2/sites-enabled/000-default.conf`

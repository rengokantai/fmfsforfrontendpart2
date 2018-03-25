# fmfsforfrontendpart2
## Server setup
### Node setup and installation
```
curl -sL | sudo -E bash -
```
```
npm config get prefix
```


###### 06:29
```
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
export PATH=~/.npm-global/bin:$PATH
source ~/.profile
```

## HTTPS
### Nginx Setup: Installation
### Nginx Setup: proxy traffic to node server
```
cd /etc/nginx/sites-available
vi default
```
```
location / {
  proxy_pass http://127.0.0.1:3000
}
```
using forever
```
forever start app.js
```

### Nginx Setup: Adding a domain name and opening port 443
```
server_name rengokantai.com yidi.me;
```
allow 443
```
ufw allow 443
```


### Installing HTTPS certificate
```
add-apt-repository ppa:certbot/certbot
apt update
apt install python-certbot-nginx
```

then
```
certbot --nginx
certbot renew --dry-run
```

## Nginx Tuning
### Nginx Tuning: Overview and Gzip
### Expires headers

```
# /var/etc/nginx/nginx.conf
gzip on;
```
```
location /static/ {
  expires 30d;
  proxy_pass http://
}
```

### Caching
```
proxy_cache_path /tmp/nginx levels=1:2
keys_zone=slowfile_cache:10m inactive=60m
use_temp_path=off
proxy_cache_key "$request_uri"
```

## Containers and more
Dedicated server
- shared resources
- no os
- fast deployment


## Database
### Database Types
### Database Best Practices
tips
- Back up your database
- Use a strong password
- Dont expose the database outside the network
- Sanitize your SQL
- back up your database


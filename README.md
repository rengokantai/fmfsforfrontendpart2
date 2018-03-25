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

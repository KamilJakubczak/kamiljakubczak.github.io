



## Setting up website with nginx 
1. Goto /etc/nginx/sites-avialable
2. Copy the default file and fill with settings of your website
(set at least **server name**)
3. Set sym link with your site configuration from **sites-available**
to **sites-enables**)
4. Reload nginx configuration with
```sh
systemctl reload nginx
```


## Adding  https certificate with cert bot
```sh
certbot --nginx
```

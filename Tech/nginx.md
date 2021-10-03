## setting a website on nginx
[nginx Setting_a_website_with_nginx_and_vultr](nginx/Setting_a_website_with_nginx_and_vultr)

# Nginx

## Config file location

```
/etc/nginx.nginx.conf
```

## Reload without restating the server

```
/etc/init.d/nginx reload
```

## Set URL if URL not found

```
location / {
    root /var/www/[your application]
    expires 3d;
    try_files @uri /index.html;
}
```

[Main M_KB](/README.md)
[Others](/Others/README.md)
# Ngnix Loadbalancer

Install Nginx
```
sudo apt install nginx
```

Check for Update
```
sudo apt update nginx
```

Do Upgrad if needed
```
sudo apt upgrade nginx
```

The Config-File is locatet in /etc/nginx/ nginx.conf

Edit the Config
```
sudo naon nginx.conf
```
Now delete all an replace with

```
events {
        worker_connections 100;
}

http {

        ##
        # Basic Settings
        ##

        tcp_nopush on;
        tcp_nodelay on;
        keepalive_timeout 65;

        include /etc/nginx/mime.types;
        default_type application/octet-stream;

        ##
        # SSL Settings
        ##

        ssl_protocols TLSv1 TLSv1.1 TLSv1.2 TLSv1.3; # Dropping SSLv3, ref: POODLE
        ssl_prefer_server_ciphers on;

        ##
        # Logging Settings
        ##

        access_log /var/log/nginx/access.log;
        error_log /var/log/nginx/error.log;

        ##
        # Servers
        ##
        upstream servers {
                server 10.1.38.42:80;
                server 10.1.38.43:80;
        }

        server {
                listen 80;
                location / {
                        proxy_pass http://servers;
                }
        }
}
```
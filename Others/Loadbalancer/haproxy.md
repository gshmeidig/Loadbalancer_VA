[Main M_KB](/README.md)
[Others](/Others/README.md)
# HAProxy

Installation Versione check: [HAProxy Install](https://haproxy.debian.net/)

## Configuriaton
Edite haproxy.cfg with [Vim]()
```
sudo vim /etc/haproxy/haproxy.cfg
```

To Config:
```
frontend webapps *:80
 default_backend webapps

backend webapps
   server webapp1 webapp1.va.ch:80 check
   server webapp2 webapp2.va.ch:80 check
```

Restart HAProxy:
```
sudo systemctl restart haproxy
```

Test if its Started:
```
sudo systemctl restart haproxy
```
### Test Loadbalancer
On the Loadbalancer, execute the following command four times. Everytime there should be a message form a diffrent server.
```
curl localhost
```

To do a Live Test with a querry which last 1000 seconds:
```
for i in {1..1000};do curl localhost &&sleep 1;done;
```

Now disable one of the Server:
```
sudo systemctl stop httpd
```


Cloud-init for Test webapps-server:
```
#cloud-config
packages:
  - nginx
write_files:
 - content: |
    <html>
     <body>
      <h1>Webapp 1</h1>
     </body>
    </html>
   path: /var/www/html/index.html
   permissions: '0644'
```
```
#cloud-config
packages:
  - nginx
write_files:
 - content: |
    <html>
     <body>
      <h1>Webapp 2</h1>
     </body>
    </html>
   path: /var/www/html/index.html
   permissions: '0644'
```

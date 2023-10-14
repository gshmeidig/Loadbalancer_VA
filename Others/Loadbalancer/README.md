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
   server webapp1 webapp1.va.ch
   server webapp2 webapp2.va.ch
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

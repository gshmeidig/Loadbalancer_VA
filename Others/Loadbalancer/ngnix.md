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
worker_processes 1;
events {
	worker_connections 1024;
}

http {
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
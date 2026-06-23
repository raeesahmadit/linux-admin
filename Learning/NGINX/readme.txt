NGINX: is a web server accepts request via HTTP/s and respond to display website content through storing, processing 
        delivering web pages to usres
        - can also be used as a reverse proxy, load balancer, mail proxy and HTTP cache
        - Airbnb, Netflix, Wordpress deploy NGINX for scalability, performance

install: 
       1- sudo vi /etcc/yum.repos.d/nginx.repo
       2- add following to nginx.repo :
                    [nginx]
                    name=nginx repo
                    baseurl=hhtps://nginx.org/packages/centos/8/$basearch/
                    enable=1
        3- sudo yum update
        4- sudo yum install nginx

start/stop: 
          systemctl status/start/stop NGINX        or
          curl -I 127.0.0.1

configs: 
         /etc/nginx/nginx.conf
         /usr/share/nignx/html

logs:
        /var/log/nginx/
        - error.log
        - access.log
        
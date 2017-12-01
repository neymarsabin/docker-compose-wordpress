# Docker and Wordpress
Docker compose file for setting up wordpress in local environment alongside phpmyadmin. 

Ultimately, **DigitalOcean** has good tutorial on how to [setup docker in ubuntu 16.04.](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)
```
wordpress:
  image: wordpress
  links:
    - wordpress_db:mysql
  ports:
    - 8080:80
wordpress_db:
  image: mariadb
  environment:
    MYSQL_ROOT_PASSWORD: examplepass
phpmyadmin:
  image: corbinu/docker-phpmyadmin
  links:
    - wordpress_db:mysql
  ports:
    - 8181:80
  environment:
    MYSQL_USERNAME: root
    MYSQL_ROOT_PASSWORD: examplepass
```

Please replace  your MySQL username and password!

For full tutorial on how to setup **wordpress** using _docker-compose_ please visit [How To Install Wordpress and PhpMyAdmin with Docker Compose on Ubuntu 14.04.](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-and-phpmyadmin-with-docker-compose-on-ubuntu-14-04)

Docker LEMP
===========

- nginx
- php7-fpm
- mysql
- elk

To run these containers : ```docker-compose up```.

Others commands
---------------

```
#  IP of nginx container
docker inspect --format '' $(docker ps -f name=nginx -q)
# Add host of the app
sudo echo "ip_container_of_nginx symfony.dev" >> /etc/hosts
# Bash
docker-compose exec php bash
# Composer (ex : composer update)
$ docker-compose exec php composer update
# Commandes Symfony
$ docker-compose exec php php /var/www/symfony/app/console cache:clear
# Command Symfony bis (with alias)
$ docker-compose exec php bash
$ sf cache:clear
# Command MySQL
$ docker-compose exec db mysql -uroot -p"root"
# Remove cache/logs ;)
$ sudo chmod -R 777 symfony/app/cache symfony/app/logs
# Stats CPU
$ docker stats $(docker inspect -f "" $(docker ps -q))
# Remove containers
$ docker rm $(docker ps -a -q)
```

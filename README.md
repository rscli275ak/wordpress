# Docker running complete wordpress site

## First tests

    docker container run --name wordpress -p80:80 -e WORDPRESS_DB_PASSWORD=secret --network wp_network -v ~/Docker/wp.local/www:/var/www/html -dit wordpress
    docker container run --name phpmyadmin -p 8080:80 -e PMA_HOST=mysql --network wp_network -dit phpmyadmin/phpmyadmin
    docker container run --name mysql --network wp_network -v ~/Docker/wp.local/db:/var/lib/mysql -dit -e MYSQL_ROOT_PASSWORD=secret mysql:5.7

## Enhancements

    * moving docker configuration in subfolder
    * prevent database volume from mounting on host
    * new .gitignore wordpress specific
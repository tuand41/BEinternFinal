docker-compose build
docker-compose up
docker-compose exec mysql sh
mysql -u root -p iotcms < /var/lib/mysql-db-backup/backup.sql
docker-compose exec php-fpm php artisan key:generate
docker-compose exec php-fpm php artisan cache:clear
// Remember to update ./app/.evn => DB_HOST=mysql

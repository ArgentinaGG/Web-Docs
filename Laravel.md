# ISPConfig - Bitbucket Install

```sh
cd /var/www/site/private
sudo -u web41 ssh-keygen (copy .ssh/id_rsa.pub to Bitbucket or GitHub deploy keys)
sudo -u web41 git clone git@bitbucket.org:xxx/yyy.git .
sudo -u web41 cp .env.example .env
sudo -u web41 composer install
php artisan key:generate

sudo -u web41 ln -s /var/www/site/private/public/ /var/www/site/web/
sudo -u web41 php artisan storage:link
```
Different PHP Version for project:
```sh
sudo -u web41 php8.3 /usr/bin/composer install
sudo -u web41 php8.3 artisan storage:link
```

## Apache Directives (ISPConfig)
DocumentRoot "{DOCROOT_CLIENT}/public"

# Install Laravel
```sh
composer create-project laravel/laravel dirnameproject
```
```sh
php artisan migrate:fresh ; php artisan db:seed

sudo -u web36 git pull
```

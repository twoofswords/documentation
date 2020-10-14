## laravel 

#### setting up php and required php extensions for laravel
```bash
sudo apt install php php7.4-common php7.4-bcmath php7.4-ctype php7.4-json php7.4-mbstring php7.4-xml php7.4-tokenizer php7.4-zip openssl
```

#### enable php extension in ubuntu
```bash
sudo nano /etc/php/7.4/apache2/php.ini
```
```diff
-;extension=fileinfo
+extension=fileinfo
-;extension=openssl
+extension=openssl
```

#### install composer and make it globally executable
```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '795f976fe0ebd8b75f26a6dd68f78fd3453ce79f32ecb33e7fd087d39bfeb978342fb73ac986cd4f54edd0dc902601dc') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
sudo php composer-setup.php --install-dir=/bin --filename=composer
php -r "unlink('composer-setup.php');"
```

#### install laravel and add it to path
```bash
composer global require laravel/installer
echo 'export PATH="$PATH:$HOME/.config/composer/vendor/bin"' >> ~/.bashrc
source ~/.bashrc
```

#### create new laravel project
```bash
laravel new MyApplication
```
or 
```bash
laravel new MyApplication --auth
```

#### launch server locally
```bash
cd MyApplication
php artisan serve
```
[Reference 1](https://getcomposer.org/download/)  
[Reference 2](https://laravel.com/docs/8.x/installation)  
[Reference 3](http://www.linuxandubuntu.com/home/install-laravel-in-ubuntu-20-04-lts)

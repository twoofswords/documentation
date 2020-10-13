## mongodb

#### install mongodb by adding developer key and repository
```bash
wget -q -O - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
sudo apt update
sudo apt install mongodb-org
```

#### start mongodb and enable its service
```bash
sudo systemctl start mongod.service
sudo systemctl status mongod
sudo systemctl enable mongod
mongo --eval 'db.runCommand({ connectionStatus: 1 })'
```
[Reference 1](https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-20-04)

#### install robo3t (mongodb gui) via snap
```bash
sudo snap install robo3t-snap
```
[Reference 1](https://askubuntu.com/questions/739297/how-to-install-robomongo-on-ubuntu)

#### install mongodb php driver
```bash
sudo apt install php-dev php-pear
sudo pecl install mongodb
sudo nano /etc/php/7.4/apache2/php.ini
```
```diff
;extension=xsl
+extension=mongodb.so
```

[Reference 1](https://www.php.net/manual/en/mongodb.installation.pecl.php)

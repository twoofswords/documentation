## install curl (and remove wget)
```bash
sudo apt install curl
sudo apt remove --purge wget
sudo apt autoremove --purge
```

### install rust
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## mongodb

#### install mongodb by adding developer key and repository
```bash
curl -fsSL https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
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

## basic CRUD app with actix and mongodb
[Reference 1](https://dev.to/jbarszczewski/rust-actix-cosmosdb-mongodb-tutorial-api-17i5)

#### create a new project
```bash
cd ~/Desktop
cargo new {project-name}
cd {project-name}
nano Cargo.toml
```
```diff
;[dependencies]
+actix-rt = "1.1.1"
+actix-web = "2.0"
```


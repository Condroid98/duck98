# membuat pesbuk

install webserver
```
sudo apt-get install -y apache2 && apt-get install -y php php-mysql
```

install database ext
```
sudo apt-get install -y mysql-server
```

ambil file master.zip
```
sudo apt-get install wget -y
wget  https://github.com/Condroid98/duck98/master.zip
```

ekstrak File
```
sudo apt-get unzip -y
unzip master.zip
```

buat user
```
sudo mysql -u root
create user 'devopscilsy'@'localhost' identified by '1234567890';
grant all privileges on *.* to 'devopscilsy'@'localhost';
```

buat database di user yang sudah di buat
```
mysql -u devopscilsy -p1234567890 <<hehe
create database dbsosmed;
```

hapus file di var/www/html
```
sudo rm -rf /var/www/html
```

pindahkan file yang sudah di ekstrak
```
sudo mv sosial-media-master/*  /var/www/html
````

masuk folder kemudian lakukan dump
```
cd /var/www/html
mysql -u devopscilsy -p1234567890 dbsosmed < dump.sql
```

restart webserver apache2
```
sudo systemctl restart apache2
```
akses localhost atau IP public

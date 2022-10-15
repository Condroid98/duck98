# membuat pesbuk

Install webserver
```
sudo apt-get install -y apache2 && apt-get install -y php php-mysql
```

Install database ext
```
sudo apt-get install -y mysql-server
```

Download alat tempur
```
sudo apt-get install wget -y
wget https://github.com/Condroid98/duck98/archive/duck98-main.zip
```

Ekstrak File
```
sudo apt-get unzip -y
unzip duck98-main.zip
```

Buat user
```
sudo mysql -u root
create user 'devopscilsy'@'localhost' identified by '1234567890';
grant all privileges on *.* to 'devopscilsy'@'localhost';
```

Buat database di user yang sudah di buat
```
mysql -u devopscilsy -p1234567890 <<hehe
create database dbsosmed;
```

Hapus file di var/www/html
```
sudo rm -rf /var/www/html
```

Pindahkan file yang sudah di ekstrak
```
sudo mv duck98-main/*  /var/www/html
````

Masuk folder kemudian lakukan dump
```
cd /var/www/html
mysql -u devopscilsy -p1234567890 dbsosmed < dump.sql
```

Restart webserver apache2
```
sudo systemctl restart apache2
```

#Akses localhost(127.0.0.1) atau IP public

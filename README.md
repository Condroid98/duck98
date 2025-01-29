# membuat pesbuk

Install webserver
```
sudo apt-get install apache2 -y && sudo apt-get install php php-mysql -y
```

Install database ext
```
sudo apt-get install mysql-server -y 
```

Alat tempur
```
sudo apt-get install wget -y && wget https://github.com/Condroid98/pesbuk/archive/master.zip
```

Ekstrak File
```
sudo apt-get install unzip -y && unzip master.zip
```

Buat user
```
sudo mysql -u root 
create user 'devops'@'localhost' identified by 'qwerty123';
grant all privileges on *.* to 'devops'@'localhost';
FLUSH PRIVILEGES;
```

Buat database di user yang sudah di buat
```
mysql -u devops -pqwerty123
create database dbsosmed;
```

*khusus Database MYSQL yang digunakan untuk membuat bash script harus menyertakan tanda "<<" exmaple :
```
mysql -u data -porang <<EOFMSQL
create database testdb;
EOFMYSQL
```

Hapus file di var/www/html
```
sudo rm -rf /var/www/html/*
```

Pindahkan file yang sudah di ekstrak
```
sudo mv pesbuk-production/*  /var/www/html
````

Masuk ke dalam folder kemudian lakukan dump
```
cd /var/www/html
mysql -u devops -pqwerty123 dbsosmed < dump.sql
```

Restart webserver apache2
```
sudo systemctl restart apache2
```

#Akses localhost(127.0.0.1) atau IP public

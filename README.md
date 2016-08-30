# MongoDB
Veritabanı istemcisi.
## İndirme ve Yükleme
```bash
mkdir Kurulum
cd Kurulum
wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-ubuntu1604-3.2.9.tgz
tar -xvf mongodb-linux-x86_64-ubuntu1604-3.2.9.tgz
cp -R mongodb-linux-x86_64-ubuntu1604-3.2.9/bin ../
```
## Oturum Servisi Olarak Arka Planda Çalıştırılması
```bash
mongod --config mongod.conf 
```

## Veritabanı Kullanıcı ve Şifre Atama
[Enable Auth — MongoDB Manual 3.2](https://docs.mongodb.com/manual/tutorial/enable-authentication/)'deki yönergeler takip edildi.
```bash
mongo
```
```javascript
use hasse
db.createUser(
  {
    user: "fenrihen",
    pwd: "xyz123",
    roles: [ { role: "readWrite", db: "hasse" }],
  }
)
exit
```
```bash
pkill mongod
mongod --auth --config mongod.conf
mongo
```
```javascript
use hasse
db.auth("fenrihen","xyz123")
```



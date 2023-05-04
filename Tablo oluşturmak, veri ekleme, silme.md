# Tablo Oluşturmak
- constraint  kısıtlama anlamına gelir. oluşturularacak kadar sütun eklenir. bir sütunun 3 özelliği girilir. sütun ismi, değişken türü, sütuna girilecek verinin özeliği girilir
``` SQL
CREATE TABLE <table_name>(
<column_name> <data_type> <constraint>,  
<column_name> <data_type> <constraint>,
);
```


``` SQL
CREATE TABLE autor (
	id SERIAL PRIMARY KEY,  otamatik olarak oluşturulur ve giderek artar
	firs_name VARCHAR (50) NOT NULL,
	last_name VARCHAR (50) NOT NULL,
	email VARCHAR (100) ,
	birthday DATE 
);
```
- Veri Eklemek için

``` SQL
INSERT INTO autor ( firs_name, last_name, email, birthday)
VALUES
	('Haruki', 'Murakimi','haruki12@gmail.com', '1948-11-07'),
	('Sabahattin' , 'Ali' , 'Sabah.123@gmail.com', '1914-07-11'),
	('Orhan', 'Pamuk', ' Pamuk1234@gmail.com', ' 1956-09-15'),
	('Halide Edip' , 'Adıvar' , 'Halide456@gmail.com' , ' 1884-12-24');
```

- autor tablosu ile benzer bir tablo oluşturmak için
``` SQL
CREATE TABLE autor2 (LIKE autor);
```
- autor tablosundan herhangi bir veriyi autor2 tablosuna ekleyebiliriz.
``` SQL
INSERT INTO autor2
SELECT * FROM autor
WHERE firs_name = 'Orhan';
```
- içerisindeki bilgiler ile autor gibi bir tablo oluşturmak istersek
``` SQL
CREATE TABLE autor3 AS 
SELECT * FROM autor;
```
- Tablo silmek için Drop Table anahtar kelimeleri kullanılır.
- Bir hata mesajı ile karşılaşmamak için IF EXISTS yapısı kullanılabilir.
``` SQL
DROP TABLE IF EXISTS autor3; 
``` 
- sadece drop table anahtar kelimesi de kulalnılabilir.
``` SQL
DROP TABLE autor2;
```
Daha fazlası için;
- [W3Schools SQL CREATE](https://www.w3schools.com/sql/sql_create_table.asp)
- [W3Schools SQL DROP](https://www.w3schools.com/sql/sql_drop_table.asp)
- [PostgreSQL Tutorial SQL CREATE](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-create-table/)
- [PostgreSQL Tutorial SQL DROP](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-drop-table/)

# Veri güncellemek

- random veri elde etmek için [Mackaroo](https://www.mockaroo.com/)  sitesi kullanılıbilir
``` sql
insert into autor (first_name, last_name, email, birthday) values ('Derry', 'Flucker', 'dflucker0@dedecms.com', '1959-05-20');
insert into autor (first_name, last_name, email, birthday) values ('Nikkie', 'Revell', 'nrevell1@spotify.com', '2010-08-16');
insert into autor (first_name, last_name, email, birthday) values ('Colby', 'Fittes', 'cfittes2@tripadvisor.com', '1914-12-15');
```
## update
``` sql
UPDATE <table_name>
SET column1= value1,
	column2= value2,
	...
WHERE condition;
```
- id si 10 olan veriyi güncellemek için
``` sql
UPDATE autor
SET first_name = ' Emrah Safa',
	last_name = 'Gürkan',
	email = ' emrah_123@gmail.com',
	birthday = '1988-12-23'
WHERE id= 10;
```
- ismi V harfi ile başlayan verilerin isim ve soyisimlerinin güncellemek için
``` sql
UPDATE autor
SET first_name = 'XXX',
	last_name = 'YYY'
WHERE first_name LIKE 'V%';
```
- ismi Tan olan kişinin yada kişilerin soyadını Update olarak değiştir. bu değişikliğin yapıldığı satırların gözükmesi için returning kelimesi kullanılır.
``` sql
update autor
set last_name = 'Update'
where first_name= 'Tan'
returning *; 
-- tüm satırı  göstermesi için * konulur.
```
## Verileri silmek için
- id si 12 olan veriyi silmek için
 ``` sql
delete from autor
where id = 12;
```
- id si 75 den büyük verileri sil, silinen verileri göstermek için returning kelimesi kullanılır.
``` sql
delete from autor
where id >75
returning * ;
```
Daha fazlası için
-[W3Schools SQL UPDATE](https://www.w3schools.com/sql/sql_update.asp)
- [W3Schools SQL DELETE](https://www.w3schools.com/sql/sql_delete.asp)
- [PostgreSQL Tutorial SQL UPDATE](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-update/)
- [PostgreSQL Tutorial SQL DELETE](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-delete/)


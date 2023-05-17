# any all
``` sql
select first_name, last_name from autor
where id = 
(
select id from book 
	where title = 'What a Way to Go!' or title = 'Earthquake'
);
```
- id iki gelen değere atanamayacağı için hata verir bunun üstesinden gelmek için any anahtar kelimesini kullanırız
- bir sütundaki değeri alt sorgudan gelen iki değere atayabiliriz.
- any de id alt sorgudan gelen değerlere atanır ör id=4 ve ya id=5 olan verileri getirir.
``` sql
select first_name, last_name from autor
where id = any
(
select id from book 
	where title = 'What a Way to Go!' or title = 'Earthquake'
);
```

- all anahtar kelimesinde ise autor tablosunda tüm satırlar incelenir hepsi alt sorgudan gelen değerlere eşitse veriler gelir yoksa veri gelmez
``` sql
select first_name, last_name from autor
where id > all
(
select id from book 
	where title = 'What a Way to Go!' or title = 'Earthquake'
);

```
 daha fazlası için 
 - [W3Schools ANY ALL](https://www.w3schools.com/sql/sql_any_all.asp)
 - [PostgreSQL Tutorial ANY](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-any/)














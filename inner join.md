# inner join 

- önceki çalıştığımız tabloları siliyoruz.
``` sql
drop table products;
drop table users;
```
- join :birden daha fazla tablodaki verileri birleştirmemize yarar.

- her bir kitaba ait yazarın kitab adı ile beraber adının ve soy adının yazılmasını istiyoruz.
- birleştirmeler foreing_key üzerinden yapılır fakat zorunlu değildir
``` sql
select title, first_name, last_name from book
inner join autor on book.author_id = autor.id;
```
- join kelimesi tek başına yazılırsa da aynı değerler döner.
- gelen sütunların hangi tablodan geldiğini de gösterebiliriz.
``` sql
select book.title, autor.first_name, autor.last_name from book
join autor on book.author_id = autor.id;
```
- inner join yapısında book değil autor tablosundan da çağırabiliriz. 
``` sql
select title, first_name, last_name from autor
inner join book on book.author_id = autor.id;
```
daha fazlası için
- [W3Schools INNER JOIN](https://www.w3schools.com/sql/sql_join_inner.asp)
- [PostgreSQL Tutorial INNER JOIN](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-inner-join/)














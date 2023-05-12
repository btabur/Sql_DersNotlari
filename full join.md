# full join

- tablo 1 ve tablo 2 deki tüm verileri getirir. Eşleşmeyen değerler için null atanır.
- öncelikle eşleşen verileri getirir. 
- simetriktir. 
- full join ile full autor join aynı işleve sahiptir.
``` sql
select * from book
full join autor on autor.id = book.author_id;
```

- iki tablonun kesişimini verir yani inner join den de bulabiliriz. (AnB)
``` sql
select * from autor
full join book on autor.id = book.author_id
where (book.id is not null and autor.id is not null);
```
tablodaki ortak olmayan verileri getirmek için  (A/B n B/A)
``` sql
select * from autor
full join book on autor.id = book.author_id
where (book.id is  null or autor.id is  null);
```
daha fazlası için 
- [W3Schools FULL JOIN](https://www.w3schools.com/sql/sql_join_full.asp)
- [PostgreSQL Tutorial FULL JOIN](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-full-outer-join/)


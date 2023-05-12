# right join

 önecliği tablo 2 deki verileri alır ve tablo 1 de eşleşen verileri ekler

 önce yazar tablosundan tüm veriler gelir ve kitabı olan yazarların kitapları eklenir.
 
``` sql
select first_name, last_name, title from book
right join autor on autor.id = book.author_id;
```
right join ile right outer join aynı işleve sahiptir.

daha fazlası için

- [W3Schools RIGHT JOIN](https://www.w3schools.com/sql/sql_join_right.asp)
- [PostgreSQL Tutorial RIGHT JOIN](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-right-join/)
12.05.23


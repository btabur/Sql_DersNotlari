# intersect ve except

- iki sorgunun kesişimini verir.
- sütunlar da benzer terimler olması lazım (Veri tipleri)
- sütun sayıları da eşit olması lazım
``` sql
(
select * from book
order by pagenumber desc
limit 10 
)
intersect 
(
select * from book
order by title
limit 10
);
``` 
- except: ilk sorguda bulunan fakat ikinci sorguda bulunmayan verileri alır (A/B gibi) 
``` sql
(
select * from book 
order by pagenumber desc
limit 10
)
except
(
select * from book 
	order by title
	limit 10
);
```
 daha fazlası için
 - [PostgreSQL Tutorial INTERSECT](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-intersect/)
 - [PostgreSQL Tutorial EXCEPT](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-except/)
 17.05.23
























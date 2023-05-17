# Alt Sorgu

select * from book
where pagenumber > 94;

select pagenumber from book
where title = 'Fun';

- sayfa sayısını el ile girmek yerine alt sorgu yaparak progrramatik girebiliriz.

select * from book
where pagenumber > 
(
select pagenumber from book
where title = 'Fun'
);

- ortamlama kitap sayfa sayısından büyük olan kitapları getiriyoruz ve ortalama ile arasındaki farkı hesaplıyoruz.
select title, pagenumber, (select avg(pagenumber) from book), (select avg(pagenumber) from book) - pagenumber as differ
from book
where pagenumber > (select avg(pagenumber) from book);

daha fazlası için 
- [PostgreSQL Tutorial Subquery](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-subquery/)
17.05.23































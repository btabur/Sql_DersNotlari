# left join

- kesişimi değil soldaki olan  ilk tablodaki verileri önce alır daha sonra sağda ki tablodan bu eşleşenleri getirir.
- simetrik değildir.

önce yazar tablosunundaki tüm verileri getirir daha sonra kitap tablosundan eşleşen verileri getirir. kitabı olmayan yazarlara null atanır.
``` sql
select title, first_name, last_name from autor
left join book on autor.id=book.author_id;
```

önce tüm kitapları getirir daha sonra yazarr tablosundan kitabı olan yazarları getirir.
``` sql
select title, first_name, last_name from book
left join autor on autor.id=book.author_id;
```
 yazarı author tablosunda olmayan kitap eklemek için book tablosunda değişiklik yaptık
``` sql
alter table book
drop constraint book_author_id_fkey;
```
 book tablosuna yazarı author tablosunda olmayan bir kitap ekledik
``` sql
insert into book (title, pagenumber, author_id)
values ( 'Gülün Adı', 466, 85),
		('yapay zeka', 108, 99);
```		
	
 kitaları olan yazarları getirmek için 
``` sql
select title, first_name, last_name from autor
left join book on autor.id=book.author_id
where book.id is not null
order by book.title;
```

daha fazlası için
- [W3Schools LEFT JOIN](https://www.w3schools.com/sql/sql_join_left.asp)
- [PostgreSQL Tutorial LEFT JOIN](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-left-join/)
		

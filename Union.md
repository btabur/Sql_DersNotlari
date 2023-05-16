# Union

- sayfa sayısı en fazla olan 5 kitabı ve aynı zaman da isme göre de 5 kitabı seçmek istediğimizde kullanırız
- iki farklı select işlemini tek bir kümede gösterir.
- sayfa sayısı en fazla olan 5 kitap ile başlığa göre ilk 5 kitap toplam 10 kitap getirir. Kesişim kümesinde eleman var ile toplam sayı azalabilir.
- Kesişim kümesindeki elemanları iki kez göstemesi için union all kelimesi kullanılır. 
- Faklı tablodaki select komutlarını da birleştirebilir.
``` sql
(
select * from book
order by pagenumber desc
limit 5
) union
(
select * from book
order by title
limit 5
);
```
- birleştirilen sütun sayıları eşit olmalıdır. Bu sütunlardaki veriler de birbiri ile aynı olmalıdır.
``` sql
(
select id, email from autor
)
union
(
select id, title from book
);
```
daha fazlası için
- [W3Schools UNION](https://www.w3schools.com/sql/sql_union.asp)
- [PostgreSQL Tutorial UNION](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-union/)
16.05.23













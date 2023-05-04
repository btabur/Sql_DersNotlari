# Alias KUllanımı

- Sorgu esnasında tablodaki sütunlara geçici isimler vermemize yarar. Sütunların isimleri gerçekte değişmemektedir. 

``` SQL
SELECT first_name AS isim , last_name AS soyisim FROM actor;
```
- AS anahtar kelimesi ile yapılabileceği gibi kullanmadan da yapabiliriz
``` SQL
SELECT first_name  isim , last_name  soyisim FROM actor;
```
- Sütunlara birden fazla isim atayacaksak " " işaretleri arasına yamamız gerekli
``` SQL
SELECT first_name AS "isim testi" , last_name  "soyisim test" FROM actor;
```
- kullanım kolaylığı açısından AS anahtar kelimesi kullanılır

- karmaşık sorgularda verilerin okunmasında yardımcı olur
``` SQL
SELECT COUNT(*) AS "Aktor sayısı" FROM actor;
```
- Concat Fonksiyonu: sütunları birleştirmemize yarar
``` SQL
SELECT CONCAT ( first_name, ' ', last_name ) AS "İsim ve Soyisim" FROM actor;
```
Daha fazlası için
- [W3Schools SQL ALIAS](https://www.w3schools.com/sql/sql_alias.asp)
- [PostgreSQL Tutorial SÜTUN][ https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-column-alias/]

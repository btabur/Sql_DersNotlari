# Aggregate Fonksiyonlar

Max, Min, Avg, Sum

- Aggregate metodlar sonucu tek bir değer alınır
- replacement_cost değerinin maksimum değerini getirir 
``` SQL
SELECT MAX ( replacement_cost) FROM film;  
```
- rental_rate değerinin minimum değerini getirir.
``` SQL
SELECT MIN(rental_rate) FROM film ;
```
- filmleri uzunlukları ortalamasını getirir 
``` SQL
SELECT AVG (length) FROM film;
```
- filmlerin ortalamasını getirir. virgülden sonra üç basamağa kadar
``` SQL
SELECT ROUND(AVG (length), 3) FROM film;
```
- filmlerin rantel_rate değerlerinin toplamını getirir.
``` SQL
SELECT SUM(rental_rate) FROM film;
```
- un uzun ve en kısa filmler ile replacement_cost değerlerinin toplamını getirir.
``` SQL
SELECT MAX(length), MIN (length), SUM (replacement_cost) FROM film;
```
- rental_rate değeri 0.99 veya 2.99 olan filmler arasından en uzun filmi döndürür.
``` SQL
SELECT MAX (length) FROM film
WHERE rental_rate IN (0.99, 2.99);
```
Daha Fazlası için 
- [W3Schools Aggregate Function](https://www.w3schools.com/sql/sql_count_avg_sum.asp)
- [PostgreSQL Aggregate Function] (https://www.postgresql.org/docs/13/tutorial-agg.html)








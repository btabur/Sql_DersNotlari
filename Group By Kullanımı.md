# Group by kullanımı

- her bir farklı rantel_rate değerine göre en uzun film sürelerini getirir.
``` SQL
SELECT rental_rate,  MAX (length) FROM film
GROUP BY rental_rate;
```
- her bir farklı rantel_rate değerine göre film sayılarını getirir.
``` SQL
SELECT rental_rate,  COUNT (*) FROM film
GROUP BY rental_rate;
```
- select ve from kelimeler arasına iki paramatere yazıla bilir. birincisi group by da kullanılan değişken ikincisi aggregate fonksiyonları

- farklı rating değerlerine karşılık gelen film sayılarını getirir. 
``` SQL
SELECT rating , COUNT(*) FROM film
GROUP BY rating;
```
- farklı replacement_cost değerlerine karşılık en kısa filmleri getirir.
``` SQL
SELECT replacement_cost, MIN (length) FROM film
GROUP BY replacement_cost;
```
- replacement_cost ve rental_rate farklı değerlerine göre en kısa filmleri getirir. 
- 3 farklı renral_rate değeri ve 21 farklı  replacement_cost değeri ile toplam 3.21 63 tane değer gelir. 

``` SQL
SELECT replacement_cost, rental_rate, MIN (length) FROM film
GROUP BY replacement_cost, rental_rate
ORDER BY MIN (length);
```
- Verileri önce gruplayıp sonra sıralayacağımız için order by daha sonra gelir

Daha Fazlası için
- [W3Schools GROUP BY] (https://www.w3schools.com/sql/sql_groupby.asp)
- [PostgreSQL GROUP BY] (https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-group-by/)


# LIMIT ve OFFSET kullanımı
- limit ile görmek istediğimiz verilere sınırlama getiririz.
``` SQL
SELECT * FROM film
WHERE rental_rate = 4.99
ORDER BY length
LIMIT 20;
```
- LIMIT anahtar kelimesini en son yazıyoruz. Mantık olarak önce koşullara göre verileri alıyoruz sonra sıralıyoruz daha sonra kaç tane veri görmek istiyorsan lımıt anahtar kelimesini kullanıyoruz.

- replacement_cost değeri 14.99 ve rental_rate değeri 0.99 olan un uzun 7 filmi getirir.
``` SQL
SELECT * FROM film
WHERE replacement_cost = 14.99 AND rental_rate =0.99
ORDER BY length DESC
LIMIT 7;
```

- offset bazı verileri atlamamıza yardımcı olur.
-country tablosundan ilk altı veriyi atlayarak sonraki 4 veriyi listeler.
``` SQL
SELECT * FROM country
OFFSET 6
LIMIT 4;
```
``` SQL
SELECT * FROM actor
WHERE first_name = 'Penelope'
ORDER BY last_name
OFFSET 2
LIMIT 1;
```
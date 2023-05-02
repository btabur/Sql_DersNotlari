# Having kullanımı

Gruplanmış verilerimize koşullar uygulayabiliriz.

- film sayısı 325 den büyük olan rantel_rate değerlerini gösterir.
``` SQL
SELECT rental_rate,  COUNT ( * ) FROM film
GROUP BY rental_rate
HAVING COUNT (*) > 325;
```
- yukarı daki ile aynı sonucu alır. Hangi değeri çıkarcağımızı bildiğimiz için bu şekilde yapabildik
``` SQL
SELECT rental_rate, COUNT (* ) FROM film
where rental_rate!= 2.99
GROUP BY rental_rate;
```
- where satır bazlı bir filitreleme yaparken Having grup bazlı filitremeleme yapar.

- payment tablosunu staff_id değişkenine gruplayıp toplam satış adedi 7300 den büyük olan değeri döndürür.
``` SQL
SELECT staff_id, COUNT(*) FROM payment
GROUP BY staff_id
HAVING COUNT (*) > 7300;
```

- toplam alışverişi 100 den daha büyük müşterileri ve toplam alışveriş miktarlarını gösterir
``` SQL
SELECT customer_id, SUM (amount) FROM payment
GROUP BY customer_id
HAVING SUM (amount) > 100
ORDER BY SUM (amount) DESC;
 ```
 
Daha fazlası için

- [W3Schools SQL HAVING]( https://www.w3schools.com/sql/sql_having.asp)
- [PostgreSQL Tutorial SQL HAVING]( https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-having/)
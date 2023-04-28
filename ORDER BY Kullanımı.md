# Order by Kullanımı
- başlığıa göre artan sıralama
```
SELECT title, length FROM film
ORDER BY title ;  
``` 
- Herhangi bir şey yazılmadığında default olarak artan gelir.
```
SELECT title, length FROM film
ORDER BY title ASC;   
```
- azalan sıralama
```
SELECT title, length FROM film
ORDER BY title DESC ;   
```
- uzunluğuna göre artan bir sıra ile oluşur. 
```
SELECT title, length FROM film
ORDER BY length ;  
```
- İsminin baş harfi A ile başlayan rental_rate e göre artan , length değerine göre azalan filmleri getirir. Sıralama da öncelik ilk yazılana bağlıdır.
- ORDER BY operatorü koşul ifadelerinden sonra gelmelidir. 
```
SELECT title, rental_rate, length FROM film  
WHERE title LIKE 'A%'
ORDER BY rental_rate ASC , length DESC;
```
- rating değeri G olan filimleri length değerine göre artan sırada getirir.
```
SELECT * FROM film  
WHERE rating = 'G'
ORDER BY length;
```

Daha fazlası için

- [W3Schools ORDER BY](https://www.w3schools.com/sql/sql_orderby.asp);
- [PostgreSQL Tutorial ORDER BY](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-order-by/);
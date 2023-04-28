# DISTINCT  ve COUNT Kullanımı

* Bir değişkenin o veri grubunda aldığı benzersiz verileri görmemize yarar. Yani o değişken kaç farklı değer almış ve bunlar nelerdir?

- rental_rate değişkeninin kaç farklı değer aldığını gösterir.
```
SELECT DISTINCT rental_rate FROM film;
```
- rental_rate VE rating değerleri farklı olan verileri getirir.
```
SELECT DISTINCT rental_rate, rating FROM film;  
```
--------
## Count
- adı nick olan kaç kişi olduğunu gösterir.
```
SELECT COUNT(*) FROM actor
WHERE first_name = 'Nick';        			 
```
- ismi A harfi ile başlayan kaç kişi olduğunu gösterir.
```
SELECT COUNT(*) FROM actor
WHERE first_name LIKE 'A%'        			
```
- actor tablosunda kaç veri olduğunu gösterir
```
SELECT COUNT(*) FROM actor;      			
```
- ismi birbirinden farklı kaç veri olduğunu getirir.
```
SELECT COUNT( DISTINCT first_name ) FROM actor; 
```
- film tablosunda uzunluğu birbirinden farklı kaç film olduğunu gösterir.
```
SELECT COUNT(DISTINCT length ) FROM film;   	
```






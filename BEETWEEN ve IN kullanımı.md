# BETWEEN ve IN Kullanımı
```
SELECT title, length FROM film  
WHERE length>=90 AND length<=120;
```

Yukarıdaki gibi uzun uzun yazman yerine Between fonkisyonunu kullanabiliriz.

```
SELECT title, length FROM film
WHERE length BETWEEN 90 AND 120;
```
yukarıdaki ile aynı işlevi yerine geririr.

- 90 ve 120 arasında olmayan değerleri döndürür.
```
WHERE length NOT BETWEEN 90 AND 120; 
```
- rental_rate değişkeni 2 ile 4 arasındaki ve replacement_cost değeri 10 ile 20 arasındaki değerleri döndürür.
```
SELECT * FROM film
WHERE (rental_rate BETWEEN 2 AND 4) AND ( replacement_cost BETWEEN 10 AND 20); 
```
- uzunluğu 40, 50 , veya 60 olan filmleri döndürür.
```
WHERE length IN (40, 50, 60);  
```
- replacement_cost değeri 10.99 , 12.99 veya 16.99 olan filmleri döndürür.
```
WHERE replacement_cost IN ( 10.99, 12.99 , 16.99 ) ;  
```
- replacement_cost değeri 10.99 , 12.99 veya 16.99  flimleri döndürür.
```
WHERE replacement_cost NOT IN ( 10.99, 12.99 , 16.99 ) ; 
```






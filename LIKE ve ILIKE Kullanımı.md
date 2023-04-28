# LIKE ve ILIKE kullanımı

- LIKE operatörü büyük küçük harfe dikkat ederek arama yapar.Bu şekilde dikkat etmemesi için ILIKE kullanılır
- isminin başı Ma şeklinde olan verileri getirir. Ma harfinden sonra herhangi bir karekter de olabilir olmaya da bilir.
```
SELECT * FROM customer
WHERE first_name LIKE 'Ma%'; 
```
- % Sembolünün anlamı ya herhangi bir karakter yoktur veya birden fazla yer tutucu için yer işlevi görür
- isminin son karakteri y olan verileri geitirir.
```
SELECT * FROM customer
WHERE first_name LIKE '%y'; 
```
- ilk harfi A ve son harfi y ile biten isinleri getirir.
```
SELECT * FROM customer
WHERE first_name LIKE 'A%y';  
```
- ismi Ma ile VE soyadı A ile başlayan verileri getirir.
```
SELECT * FROM customer
WHERE first_name LIKE 'Ma%' AND last_name LIKE 'A%';  
```
- büyük küçük harf duyarlılığını ortadan kaldırır.
```
SELECT * FROM customer
WHERE first_name ILIKE 'a%';  
```
- ismin ilk harfi A olmayan verileri getirir.
```
SELECT * FROM customer
WHERE first_name NOT LIKE 'A%'; 
```
- Sadece tek bir karakter tutmak için _ alt tire eklenir.
```
SELECT * FROM customer
WHERE first_name LIKE 'J_an'; 
```
- İsmi J ile başlayıp n ile biten tüm veriler gelir.
```
SELECT * FROM customer
WHERE first_name LIKE 'J%n';  
```
- postgreSql de ~~ işareti de LIKE anlamındadır.
```
SELECT * FROM customer
WHERE first_name ~~ 'A%';  
```
- postgreSql de ~~* işareti de ILIKE anlamındadır.
```
SELECT * FROM customer
WHERE first_name ~~* 'a%'; 
```
- postgreSql de ! işareti de NOT anlamındadır.
```
SELECT * FROM customer
WHERE first_name !~~ 'A%';  
```
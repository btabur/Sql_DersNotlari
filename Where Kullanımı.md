# WHERE kullanımı

Koşulları listelemek için kullanılır. 
- film tablosundan koşul1 = 5 şartını sağlayan tüm verileri getirir.
```
SELECT * FROM film WHERE koşul1 = 5 ;          
```
- actor tablosundan adı Nick olan verileri getirir.
```
SELECT * FROM actor WHERE first_name= 'Nick' ; 
```
- film tablosundan uzunluğu 90 üzerinde olan flimleri getirir.
```
SELECT * FROM film WHERE length > 90 ;        
```
### Karşılatırma Operatörleri

1. <=   Küçük Eşittir
2. >=   Büyük Eşitttir
3. !=   Eşit Değildir
4. <>   Eşit Değildir

- AND operatorü: İki şartta doğru ise çalışır.
- actor tanlosundan ismi Nick VE soyadı Stallone olan verilerinden sadece firs_name ve last_name sütunlarını getirir. 
```
SELECT first_name, last_name FROM actor 
WHERE firs_name = 'Nick' AND last_name = 'Stallone' ;  
```
- OR operatorü: iki şarttan birinin doğru olması yeterlidir. OR dan sonra yeni filitreleme başalar. 
- actor tablosundan ismi Nick VEYA soyadı Bob olan verileri getirir.
```
SELECT * FROM actor
WHERE first_name = 'Nick' OR last_name = 'Bob' ;     
```

- NOT operatorü: İstenen şartların değilini (tümleyenini) getirir.
- film tanlosundan rantal_rate değeri 4.99 dışındaki verileri getirir.
```
SELECT * FROM film
WHERE NOT rental_rate = 4.99 ;   
```
- film tablosundan bu iki şartı da sağlayanların dışındaki elemanları getirir.
```
SELECT * FROM film 
WHERE NOT ( rental_rate = 4.99 AND replecemant_cost = 20.99 )   
```



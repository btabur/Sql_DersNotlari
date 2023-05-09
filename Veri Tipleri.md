# Veri Tipleri

``` sql
create table test(
real_type real,
	double_type double precision,
	numeric_type numeric 
);

insert into test
values 
(1.2345567865434567,
 1.2345567865434567,
 1.2345567865434567
);

select * from test;
```
- girdiğimiz sayının tam olarak ifade edilmesini istiyorsak numeric tür gireriz.
- real türde virgülden sonra 6 basamağa kadar hassasiyet vardır sonrasını yuvarlar.
- double precision türde virgülden sonra 15 basamağa kadar hassasiyet vardır. Sonrasını yuvarlar

``` sql
create table test2 (
float4_type float4,
float8_type float8,
decimal_type decimal );
```

- float4: real veri tipinin aynısıdır.
- float8: double precision veri tipinin aynısıdır.
``` sql
insert into test2
values (
	1.2345567865434567,
	1.2345567865434567,
	 1.2345567865434567);

select * from test2;

select (10.0 :: integer);  --hangi tür olduğunu belirtiyoruz.

select (12.2234567654345676543 :: real);

select (12.2234567654345676543 :: numeric);
```
## Character Types

``` sql
select('lorem' :: char(10));
```
- char kelimesi bize istediğimiz uzunlukta bir yer ayırır. daha az girilmesi durumunda ayrılan alan aynı şekilde kalır.
``` sql
select('lorem' ::varchar(10));
```
- varchar kelimesi de istediğimiz uzunlukta yer ayırır fakat daha küçük veri girilirse ayrılan alaz azalabilir.
``` sql
select ('lorem impus dolar sit'::varchar);
```
- sınırlandırma girmediğimizde yazılan değer kadar boşluk oluşur.
``` sql 
select( 'lorem impus dolar sit at the bank':: text);
```
- text kelimesi ile sınırlandırma olmadan istenilen uzunlukta değer girilebilir.

## Boolean Veri Tipi

- true, yes, on, 1 , t gibi değerler TRUE değer döndürür.
-false, no , off, 0, f gibi değerlerde FALSE değer döndürür.

```sql
select( 'on' :: boolean);  -- değeri true olarak gözükür.

select(0 :: boolean);  -- değeri false olarak görünür.

select(null:: boolean); --null olarak gözükür.

```

## Date Veri Tipleri

- Tarihi gösterirken
``` sql
select( '1980-12-030'::date);
select ('dec-03-1980'::date);
select('dec 03 1980'::date);
```
- herhangi bir veri türü yazılmaz ise default olarak text olarak belirlenir. 
``` sql
select('1980 December 03'); 
``` 

- Saati gösterirken
- saniyeyi girmediğimizde otamatik 00 alır. default olarak da a.m alır.
``` sql
select('03:44'::Time); 
select('03:44 PM'::time);
select('03:44:12 AM'::time);
```

- zaman dilimine göre (utc) gösterir
``` sql
select('02:25'::time with time zone);  
```
- tarih ve saati kullanacakken timestamp kullanılır.
```sql
select('1980 December 03 03:13:07':: timestamp);  
```
- Daha fazlası için

[PostgreSQL 13 Veri Tipleri](https://www.postgresql.org/docs/13/datatype.html)

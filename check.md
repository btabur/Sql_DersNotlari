# check kullanımı
``` sql
insert into users(username, email, age)
values ('gamer', 'gamer@gmail.com',-22);

select * from users;
```
- girilen bazı verilerin değerlerini kontrol etmek isteyebiliriz. yukarıda ki gibi yaşın negetif girilmemesini veya belli aralıkta olmasını isteyebiliriz. bu durum da check kelimesini kullanırız.
``` sql
alter table users
add check (age>18);
```
- biraz önce bu şartı sağlamayan veri girildiği için hata verir. hata veren veriyi silmemiz veya değiştirmemiz lazım
``` sql
delete from users 
where age = -22;
select * from users;
```
- şimdi istediğimiz değişikliği yapabiliriz.
``` sql
alter table users
add check (age>18);
```
- yaş için girilen şartı sağlamadığı için hata verir.
``` sql
insert into users(username, email, age)
values ('gamer2', 'gamer2@gmail.com',5);
```
- yeni bir tablo oluştururken.
- ürünü fiyatı ve indirimli fiyatı sıfırdan büyük olmak zorunda bununla beraber en altta yeni bir check tanımlayıp indirimli fiyatında normal fiyattan küçük olması kontrol edilmiş durumda
``` sql
create table products(
	product_no integer,
	name text,
	price numeric check (price>0),
	discounted_price numeric check (discounted_price >0),
	check (price> discounted_price)
);
``` 
- indirimli fiyat normal fiyattan yüksek olduğu için hata verir.
``` sql
insert into products( product_no, name, price, discounted_price)
values(1,'tester', 10, 12);
```
``` sql
insert into products( product_no, name, price, discounted_price)
values(1,'tester', 10, 8);
select * from products;
```
daha fazlası için 
-[W3Schools CHECK](https://www.w3schools.com/sql/sql_check.asp)
- [PostgreSQL Tutorial CHECK](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-check-constraint/)

11.05.23



# Unique
``` sql
insert into users (username, email, age)
values ('tester', 'tester@gmail.com',440);

select * from users;
```
- girililen verilerin eşsiz olmmasını istiyorsak unique anahtar kelimesi ile kısıtlama getiririz.
- bu kısıtlamayı iki şekilde yapabiliriz 
1. tabloyu ilk oluştururken
``` sql
create table users(
    id serial primary key,
	username varchar(20) not null,
	email varchar(50) unique,
	age integer
);
```
 2. tablo oluşturulmuş sonradan değiştirmek isteniyor ise alter kelimesi kullanılır.
``` sql
alter table users
add unique (email);
```
- email sütununda benzer veriler olduğu için hata verir.
- öncelikle benzer terimleri değiştirmemiz veya silmemiz lazım.
``` sql
update users
set email ='test2@gmail.com'
where email ='tester@gmail.com';

select * from users;
```
- benzer verileri değiştirdiğimiz için istediğimiz değişikliği yapabiliriz.
``` sql
alter table users
add unique (email);
```
- Şimdi veri tabanında bulunan bir mail girdiğimizde sistem uyarı verecek.
``` sql
insert into users (username, email, age)
values ('tester', 'tester@gmail.com',440);
```

daha fazlası için 
- [W3Schools UNIQUE](https://www.w3schools.com/sql/sql_unique.asp)
- [PostgreSQL Tutorial UNIQUE](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-unique-constraint/)

11.04.2003





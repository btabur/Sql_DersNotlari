# NOT NULL
- CONSAİNT verilere rastgele veri girilmesini istemeyiz. bunun için çeşitli kısıtlamalar yaparız.
``` sql
create table users(
id serial primary key,
	username varchar(20),
	email varchar(50),
	age integer
);

select * from users;

insert into users(username, email, age)
values 
('tester', 'test123@gmail.com', 23);

insert into users(email, age)
values 
( 'test1234@gmail.com', 25);
select * from users;
```
- bir tablo oluşturulmuş ve daha sonra içerisindeki verilere kısıtlama getirilmek isteniyor ise kullanılır. bu aşamada yukarıda null değer girildiği için hata verecek. Bu null değerlere ya ortalama bir değer atamalıyız veya silmeliyiz.
``` sql
alter table users
alter column username
set not null;
```
- burada null değerler alan verileri sileceğiz.
- null olup olmadığını kontrol etmek için is kelimesi kullanılır.
``` sql
delete from users
where username is null returning * ;
```
- null değer kalmadığı için başarılı bir şekilde değişecektir. artık username değişkeni null değer alamaz.
``` sql
alter table users
alter column username
set not null;
select * from users;
```
- username null olamayacağı için hata verir.
``` sql
insert into users (email, age)
values (
'test45@gmail.com',45
);
```
- null değer ile boş değer farklı şeylerdir. buradaki gibi username boş değer alabilir. 
``` sql
insert into users (username, email, age)
values (
'','test45@gmail.com',45
);
select * from users;
```
daha fazlası için
- [W3Schools NOT NULL](https://www.w3schools.com/sql/sql_notnull.asp)

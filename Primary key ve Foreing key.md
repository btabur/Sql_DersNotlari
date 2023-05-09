# Primary Key ve Foreing Key

- PRIMARY KEY  (birincil anahtar): satırda bulunan bir veriyi diğer verilerden ayırmaktadır. benzersiz bir tanımlayıcı oluşturur.
- FOREING KEY : genelde başka bir tablodaki satıra referans verir. Tablolar arasında ilişki kurmamıza yardımcı olur.

``` sql
create table book (
	id serial primary key,
	title varchar(100) not null,
	pagenumber integer not null,
	author_id integer references autor (id)  -- autor tablosundaki id ile ilişki kurar
);
```
--Yeni veri eklerken autor tablosu ile ilişkili yaptığımız için autor_id değerinin autor tablosunda bulunan bir id ye eşit olması gerekir.

``` sql
insert into book (title, pagenumber, author_id) values ('As I Was Moving Ahead Occasionally I Saw Brief Glimpses of Beauty', 59, 54);
insert into book (title, pagenumber, author_id) values ('What a Way to Go!', 28, 37);
insert into book (title, pagenumber, author_id) values ('Time to Kill (Tempo di uccidere)', 51, 45);
insert into book (title, pagenumber, author_id) values ('Jails, Hospitals & Hip-Hop', 37, 56);
insert into book (title, pagenumber, author_id) values ('Six Degrees of Separation', 89, 44);
insert into book (title, pagenumber, author_id) values ('Earthquake', 96, 13);
insert into book (title, pagenumber, author_id) values ('Vollidiot', 61, 34);
insert into book (title, pagenumber, author_id) values ('My Joy (Schastye moe)', 97, 22);
insert into book (title, pagenumber, author_id) values ('Vampyros Lesbos (Vampiras, Las)', 19, 66);
insert into book (title, pagenumber, author_id) values ('Feast II: Sloppy Seconds', 3, 73);
insert into book (title, pagenumber, author_id) values ('Fun', 94, 52);
insert into book (title, pagenumber, author_id) values ('Streamers', 22, 32);
insert into book (title, pagenumber, author_id) values ('Mercredi, folle journée!', 26, 13);
insert into book (title, pagenumber, author_id) values ('Second Man, The (O Defteros Andras)', 54, 59);
insert into book (title, pagenumber, author_id) values ('Barefoot Gen 2 (Hadashi no Gen II)', 31, 72);
insert into book (title, pagenumber, author_id) values ('Solarbabies', 15, 33);
insert into book (title, pagenumber, author_id) values ('Return of the Living Dead Part II', 75, 6);
insert into book (title, pagenumber, author_id) values ('Mission, The (Cheung fo)', 39, 34);
insert into book (title, pagenumber, author_id) values ('Great Texas Dynamite Chase, The', 43, 27);
insert into book (title, pagenumber, author_id) values ('Whistle Down the Wind', 50, 7);
```
- book tablosu üzerinden author_id referansı ile iki tabloyu birleştirerek getirir.
``` sql
select * from book
join autor on autor.id=book.author_id;
```
daha dazlası için 
- [W3Schools PRIMARY KEY](https://www.w3schools.com/sql/sql_primarykey.asp)
- [W3Schools FOREIGN KEY](https://www.w3schools.com/sql/sql_foreignkey.asp)
- [PostgreSQL Tutorial PRIMARY KEY](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-primary-key/)


Database Project for **Biblioteca**

The scope of this project is to use all the SQL knowledge gained throught the Software Testing course and apply them in practice.

Application under test: **Biblioteca**

Tools used: MySQL Workbench

Database description: Creare baze de date si legatura intre tabele , pentru o biblioteca.

Database Schema 

You can find below the database schema that was generated through Reverse Engineer and which contains all the tables and the relationships between them.

The tables are connected in the following way:

**autor** is connected with **carte** through a **1:n** relationship which was implemented through **autor.id** as a primary key and **carte.id_autor** as a foreign key 

**editura**  is connected with **carte**  through a **1;n** relationship which was implemented through **editura.id** as a primary key and **carte.id_editura** as a foreign key

**cititor**  is connected with **fisa_lectura** through a **1:n** relationship which was implemented through **cititor.id** as a primary key and **fisa_lectura.id_cititor** as a foreign key

**carte**  is connected with **fisa_lectura** through a **1:n** relationship which was implemented through **carte.id** as a primary key and **fisa_lectura.id_carte** as a foreign key


Database Queries

DDL (Data Definition Language)

  The following instructions were written in the scope of CREATING the structure of the database (CREATE INSTRUCTIONS)

  **create table autor (
	id int primary key AUTO_INCREMENT,
	nume varchar(50),
	prenume varchar(100),
    locul_nasterii varchar(100),
    data_nasterii datetime
);**


**create table editura (
	id int primary key AUTO_INCREMENT,
	nume varchar(100),
	telefon varchar(15),
	adresa varchar(200)
);**

**create table carte (
	id int primary key AUTO_INCREMENT,
	id_autor int,
	id_editura int,
	denumire varchar(100) not null,	
	nr_exemplare int not null,	
	an_aparitie datetime,
	pret decimal(12,2) not null,
	FOREIGN KEY (id_autor) REFERENCES autor(id),
	FOREIGN KEY (id_editura) REFERENCES editura(id)
);**
 
**create table cititor (
	id int primary key AUTO_INCREMENT,
	nume varchar(50),
	prenume varchar(100),
	telefon varchar(15),
	adresa varchar(200)
);**
	
	
**create table fisa_lectura (
	id int primary key AUTO_INCREMENT,
	id_carte int,
	id_cititor int,
	data_imprumut datetime not null,
	data_returnare datetime,
	FOREIGN KEY (id_carte) REFERENCES carte(id),
	FOREIGN KEY (id_cititor) REFERENCES cititor(id)
);**

**

  After the database and the tables have been created, a few ALTER instructions were written in order to update the structure of the database, as described below:

 - -- modific tipul unei coloane
**alter table autor 
modify column nume varchar (60);**

-- sterg coloana nume
alter table autor
drop column nume;**

-- adaug coloana nume
alter table autor add column nume varchar (50) not null;


  DML (Data Manipulation Language)

  In order to be able to use the database I populated the tables with various data necessary in order to perform queries and manipulate the data. 
  In the testing process, this necessary data is identified in the Test Design phase and created in the Test Implementation phase. 

  Below you can find all the insert instructions that were created in the scope of this project:

-- autor
INSERT INTO autor (nume,prenume,locul_nasterii,data_nasterii) VALUES ('Eminescu','Mihai', 'Botosani', '1850-01-15');
INSERT INTO autor (nume,prenume,locul_nasterii,data_nasterii) VALUES ('Creanga','Ion', 'Iasi', '1889-12-31');
INSERT INTO autor (nume,prenume,locul_nasterii,data_nasterii) VALUES ('Sadoveanu','Mihail', 'Bucuresti',  '1961-10-19');
INSERT INTO autor ( prenume, locul_nasterii, data_nasterii, nume) values ( 'Mircea', 'Bucuresti', '1956-06-01', 'Cartarescu');

-- editura
INSERT INTO editura (nume,telefon,adresa) VALUES ('NEMIRA','0721747464','Str. Iani Buzoiani, nr. 14, sector 1, Bucuresti, România');
INSERT INTO editura (nume,telefon,adresa) VALUES ('Editura Gramar','0770104175','Bucuresti, Strada Ion Baiulescu, nr. 75');
INSERT INTO editura (nume, telefon, adresa) VALUES ('Editura Carturesti','0213125450', 'Bucuresti Strada Barbu Vacarescu, nr. 22');
INSERT into editura ( nume, telefon, adresa ) values ( 'Litera', '0215230456', 'str. Principala nr.25');


-- cititor
INSERT INTO cititor (nume,prenume,telefon,adresa) VALUES ('Vasile','Ion','0721111111','Bd. Constantin Brancoveanu nr 12');
INSERT INTO cititor (nume,prenume,telefon,adresa) VALUES ('Teodor','Critian','0721222222','Bd. Constantin Brancoveanu nr 13');
INSERT INTO cititor (nume, prenume, telefon, adresa) VALUES ('Laura',' Dima', '0752212034', ' Str, Frumoasa nr 15 ');
INSERT INTO cititor ( nume, prenume, telefon, adresa) values ( 'Visan', 'Alina', '0215230789', 'str. Lalelelor nr.7');

-- carte
INSERT INTO carte 
(id_autor,id_editura,denumire    ,nr_exemplare,an_aparitie ,pret) VALUES
(1       ,1         ,'Luceafarul',5           ,'1883-04-01',100 );

INSERT INTO carte 
(id_autor,id_editura,denumire                      ,nr_exemplare,an_aparitie ,pret) VALUES
(1       ,1         ,'La mormântul lui Aron Pumnul',10          ,'1886-01-01',50 );

INSERT INTO carte 
(id_autor,id_editura,denumire                ,nr_exemplare,an_aparitie ,pret) VALUES
(2       ,2         ,'Amintiri din copilarie',4           ,'1892-01-01',150 );

INSERT INTO carte 
(id_autor,id_editura,denumire                ,nr_exemplare,an_aparitie ,pret) VALUES
(3       ,2         ,'Baltagul',14           ,'1930-11-01',200 );

-- fisa_lectura 
INSERT INTO fisa_lectura 
(id_carte,id_cititor,data_imprumut,data_returnare) VALUES
(1       ,1         ,'2024-01-01' ,null  );

INSERT INTO fisa_lectura 
(id_carte,id_cititor,data_imprumut,data_returnare) VALUES
(4       ,2         ,'2024-06-01' ,'2024-07-01'  );

 
 After the insert, in order to prepare the data to be better suited for the testing process, I updated some data in the following way:


-- modific nume, prenume in tabela cititor
select * from cititor;
update cititor set nume ='Ioana', prenume='Nicoleta' where id='3';
-- modific locul nasterii in tabela autori
select * from autori;
update autor set locul_nasterii='Iasi' where id='7';
-- modific  telefon in tabela editura 
select * from editura;
update editura set telefon='021789123' where id='4'


DQL (Data Query Language)

After the testing process, I deleted the data that was no longer relevant in order to preserve the database clean: 

select * from autor;
delete from autor where id = 4; 


In order to simulate various scenarios that might happen in real life I created the following queries that would cover multiple potential real-life situations:


select * from autor;

select autor.id, autor.nume, autor.prenume, carte.denumire  
from autor 
inner join carte on autor.id=carte.id_autor
where nume= "Eminescu" and prenume= "Mihai" 
order by carte.denumire;

select * from carte;
select * from cititor;
select * from editura;
select * from fisa_lectura;


SELECT  nume, prenume from autor where locul_nasterii ("Bucuresti");

-- selectam primele intrari
select*from autor limit 2;

-- ignora 1 rand si afiseaza urmatoarele 2
select*from autor limit 2 offset 1; 

-- aranjare ordine descrescatoare  
select*from  autor
order by id desc
limit 2 offset 1;

select * from carte;

select a.id, e.id, a.nume as autor_nume, a.prenume as autor_prenume, c.denumire as denumire_carte, e.nume as editura_nume
from autor a
inner join carte c on c.id_autor = a.id
inner join editura e on a.id = c.id_editura;

select id, id_autor,id_editura, denumire, nr_exemplare from carte where nr_exemplare >5;

select a.id, e.id, a.nume as autor_nume, a.prenume as autor_prenume, c.denumire as denumire_carte, e.nume as editura_nume
from autor a
left join carte c on c.id_autor = a.id
left join editura e on a.id = c.id_editura;


select sum(nr_exemplare) as total_exemplare from carte where id_autor= (select id from autor where nume= 'Eminescu');

select a.id, a.nume, a.prenume,  sum(c.nr_exemplare) as total_exemplare
from carte c
inner join autor a on a.id = c.id_autor
group by a.id, a.nume, a.prenume
order by a.nume, a.prenume;

select sum(nr_exemplare) from carte;


Conclusions

Like a conclusion, in this project, i apply all the Sql database instructions for create a database, modify and delete information from database, create tabel, modify tabel with the instructions of database querys .

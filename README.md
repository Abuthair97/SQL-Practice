# SQL-Practice

DAY_1-PRACTICE

create database virat;

use virat;

CREATE TABLE batches(
batch_id INT PRIMARY KEY,
batch_name VARCHAR(50) NOT NULL
);

drop table Students;
CREATE TABLE students(
student_id INT AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
second_name VARCHAR(50) NOT NULL,
batch_id INT,
FOREIGN KEY (batch_id) REFERENCES batches (batch_id) on Delete Cascade
);

INSERT INTO batches(batch_id,batch_name)VALUES(1,"BATCH A"),(2,"BATCH B"),(3,"BATCH C");
select * from batches;

INSERT INTO students(first_name,second_name,batch_id) values('Abu','Sheik',1),('kira','Hema',2);



delete from batches where batch_id = 2 ;
select * from students;

drop table students;
CREATE TABLE students(
student_id INT AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
second_name VARCHAR(50) NOT NULL,
batch_id INT,
FOREIGN KEY (batch_id) REFERENCES batches (batch_id) on DELETE SET NULL 
);

Insert into students(first_name,second_name,batch_id)values('Abu','Sheik',1),('Kira','Hema',2);
select * from students;
Delete from batches Where batch_id = 2 ;

ALTER TABLE students 
add age INT;

update students set age = 21 where student_id =1 ;
update students set age = 23 where student_id = 2;

select * from students;

ALTER TABLE students
RENAME COLUMN age to age_number;

select * from students;


DAY_2-PRACTICE

 CRUD 1

 
use sakila;
INSERT INTO film (title, description, release_year, language_id, rental_duration,
rental_rate, length, replacement_cost, rating, special_features)
VALUES ('The Dark Knight', 'Batman fights the Joker', 2008, 1, 3, 4.99, 152, 19.99, 'PG-13',
'Trailers'),
('The Dark Knight Rises', 'Batman fights Bane', 2012, 1, 3, 4.99, 165, 19.99, 'PG-13',
'Trailers'),
('The Dark Knight Returns', 'Batman fights Superman', 2016, 1, 3, 4.99, 152, 19.99, 'PG-13',
'Trailers');

Insert into film(title, description, release_year, language_id, rental_duration,
rental_rate, length, replacement_cost, rating, special_features)
Values('Scaler Stories', 'SQL batch is rocking', 2023, 2, 7, 4.5, 90, 10.5, 'PG-13',
'Trailers');

Without specifying column name


INSERT INTO film
VALUES (default, 'The Dark Knight', 'Batman fights the Joker', 2008, 1, NULL,
3, 4.99, 152, 19.99, 'PG-13', 'Trailers', default);

 
 reading/printing data using select
select 'Hello world' as output;
select 1 as Rahul;
select *
from film;
select title as film_name
from film;
select film_id, title as film_name, release_year
from film;
select 'Rahul' as output
from film;
select rating
from film;

 distinct: To print only unique non null values

select distinct rating
from film;
select release_year, rating
from film;

-- Distinct can be used on a set of columns as well

select distinct release_year, rating
from film;

-- select distinct
-- from film;

select release_year
from film;
select 'Rahul'
from film;

 Find number of times a person can watch a movie during given rental duration
 
select title, round(rental_duration/round(length/60)) as no_of_times, rental_duration,
round(length/60)
from film;

-- Updating data in a new table using existing one
use school;

create table students_copy(
student_id INT AUTO_INCREMENT PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL);
SELECT first_name, last_name
from students;


select * from students_copy;
INSERT INTO students_copy(first_name, last_name)
SELECT first_name, last_name
from students;


use sakila;


select distinct release_year
from film;

-- where clause


select title, release_year, rating
from film
where release_year = 2006;


select distinct rating
from film
where release_year = 2023;

select *
from film
where release_year > 2006;


select *
from film;

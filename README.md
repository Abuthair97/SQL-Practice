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

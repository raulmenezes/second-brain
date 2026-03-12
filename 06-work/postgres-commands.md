---
tags:
  - area/databases
  - area/knowledge
  - topic/database
  - topic/docker
  - topic/snippets
---

# Postgres commands

Start up:
docker run --name pg-docker -e POSTGRES_PASSWORD=root -d -p 5432:5432 postgres

Connect:
-U: database user name
-d: database

psql -h localhost -U postgres -d postgres

**List of Databases:** \l

**Create Database:** CREATE DATABASE testdatabase;

Connect to new database: \c testdatabase

Create table:
Create table table_name (column_name data_type)

Create TABLE person ( id INT, first_name VARCHAR(50), last_name VARCHAR(50), gender VARCHAR(6), date_of_birth DATE);

Display tables:
\d

\dt

\dn

\d person

Creating Tables with Constraints

Create TABLE person ( 
id BIGSERIAL NOT NULL PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
gender VARCHAR(6) NOT NULL,
date_of_birth DATE NOT NULL email VARCHAR(140) );

Insert records into table

INSERT INTO person (
first_name, last_name, gender, date_of_birth)
VALUES ('Raul', 'Smith', 'MALE', DATE '1992-01-15');

INSERT INTO person (
first_name,
last_name,
gender,
date_of_birth,
Email)
VALUES (‘Jess’, ‘Chan’, ‘FEMALE’, DATE '1998-07-07’);

Inject SQL file:

\i [path_file_sql]

\i /Users/raulmenezes/Downloads/person.sql 

 select first_name, last_name from person;

Select From:
select * from person; 

select first_name, last_name from person; 

Order By

SELECT * FROM person ORDER by country_of_birth (DESC)

SELECT * FROM person ORDER by country_of_birth DESC

select country_of_birth from person order by country_of_birth;

Distinct
select country_of_birth from person order by country_of_birth;

select distinct country_of_birth from person order by country_of_birth;

select * from person where gender = 'Male' AND country_of_birth = 'Poland';

LIMIT OFFSET
select * from person where gender = 'Male' AND (country_of_birth = 'Poland' OR country_of_birth = 'China') LIMIT 10;

select * from person where gender = 'Male' AND (country_of_birth = 'Poland' OR country_of_birth = 'China') OFFSET 10 LIMIT 10;

IN
select * from person where country_of_birth IN ('China', 'Brazil')

## Related
- [[databases-moc]]
- [[check-storage-in-postgresql]]
- [[start-mongo]]
- [[mean-stack]]

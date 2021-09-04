## HOW TO START POSTGRESQL SERVER IN WSL :

# Installation :

> sudo apt update
> sudo apt install postgresql postgresql-contrib
> psql --version

# Server start :

> sudo service postgresql status
> sudo service postgresql start //!important
> sudo service postgresql stop

# To run PostgreSQL with psql shell:

> sudo -u postgres psql

## PostgreSQL Commands :
# ----------------To exit the shell --------------------------------

\q
To create new user

CREATE USER Aditi Agg  WITH PASSWORD '123456';
To create new database

CREATE DATABASE devsnest;
grant access of database to other user

GRANT ALL PRIVIlEGES ON DATABASE devsnest to Aditi;
grant specific access of db to other user

OPERATION = {UPDATE,SELECT,INSERT,DELETE}

GRANT <OPERATION> PRIVILEGES ON DATABASE <devsnest> to <Aditi>;
Delete database

DROP DATABASE <devsnest>;
connect to database

\c <devsnest>
create table

CREATE TABLE <stud>(
roll_no INT NOT NULL,
name CHAR[50] NOT NULL,
address TEXT
);
display the list of tables (relations)

\d
display fields info of specific table

\d <stud>
delete table

DROP TABLE IF EXISTS <stud>;
Visualization :
Database (Drive)
Tables (Files)
Schemas (Folders)
Tables (Files)

> creating schema
create schema myschema;
creating table inside schema

create table myschema.company(
   ID   INT              NOT NULL,
   NAME VARCHAR (20)     NOT NULL,
   AGE  INT              NOT NULL,
   ADDRESS  CHAR (25),
   SALARY   DECIMAL (18, 2),
   PRIMARY KEY (ID)
);
delete the schema + all tables inside it

DROP SCHEMA myschema CASCADE;
Insert values in table

INSERT INTO DEPARTMENT (ID,DEPT,EMP_ID)
VALUES (1,'CSE',87),(2,'IT',21),(3,'EN',60);

## Primary keys & Foreign keys :

CREATE TABLE customers(
   customer_id INT GENERATED ALWAYS AS IDENTITY,
   customer_name VARCHAR(255) NOT NULL,
   PRIMARY KEY(customer_id)
);

CREATE TABLE contacts(
   contact_id INT GENERATED ALWAYS AS IDENTITY,
   customer_id INT,
   contact_name VARCHAR(255) NOT NULL,
   phone VARCHAR(15),
   email VARCHAR(100),
   PRIMARY KEY(contact_id),
   CONSTRAINT fk_customer
      FOREIGN KEY(customer_id)
	  REFERENCES customers(customer_id)
	  ON DELETE CASCADE                /*ON DELETE CASCADE also deletes the reference
                                        data present in the other table*/
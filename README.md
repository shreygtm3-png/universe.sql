Perfect. I've updated the README.md to include your specific filename and GitHub profile. This is ready to be copied directly into your repository.

Celestial Universe Database
A PostgreSQL relational database containing structured information about the cosmos, including galaxies, stars, planets, and moons. This project demonstrates relational database design, table relationships, and data integrity.

Project Overview
This database was developed to map the hierarchical relationship of celestial bodies. It utilizes PostgreSQL 12.22 and features:

One-to-Many Relationships: Galaxies containing stars, stars hosting planets, and planets with multiple moons.

Data Integrity: Strict use of PRIMARY KEY, FOREIGN KEY, UNIQUE, and NOT NULL constraints.

Schema Diversity: Implementation of various data types including NUMERIC, BOOLEAN, VARCHAR, and TEXT.

File Structure
universe.sql: The complete PostgreSQL database dump containing the schema (DDL) and the initial dataset (DML).

Installation & Setup
To replicate this database in your local environment, ensure you have PostgreSQL installed.

1. Clone the repository
Bash
git clone https://github.com/shreygtm3-png/universe-db.git
cd universe-db
2. Import the Database
Run the following command in your terminal to create and populate the universe database:

Bash
psql -U postgres < universe.sql
(Note: If you are using the freeCodeCamp environment, ensure the user is set to freecodecamp.)

3. Connect and Explore
Bash
psql --username=postgres --dbname=universe
Database Schema at a Glance
Table	Primary Key	Foreign Keys	Description
galaxy	galaxy_id	None	Stores galaxy names, ages, and descriptions.
star	star_id	galaxy_id	Maps stars to their respective galaxies.
planet	planet_id	star_id, planet_type_id	Details on orbital periods and life-habitability.
moon	moon_id	planet_id	Information on lunar radii and orbital cycles.
planet_type	planet_type_id	None	A lookup table for planetary classifications.
Sample Query
To find all planets that are considered "Terrestrial":

SQL
SELECT p.name, t.description 
FROM planet p 
JOIN planet_type t ON p.planet_type_id = t.planet_type_id 
WHERE t.name = 'Terrestrial';
Developed by: shreygtm3-png

Certification: freeCodeCamp Relational Database Course

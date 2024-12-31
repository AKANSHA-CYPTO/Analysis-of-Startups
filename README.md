Project 1 
Overview
This dataset, named TrendsInStartups_Explorin, contains information on various startups, including their valuation, stage of funding, year founded, sector, size, and location. The file also includes SQL queries designed to extract meaningful insights and trends.

File Contents
The document outlines the following SQL solutions:

Counting Startups:
SELECT COUNT(name) FROM TrendsInStartups_Explorin;
This query calculates the total number of startups in the dataset.

Total Valuation:
SELECT SUM(valuation) FROM TrendsInStartups_Explorin;
Aggregates the total valuation of all startups.

Maximum Amount Raised in Seed Stage:
SELECT MAX(amount_raised) FROM TrendsInStartups_Explorin WHERE stage = 'Seed';
Identifies the highest amount raised by any startup in the seed funding stage.

Earliest Founded Year:
SELECT MIN(founded_year) FROM TrendsInStartups_Explorin;
Finds the earliest year a startup in the dataset was founded.

Average Valuation by Sector:
SELECT DISTINCT(sector), AVG(valuation) FROM TrendsInStartups_Explorin GROUP BY sector;
Computes the average valuation for each distinct sector.

Largest Startup by Location:
SELECT DISTINCT(location), MAX(size) FROM TrendsInStartups_Explorin GROUP BY location;
Determines the largest startup size per location.

Locations with Large Average Startup Sizes:
SELECT location, AVG(size) AS average_size FROM TrendsInStartups_Explorin GROUP BY location HAVING average_size > 500;
Lists locations where the average size of startups exceeds 500.

Top 15 Startups by Valuation:
SELECT DISTINCT(name), SUM(valuation) AS value FROM TrendsInStartups_Explorin GROUP BY name ORDER BY value DESC LIMIT 15;
Identifies the top 15 startups by total valuation.

Startups with Multiple Stages:
SELECT name, COUNT(stage) FROM TrendsInStartups_Explorin GROUP BY name HAVING COUNT(stage) = 4;
Filters startups that have gone through exactly four funding stages.

Requirements
To interact with the data, you'll need:

A relational database management system (RDBMS) like MySQL, PostgreSQL, or SQLite.
Basic knowledge of SQL to execute the queries listed above.
Usage
Load the TrendsInStartups_Explorin table into your RDBMS.
Run the SQL queries provided to extract specific insights or trends.
Modify the queries as necessary to tailor them to additional analyses.
From: Akansha

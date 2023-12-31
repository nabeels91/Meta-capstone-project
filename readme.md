# Global Super Store Database Design

## About the Project

This project is about designing a database model for Global Super Store to arrange their data in a way more scalable, clean and useful for their business needs and to be able to some data analysis in order to achieve their business goals. this is the project of the 7th course Advanced Data Modeling of Meta Database Engineer Professional Certificate on Coursera.

# About the Data

Global Super Store(GSS) store data about the orders which have been made by customers. There's information is on a wide xlsx sheet and is a very basic way of storing information making it hard to benefit from their stored info. 

All those information is stored in ONLY ONE dataset. This makes the data difficult to monitor, analyze, and extract insights! Therefore we need a structured database to store all those information in a simple and easy-to-monitor format.

![css file](https://github.com/nabeels91/Meta-capstone-project/blob/main/xslx:CSV.png)


# Data Modeling

To make a well designed database, we start by planning it. A ERD (entity relationship Diagram) is what we will use to design this database.

The dataset contains the following entities:

Order
Customer
Product
Sales
Address
Shipping
Cost

There are there levels of modeling, 1- conceptual model which we have been given so i will ommit it. 2 - logical data model and finally a physical data model.

The logical and physical data model:
the physical data model is basically a logical data model with all the gaps filled. All relationships foreign key connections and normalisation standards (up to normal form 3) are applied here

My ERM was designed in MySql Models. The output is as below:
![erm](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.02.04.png)

Once this is complete and the relationships are correctly designed use the MySQl feature to forward engineer the ERD to a database with schema and tables made.
Once that is finished the result should look as follows:

![Forward engineering ](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.02.42.png)

the Script that was autogenerated by the MySQL forward engineer function was as follows:
![forward ENgineer](https://github.com/nabeels91/Meta-capstone-project/blob/main/forward%20Engineering%20Scsh.png)

# Dimensional Data Model for GSS

Dimensional Data Models is the most widely used model for analysis, as it optimizes the database for fast retrieval of the data and relance of the design.

Dimensional Data Model consists of dimensions, the categorical data which we're interested in and give us the context of the analysis, and facts, the collection of measurement and metrics that any business needs to analyze.

The most common schema that any dimensional data model can be built with is the Star Schema. It has the fact table at its center, and all the dimensions around it.

Here, the fact table is Sales, and the dimensions are divided into Location, Date, and Products

The implementation of the Star Schema on MySQL Workbench:

!(star schema)[https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.02.12.png]

# Analysis in tableau:
Once that is complete this section of the exercise has been complete and the next task is to upload the CSV file into table then analysing it and answering a few questions in relation to GSS's performance in the USA.

## The import should look like this: 
![import](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.11.16.png)

## The performance of each state in the US is present as follows:
![sales](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.24.34.png)

## A bubble chart representation of the profit per state as follows:
![profits](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.24.41.png)

## The yearly performance of the states with sales of more that 40'000 per year.
![over 40k](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.24.52.png)

## Finally a worksheet  with the 3 metrics all displayed and the filter is the state which should override all other filters except the country filter.
![worksheet](https://github.com/nabeels91/Meta-capstone-project/blob/main/Screenshot%202023-09-06%20at%2023.25.07.png)

this can be seen live in cation here: https://public.tableau.com/app/profile/nabeel4512/viz/Meta-Courseracourse7/Dashboard1


















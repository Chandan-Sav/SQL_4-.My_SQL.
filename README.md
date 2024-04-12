# Burger Dataset SQL_queries
## About

This project aims to explore the Burger data to understand customer and burger type, delievery person of different types, customer behaviour. The aims is to study how some of the queries were solved using SQL Queries. The dataset is [Burger_Dataset](https://www.kaggle.com/datasets/chandansav/burger-dataset).

These markdowns are known to affect some of the, but it is challenging to predict which KPI's are affected and the extent of the impact." [source](https://www.kaggle.com/datasets/chandansav/burger-dataset)

## Purposes Of The Project

The major aim of thie project is to do the  case study for data of Burger business to understand the different factors that affect customer.

## About Data

The dataset was obtained from the [Burger_Dataset](https://www.kaggle.com/datasets/chandansav/burger-dataset). This dataset contains all customer transactions from a four different tables of Burger business including Burger_name,Burger_runners,Burger_runners_order & Customer_orders respectively. The data contains 16 columns and which is divided in 4 Table's:

## Table 1 [Burger_name]
| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| burger_id            | ID Number's of Burger              | INTEGER    |
| burger_name                 | Name of a Burger        | VARCHAR(10)     |


## Table 2 [Burger_runners]
| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| runner_id            | ID no of Runners              | INTEGER    |
| registration_date                | Date of Registration       | DATE    |


## Table 3 [Burger_runners_order]
| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| order_id            | Order ID            | INTEGER    |
| runner_id                 | ID no of Runners         | INTEGER      |
| pickup_time            | Timestamp when order was placed           | Timestamp   |
| distance                 | Distance Travelled         | VARCHAR(7)     |
| duration            |Duration taken to complete order          | VARCHAR(10)    |
| cancellation                | If order get cancelled        | VARCHAR(23)      |


## Table 4 [Customer_orders]
| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| order_id            | Order ID            | INTEGER    |
| runner_id                 | ID no of Runners         | INTEGER      |
| burger_id           | ID Number's of Burger           | INTEGER    |
| exclusions                 | Items Excluded        | VARCHAR(4)     |
| extras           |Extra added Itens         | VARCHAR(4)    |
| order_time                | Timestamp when order was delievered       | Timestamp     |

## Case Study Queries to find

### Queries

1. How many burgers were ordered?
2. How many unique customer orders were made?
3. How many successful orders were delivered by each runner?
4. How many of each type of burger was delivered?
5. How many Vegetarian and Meatlovers were ordered by each customer?
6. What was the maximum number of burgers delivered in a single order?
7. For each customer, how many delivered burgers had at least 1 change and 
how many had no changes?
8. What was the total volume of burgers ordered for each hour of the day?
9. How many runners signed up for each 1 week period? 
10.What was the average distance travelled for each customer?


## Code

For the rest of the code, check the [SQL_queries.sql](https://github.com/Chandan-Sav/SQL_4-.My_SQL./blob/main/Burger_SQL_Query.sql) file

```sql
-- Create database
CREATE DATABASE IF NOT EXISTS burgerdb;

-- Create table

-- Table 1 [Burger_name]

CREATE TABLE burger_names(
   burger_id   INTEGER  NOT NULL PRIMARY KEY 
  ,burger_name VARCHAR(10) NOT NULL
);


-- Table 2 [Burger_runners]

CREATE TABLE burger_runner(
   runner_id   INTEGER  NOT NULL PRIMARY KEY 
  ,registration_date date NOT NULL
);


-- Table 3 [Burger_runners_order]

CREATE TABLE runner_orders(
   order_id     INTEGER  NOT NULL PRIMARY KEY 
  ,runner_id    INTEGER  NOT NULL
  ,pickup_time  timestamp
  ,distance     VARCHAR(7)
  ,duration     VARCHAR(10)
  ,cancellation VARCHAR(23)
);


-- Table 4 [Customer_orders]

CREATE TABLE customer_orders(
   order_id    INTEGER  NOT NULL 
  ,customer_id INTEGER  NOT NULL
  ,burger_id    INTEGER  NOT NULL
  ,exclusions  VARCHAR(4)
  ,extras      VARCHAR(4)
  ,order_time  timestamp NOT NULL
);





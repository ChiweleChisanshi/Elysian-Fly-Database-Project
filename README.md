# Elysian Fly Database Project

## Overview

This project was completed for MIS 3353: Database Management. My team designed a relational database for Elysian Fly, a fictional fly-fishing company that needed a better way to organize and analyze its business data.

The project included database planning, an Entity Relationship Diagram, normalization, logical design, physical design, SQL queries, documentation, and project reflection.

## Business Problem

Elysian Fly needed a structured database to manage information related to customers, vendors, fly products, sales orders, purchase orders, payments, deliveries, guided fishing trips, and inventory.

Without a well-designed database, the company could struggle with duplicate data, inconsistent records, poor reporting, and difficulty tracking business activity.

## Project Goal

The goal of this project was to design a database that could help Elysian Fly:

- Organize business data
- Improve decision-making
- Track sales and vendor activity
- Manage customer and product information
- Support business reporting
- Reduce data redundancy
- Improve data integrity

## My Role
As part of the Crimson & Cream team, I contributed to the database design and documentation process. I helped with requirements analysis, ERD planning, normalization, implementation review, SQL-based business analysis, and written documentation.

## What I Learned

This project helped me understand how database design supports business operations and decision-making. I learned how to move from business requirements to an ERD, then from an ERD to normalized relations, and finally to a physical database design.

I also learned the importance of accurate documentation, consistent naming, data integrity, and careful SQL testing.
## Tools and Concepts Used

- SQL
- Entity Relationship Diagrams
- Lucidchart
- Database normalization
- Third Normal Form
- Referential integrity
- Logical database design
- Physical database design
- Data dictionary
- Business analysis
- Team documentation

## Database Design Process

### 1. Conceptual Design

We started by identifying the main business areas that the database needed to support. These included customers, vendors, products, sales, purchases, payments, deliveries, employees, and guided fishing trips.

We also reviewed the business cycles involved in the company, including the revenue cycle, production cycle, and expenditure cycle.

### 2. Requirements Gathering

The team reviewed the case information and gathered additional details from a client meeting. This helped us understand what the company needed from the database.

Some important requirements included:

- Tracking customer orders
- Tracking product details such as fly size, color, and pattern
- Managing vendors and vendor accounts
- Tracking inventory and reorder points
- Recording payments
- Tracking employee and guide performance
- Supporting reports for sales and product performance

### 3. Entity Relationship Diagram

We created an ERD to show the main entities in the database and how they relate to each other.

Some of the major entities included:

- Customer
- Employee
- Vendor
- Fly
- SalesOrder
- SalesOrderLine
- PurchaseOrder
- PurchaseOrderLine
- PaymentIn
- PaymentOut
- DeliveryIn
- DeliveryOut
- GuideFishingTrip
- Discount
- ShippingType
- State
- Color
- Size
- Pattern

The ERD helped us plan the structure of the database before moving into the logical and physical design.

### 4. Normalization

We normalized the database to reduce duplicate data and improve data integrity. The database was designed using normalization principles up to Third Normal Form.

Normalization helped us:

- Avoid repeated data
- Create cleaner tables
- Improve accuracy
- Make the database easier to maintain
- Support more reliable reports

### 5. Logical Design

After creating the ERD, we converted the design into normalized relations. This included identifying primary keys, foreign keys, table attributes, and relationships between tables.

### 6. Physical Design

The physical design translated the logical database model into an implementable database structure. This included creating tables, setting relationships, defining constraints, and preparing the database for SQL queries.

## SQL Business Questions

We wrote SQL queries to answer business questions such as:

- What are total sales by customer state?
- What are total sales by vendor?
- Which fly patterns sell the most?
- Which fly sizes sell the most?
- Which products are least sold?
- Which products may need to be discontinued?
- What are total sales by sales channel?
- Which products have the highest margin?
- What are the most popular DIY fly-tying materials?
- How many products are managed by each vendor manager?

## Example SQL Query

```sql
SELECT 
    TS.StateName,
    SUM(TSO.Total) AS TotalSales
FROM TCustomer TC
JOIN TState TS 
    ON TC.StateID = TS.StateID
JOIN TSalesOrder TSO 
    ON TSO.CustID = TC.CustID
GROUP BY TS.StateName;

# E-Commerce Back End

## Table of Contents
- [Introduction](#introduction)
- [User Story](#user-story)
- [Acceptance Criteria](#acceptance-criteria)
- [Mock-Up](#mock-up)
- [Getting Started](#getting-started)
- [Database Models](#database-models)
- [Associations](#associations)
- [API Routes](#api-routes)
- [Seeding the Database](#seeding-the-database)
- [Video Walkthrough](#video-walkthrough)

## Introduction
Internet retail, or e-commerce, is a crucial sector within the electronics industry, facilitating the online buying and selling of electronic products. In 2021, the industry in the United States generated an estimated US$2.54 trillion. E-commerce platforms like Shopify and WooCommerce offer a range of services to businesses, making the understanding of e-commerce site architecture essential for developers. This project involves building the back end for an e-commerce site by modifying starter code and configuring an Express.js API to use Sequelize with a MySQL database.

## User Story
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies

## Acceptance Criteria
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database

## Mock-Up
The application demonstrates GET routes for all categories, products, and tags in Insomnia. It also shows GET routes for a single category, product, and tag, as well as POST, PUT, and DELETE routes for products, tags, and categories.
[Mock-Up](./Assets/13-orm-homework-demo-01.gif)

## Database Models
The database should contain the following models:
- **Category**
  - `id`: Integer, Primary Key, Auto Increment, Not Null
  - `category_name`: String, Not Null
- **Product**
  - `id`: Integer, Primary Key, Auto Increment, Not Null
  - `product_name`: String, Not Null
  - `price`: Decimal, Not Null, Validates Decimal
  - `stock`: Integer, Not Null, Default 10, Validates Numeric
  - `category_id`: Integer, References Category's id
- **Tag**
  - `id`: Integer, Primary Key, Auto Increment, Not Null
  - `tag_name`: String
- **ProductTag**
  - `id`: Integer, Primary Key, Auto Increment, Not Null
  - `product_id`: Integer, References Product's id
  - `tag_id`: Integer, References Tag's id

## Associations
- **Product** belongs to **Category**, and **Category** has many **Product** models.
- **Product** belongs to many **Tag** models, and **Tag** belongs to many **Product** models through **ProductTag**.

## API Routes
Completed routes in `product-routes.js`, `tag-routes.js`, and `category-routes.js` to enable CRUD operations.

## Seeding the Database
After creating the models and routes, run `npm run seed` to seed data to the database for route testing.

## Video Walkthrough
For a detailed walkthrough of the application, please view the video here: [Video Walkthrough](https://drive.google.com/file/d/1zar5RxZFizZtDuAvwfDQoVdScFaskE63/view)





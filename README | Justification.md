# BooksOnline

BooksOnline is a simple bookstore application built in Claris FileMaker as part of the Software Engineer V assignment.

## Features

### Products
The application supports three product types:

- Physical
- Digital
- Voucher

Each product contains:
- Name
- Product Type
- Unit Price
- Available Stock Quantity

### Customers

Customer records include:

- First Name
- Last Name
- Email Address

### Orders

Orders can be created and managed through the application.

Each order contains:

- Customer
- Status
- Order Items

Supported order statuses:

- Draft
- Completed

### Order Items

Each order item contains:

- Product
- Quantity
- Current Unit Price

The current unit price is copied from the product when the item is added to the order, ensuring historical order values remain unchanged if product prices are modified later.

## Business Rule

A stock validation rule is implemented.

When an order is completed, the application verifies that sufficient stock is available for all ordered items. Orders that exceed available stock cannot be completed.

## Admin View

The application provides a simple administrative interface for:

- Managing products
- Managing customers
- Managing orders

## Technology

- Claris FileMaker Pro
- FileMaker scripting
- Relational data model
- UUID-based primary keys

## Data Model

The solution consists of the following core entities:

- Products
- Customers
- Orders
- OrderItems

Relationships are used to connect customers to orders and products to order items.

## Repository Contents

- BooksOnline.fmp12 – FileMaker application
- README.md – Project overview
- Architecture_Overview.pdf – Scaling and architecture concept

## Author

Mariusz
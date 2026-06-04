# BooksOnline

BooksOnline is a simple bookstore app.

# Design Justification

The solution was designed with simplicity, clarity, and maintainability in mind. The data model follows a standard relational structure consisting of Products, Customers, Orders, and OrderItems. This separation keeps the model easy to understand while supporting future growth and changes to business rules.

Products support three types: Physical, Digital, and Voucher, as required by the assignment. Orders are linked to customers and contain one or more order items. To preserve historical accuracy, the product price is copied to the order item when the product is added to an order. This ensures that changes to product pricing do not affect previously created orders.

A stock validation rule was implemented as the primary business rule. Before an order can be completed, the application verifies that sufficient stock is available. This demonstrates how business rules can be enforced through FileMaker scripts and calculations while remaining easy to modify.

The user interface was intentionally kept minimal, focusing on functionality rather than presentation. A simple administrative area allows management of products, customers, and orders. UUIDs are used as primary keys throughout the solution to ensure reliable record identification and relationships.

## Author

Mariusz

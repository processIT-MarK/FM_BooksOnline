# Architecture Overview

## Solution Architecture

The application was designed as a simple FileMaker solution focused on clarity, maintainability, and adaptability. The data model is built around four core entities: Products, Customers, Orders, and OrderItems.

The current implementation focuses on the main business process of creating and managing orders while keeping the user interface intentionally simple. This makes the solution easy to understand, maintain, and extend as business requirements evolve.

In a production environment, the solution would be hosted on FileMaker Server, allowing multiple users to work with the system simultaneously. External systems such as a webshop, ERP, or reporting platform could integrate through the FileMaker Data API, allowing FileMaker to remain the central system managing products, customers, and orders.

## Scalability

The solution separates master data (Products and Customers) from transactional data (Orders and OrderItems), creating a structure that can grow without requiring significant changes to the underlying data model.

As new requirements arise, additional business rules, reporting capabilities, and integrations can be added while keeping the existing order process intact. The same architecture could support multiple users and external data sources while maintaining a clear separation between business data and transactional records.

## Potential Bottleneck

The most likely bottleneck is stock handling during order completion.

In a larger multi-user environment, multiple users could attempt to complete orders containing the same product at the same time. This may lead to record locking or stock conflicts if several users are updating the same product simultaneously.

For simplicity, stock is currently stored directly on the product record. In a larger solution, I would introduce an inventory movement model where every stock change is recorded as a separate transaction. This would provide a complete audit trail, improve traceability, and reduce the risk of conflicts when multiple users work with the same products.
# Database Design and Implementation

This project demonstrates the design, implementation, and testing of a relational banking database using Microsoft SQL Server. It covers the full database lifecycle: conceptual modeling, physical schema creation, business logic implementation, and structured testing.

The system supports customer management, account handling, financial transactions, auditing, and reporting while enforcing strong data integrity and business rules.

## Technologies Used

- Microsoft SQL Server
- T-SQL (DDL, DML, Stored Procedures, Triggers)
- ERD / UML Modeling
- SQL Testing Scripts

## Database Design

Designed a normalized relational schema using ERD and UML.

Core entities:
- Customer
- Account
- Transaction
- TransactionAccount
- TransactionComment
- CustomerAddressLog (audit table)

Relationships enforced with primary keys and foreign keys. The physical design ensures scalability, integrity, and clarity.

## Schema & Data Integrity

Implemented constraints to enforce business rules:

- PRIMARY KEY, FOREIGN KEY
- UNIQUE constraints for customer identity
- CHECK constraints for:
  - Valid customer, account, and transaction types
  - Non-negative balances
  - Valid dates
- IDENTITY columns for surrogate keys

## Business Logic Implementation

Business logic is encapsulated using stored procedures and triggers to ensure consistency and reusability.

### Key Stored Procedures & Features

Customer Management
- Create customers with validation and duplicate checks
- Update customer address with audit tracking

Account Management
- Create accounts linked to customers
- Validate ownership and account status

Transaction Processing
- Deposits, withdrawals, and transfers
- Ownership and balance validation
- Multi-account handling for transfers

Reporting & Utilities
- Count customers by city
- Calculate total balance per customer

## Triggers & Automation

- Balance Enforcement Trigger: prevents negative account balances and rolls back invalid operations
- Audit Trigger: logs address changes into CustomerAddressLog
- Balance Update Trigger: updates account balances when transactions occur and handles TO/FROM logic for transfers

## Transactions & Error Handling

Robust transaction control is used to ensure atomic operations:
- BEGIN TRANSACTION, COMMIT, ROLLBACK
- Error handling with TRY...CATCH and RAISERROR
- Custom validation messages to ensure atomicity and consistency during failures

## Testing Strategy

Comprehensive SQL test scripts are included. Tests cover:
- Valid (positive) scenarios
- Invalid (negative) scenarios
- Edge cases (duplicates, overdrafts, invalid accounts)

Validation queries verify the correct data state after each test, mimicking real-world database QA practices.

## Key Skills Demonstrated

- Relational database modeling (ERD/UML)
- Advanced T-SQL programming
- Stored procedures and triggers
- Transaction management and error handling
- Data integrity and auditing
- SQL-based testing and validation
- Reporting with joins and aggregations


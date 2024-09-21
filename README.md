# Expense Tracker Database Schema

This project provides a database schema for an Expense Tracker application. The schema is designed to store user profiles, expenses, categories, payment methods, and budgets. It is implemented using SQL and can be used with an Object-Relational Mapping (ORM) library in Node.js.

## Database Schema Overview

The database consists of the following tables:
- **Users**: Stores user information.
- **Expenses**: Stores expense data for each user.
- **Categories**: Defines custom categories for organizing expenses.
- **Payment Methods**: Stores available payment methods for each user.
- **Budgets**: Allows users to set spending limits by category and date range.

### Tables

1. **Users Table**
    - `user_id`: Primary Key
    - `username`: Unique username
    - `email`: User's email address (unique)
    - `password`: Hashed password
    - `created_at`: Timestamp when the record was created
    - `updated_at`: Timestamp when the record was last updated

2. **Expenses Table**
    - `expense_id`: Primary Key
    - `user_id`: Foreign Key referencing `Users`
    - `category_id`: Foreign Key referencing `Categories`
    - `amount`: Expense amount
    - `date`: Date of the expense
    - `description`: Expense description
    - `created_at`: Timestamp when the record was created
    - `updated_at`: Timestamp when the record was last updated

3. **Categories Table**
    - `category_id`: Primary Key
    - `user_id`: Foreign Key referencing `Users`
    - `category_name`: Name of the category
    - `created_at`: Timestamp when the record was created
    - `updated_at`: Timestamp when the record was last updated

4. **Payment Methods Table**
    - `payment_method_id`: Primary Key
    - `user_id`: Foreign Key referencing `Users`
    - `payment_method_name`: Name of the payment method
    - `created_at`: Timestamp when the record was created
    - `updated_at`: Timestamp when the record was last updated

5. **Budgets Table**
    - `budget_id`: Primary Key
    - `user_id`: Foreign Key referencing `Users`
    - `category_id`: Foreign Key referencing `Categories`
    - `amount`: Budget amount
    - `start_date`: Budget start date
    - `end_date`: Budget end date
    - `created_at`: Timestamp when the record was created
    - `updated_at`: Timestamp when the record was last updated

## Setup Instructions

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/expense-tracker.git
    ```
2. Navigate to the project directory:
    ```bash
    cd expense-tracker
    ```
3. Import the SQL schema into your database:
    ```bash
    psql -U your_user_name -d your_database_name -f expense_tracker_schema.sql
    ```
4. Install Node.js dependencies and configure ORM (e.g., Sequelize) to interact with the database.

## Usage

This project can be used as the database backbone for an Expense Tracker application, providing CRUD (Create, Read, Update, Delete) operations for user data, expenses, categories, payment methods, and budgets.

## Technologies

- **SQL**: Used for designing the database schema.
- **Node.js**: Backend environment for the application.
- **ORM**: Object-Relational Mapping libraries such as Sequelize (optional).

## Author

- **Name**: Simangele
- **GitHub**: (https://github.com/smangelent@gmail.com)
- **Email**: smangelent@gmail.com

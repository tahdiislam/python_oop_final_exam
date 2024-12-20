# Banking System

This is a Python-based banking system that provides functionalities for managing bank accounts, performing transactions (withdrawals and transfers), and handling users with different roles such as account holders and admins. The system follows Object-Oriented Programming (OOP) principles to ensure modularity, reusability, and scalability.

## Features

- **Account Creation**: Allows users to create accounts and log in to the system.
- **Deposit and Withdrawal**: Users can deposit money into their accounts and withdraw funds.
- **Money Transfer**: Users can transfer money between accounts.
- **Transaction History**: The system keeps a history of all transactions, including withdrawals and transfers.
- **Loan Management**: Account holders can request loans and check their loan limits.
- **Admin Panel**: Admins can manage user accounts, view transaction history, and approve or reject loan requests.
- **Account Balance**: Users can check their current account balance.

## OOP Concepts Used

### 1. **Classes and Objects**
- **AccountHolder**: Represents an individual customer with an account. It has attributes such as `balance`, `account_type`, `loan_limit`, and methods like `deposit_money`, `withdraw_money`, and `request_loan`.
- **Admin**: A subclass of `User`, representing an admin user with additional administrative privileges.
- **Transaction**: A base class that represents any financial transaction. It is inherited by subclasses like `Withdraw` and `Transfer`.
- **Bank**: The central entity that manages multiple `AccountHolder` and `Admin` objects, as well as overseeing transactions.

### 2. **Inheritance**
- The **`AccountHolder` class** inherits from the **`User` class**, sharing common attributes like `name`, `email`, and `account_number`. This allows the `AccountHolder` class to reuse the logic of the `User` class while adding specific functionality like account balance management.
- The **`Withdraw`** and **`Transfer`** classes inherit from the **`Transaction`** class, allowing both transaction types to share common behaviors (e.g., `status`) while customizing the details of each transaction type.

### 3. **Encapsulation**
- Private attributes (e.g., `__balance`, `__loan_limit`) are used to restrict direct access to sensitive data. Methods such as `deposit_money`, `withdraw_money`, and `request_loan` are used to safely modify these private attributes, ensuring proper validation and control over how data is changed.
  
  Example of encapsulation in the `AccountHolder` class:
  ```python
  @property
  def balance(self):
      return f"Available Balance: {self.__balance} \n"

  @balance.setter
  def balance(self, amount):
      if amount > 0:
          self.__balance += amount
          print(f"{amount}TK balance added successfully")
### 4. **Polymorphism**
### 5. **Abstraction**
### 6. **Composition**
# Bank Transaction System

This project implements a **Bank Transaction System** that provides features such as **depositing and withdrawing money**, **transferring funds between accounts**, **virtual cards**, **budgeting**, **rewards points**, **notifications**, and **automatic transactions**. The system is designed using Python with Object-Oriented Programming (OOP) principles.

## Features

- **Deposit and Withdrawal**: Users can deposit money into their account and withdraw from it.
- **Transfer Funds**: Users can transfer funds from one account to another.
- **Virtual Cards**: Users can create virtual cards and load them with funds.
- **Budgeting**: Users can create budgets for different categories and track their spending.
- **Rewards Points**: Users earn reward points for transactions, which can be redeemed.
- **Notifications**: The system sends notifications to the user (e.g., transaction successful).
- **Automatic Transactions**: Users can set up automatic transactions to be executed at regular intervals.

## Code Explanation

### 1. Account Class

The `Account` class handles all main bank account operations including deposits, withdrawals, transfers, interest calculation, and transaction tracking.

#### Methods:

- `__init__(self, name)`  
  Creates a new account with a unique ID, initializes balance, reward system, budgeting, and transaction history.

- `deposit(self, amount, from_account=None)`  
  Adds funds to the account balance. Optionally logs who sent the funds.

- `withdraw(self, amount, to_account)`  
  Deducts funds from the account balance if sufficient. Optionally logs the recipient.

- `transfer(self, amount, to_account)`  
  Transfers funds to another account using withdraw and deposit methods.

- `get_balance(self)`  
  Returns the current account balance.

- `get_transactions(self)`  
  Returns a list of recent transactions for the account.

- `apply_interest(self, interest_rate)`  
  Applies interest to the account balance and logs it as a transaction.

---

### 2. VirtualCard Class

The `VirtualCard` class simulates a virtual debit card that can be loaded from an account for separate use.

#### Methods:

- `__init__(self, account)`  
  Creates a virtual card linked to a specific account.

- `load_card(self, amount)`  
  Transfers a specified amount from the linked account to the virtual card.

---

### 3. Budget Class

The `Budget` class allows users to create and manage spending limits for specific categories such as travel, food, etc.

#### Methods:

- `create_budget(self, category, amount)`  
  Initializes a budget for a specific spending category.

- `add_expense(self, category, amount)`  
  Logs an expense under a specific category and updates the remaining budget.

---

### 4. Rewards Class

The `Rewards` class manages a reward point system based on transactions.

#### Methods:

- `add_points(self, amount)`  
  Adds reward points based on a percentage of a transaction amount.

- `redeem_points(self, points_to_redeem)`  
  Deducts and returns points if the user has enough points to redeem.

---

### 5. Notifications Class

The `Notifications` class handles sending system notifications to users.

#### Methods:

- `__init__(self, account)`  
  Binds the notification system to a specific account.

- `send_notification(self, message)`  
  Sends a message to the user tied to the account.

---

### 6. AutoTransaction Class

The `AutoTransaction` class automates regular money transfers between accounts at a fixed time interval.

#### Methods:

- `__init__(self, account, target_account, amount, interval_seconds)`  
  Sets up a scheduled transfer between two accounts.

- `start(self)`  
  Starts the automatic transaction process at the defined interval using a background thread.

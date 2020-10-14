# Banking Accounts Simulation
## The project is to develop a banking application for a bank that has multiple customers spread across the country.

## INTRODUCTION

- We are aware of banking services and would have done some transactions like deposit, withdrawal, transfer of funds and so on.
- A bank typically has large number of customers and maintains the details of each customer i.e. what is the name of my customer, his address, account number, how much money is there in his account etc.
- We also hear about multiple types of accounts like Saving account, Current account.

### The Bank provides following services:
  - A customer can have either of the following type of accounts:
    - **Savings Account** – Generally used for temporary savings. Offers interest at the rate of 7.5% per annum on your savings. Maximum 10 withdrawals are allowed per month. No minimum balance is needed to open or maintain this account.
    - **Current Account** – Generally used by corporates and business men. No interest is offered on this account. No limit of on no. of withdrawals. A customer needs to have minimum 5K to open or maintain this account.
  - A customer can do following transactions:
    - Deposit and withdraw money in his account/s
    - Transfer money to other accounts
    - Print his account statement for given range of dates
  - Bank wants to maintain history of closed accounts i.e. which accounts have been closed on which dates. Bank admin can see this history.
  - Every customer has a customer-id and password to access his account.
    - When a new customer registers himself with the bank, a customer-id is auto generated by the bank and given to him.
    - Password needs to be set by the customer. It should be minimum 8 characters and can be any combination of numeric and alphabets.
    - Allow maximum 3 consecutive re-trials for unsuccessful login attempts.
  - Bank keeps following information of all customers to send regular updates
    - First and Last Name of customer
    - Address has following fields - Address Line 1, Line 2, City, State, Pincode. Pincode should be a 6 digit numeric and rest of the fields are strings.
    - Account no. /s – Account no. is auto-generated by the bank on opening of a new account and is same as customer id.
    - Transactions (withdrawals &amp; deposits) done by the customers on respective accounts
- A customer can have only one account in a bank. (However, the next project i.e. Project V which will build incrementally on top of this project will allow customers to have multiple accounts in a bank.)
- Interest on savings account is not getting applied.
- Account once locked due to 3 successive erroneous passwords cannot be unlocked.
- Password is not encrypted.

### Tables in Database:

#### Username: tanishk

#### Password: 12345   (I know! I know! Not the best password! You can use a good one ;) )

#### Oracle version: 11.2.0.2.0

#### Tables:  
* 1. **CUST\_ACCOUNTS**  
Primary Key: **ID**  
|**Attribute** | **Type** |  
| ---------------------------- |
|**ID** | NUMBER(10) |  
| PASSWORD | VARCHAR2(25) |  
| ACTYPE | VARCHAR2(7) |  
| BALANCE | NUMBER(10) |  
| IS\_LOCKED | VARCHAR2(3) |  

* 2. **CUST\_INFO**  
Primary Key: ID 
|**Attribute** | **Type** |  
| ---------------------------- |
| **ID** | NUMBER(10) |
| FNAME | VARCHAR2(20) |
| LNAME | VARCHAR2(20) |
| ADRLINE1 | VARCHAR2(50) |
| ADRLINE2 | VARCHAR2(50) |
| CITY | VARCHAR2(25) |
| STATE | VARCHAR2(25) |
| PINCODE | NUMBER(6) | 

* 3. **TRANSACTIONS**  
Primary Key: ID 
|**Attribute** | **Type** |  
| ---------------------------- | 
| **ID** | NUMBER(10) |
| TR\_DATE | DATE |
| AMOUNT | NUMBER(10) |
| BALANCE | NUMBER(10) |
| TRTYPE | VARCHAR2(6) |  

* 4. **CLOSED\_ACCOUNTS**  
Primary Key: ID 
|**Attribute** | **Type** |  
| ---------------------------- | 
| **ID** | NUMBER(10) |
| DATE\_CLOSED | DATE |  

* 5. **ADMIN\_INFO**  
Primary Key: ID 
|**Attribute** | **Type** |  
| ---------------------------- |
| **ID** | VARCHAR2(25) |
| PASSWORD | VARCHAR2(25) |
| IS\_LOCKED | VARCHAR2(3) |

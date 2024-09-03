# Simple Bank Project
This is a personal project to design, develop and deploy a backend web service from scratch.

My goal is to create a functional APIs, and at the same time learn more about the tools for backend development.

The programming language that I will be using to develop the service will be **Golang**

## Simple bank service
This project will provide APIs for the frontend to do the following:
+ Create and manage bank accounts, which are composed of owner's name, balance, and currency.
+ Record all balance changes to each of the accounts. So every time some money is added to or subtracted from the account, and account entry record will be created.
+ Perform a money transfer between 2 accounts. This should happan within a transaction, so that either both accounts' balance are updated sucessfully or none of them are.

### setup infrastructure
+ start postgres container:
```
make postgres
```
+ Create simple_bank database:
```
make createdb
```

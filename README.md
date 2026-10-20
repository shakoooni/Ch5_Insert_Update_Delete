# Ch5_Insert_Update_Delete

Welcome! This project uses the Sakila database to practice inserting, updating, and deleting data using the SQL concepts in Chapter 5.

---

## Project Overview

This project demonstrates how to:

- Count records in a table
- Verify a full backup of the customer table
- Compare tables using `CHECKSUM TABLE`
- Identify returned and unreturned rentals using `return_date`
- Verify a partial backup containing returned rentals
- Drop backup tables when they are no longer needed
- Insert related city, address, and customer records
- Use `DEFAULT` and `NULL` when inserting data
- Insert records using an explicit column list
- Update individual records and multiple records with `WHERE`
- Delete records while accounting for foreign key relationships
- Verify changes using `SELECT` queries

The SQL queries are in [Ch_Queries](https://github.com/shakoooni/Ch5_Insert_Update_Delete/blob/main/Ch_Queries).

Repository: [shakoooni/Ch5_Insert_Update_Delete](https://github.com/shakoooni/Ch5_Insert_Update_Delete)

---

## Technologies Used

- MySQL
- Sakila sample database
- MySQL Workbench

---

## Features

- Counts customer records and checks the customer backup
- Compares the original customer table and its backup using checksums
- Counts all rentals, returned rentals, and rentals that have not been returned
- Displays the returned-rental backup
- Removes the temporary backup tables
- Adds Jay Meesala as a new customer with a new city and address
- Adds a second customer, Alex Meesala, using the same address
- Updates both customers' store IDs and email addresses
- Moves both customers to another address with one update statement
- Demonstrates a foreign key restriction when deleting a referenced city
- Deletes the assignment records and checks the customer deletion

---

## New Concepts Used

`COUNT(*)`, full and partial table backups, `CHECKSUM TABLE`, `IS NULL`, `IS NOT NULL`, `DROP TABLE`, `INSERT INTO`, `VALUES`, `DEFAULT`, `NULL`, auto-increment columns, explicit column lists, `UPDATE`, `SET`, `WHERE`, `DELETE FROM`, `IN`, foreign keys, and verification with `SELECT`.

---

## Console Output Testing Example

### Query 1: Full Customer Backup and Verification

Count the customer records, inspect the full backup, and compare the tables using checksums.

**Part 1.1: Count customer records**

![Query 1.1: Customer record count](assets/Q1.1.png)

**Part 1.3: Verify the customer backup**

![Query 1.3: Customer backup verification](assets/Q1.3.png)

**Part 1.4: Compare table checksums**

![Query 1.4: Customer and backup checksums](assets/Q1.4.png)

### Query 2: Partial Rental Backup

Count all rentals, distinguish returned and unreturned rentals, and inspect the backup containing returned rentals.

**Part 2.1.A: Count all rentals**

![Query 2.1.A: Total rental count](assets/Q2.1.png)

**Part 2.1.B: Count returned rentals**

![Query 2.1.B: Returned rental count](assets/Q2.1B.png)

**Part 2.1.C: Count rentals that have not been returned**

![Query 2.1.C: Unreturned rental count](assets/Q2.1C.png)

**Part 2.2: Verify the returned-rental backup**

![Query 2.2: Returned-rental backup](assets/Q2.2.png)

### Query 3: Drop Backup Tables

Drop `customer_full_backup` and `returned_rental` after completing the backup exercises.

![Query 3: Drop backup tables](assets/Q3.png)

### Query 4: Insert a New City, Address, and Customer

Insert a new city and address, then add Jay Meesala as a customer. Use `DEFAULT` for auto-increment and default values, and `NULL` where permitted.

**City record**

![Query 4: New city record](assets/Q4.png)

**Address record**

![Query 4.1: New address record](assets/Q4.1.png)

**Customer record**

![Query 4.2: New customer record](assets/Q4.2.png)

### Query 5: Insert a Second Customer Using a Column List

Insert Alex Meesala with the same address and last name as the first customer. Omit auto-increment, default, and nullable columns, then verify both customers by address ID `606`.

**Part 5.1: Insert the second customer**

![Query 5.1: Insert a second customer](assets/Q5.1.png)

**Part 5.2: Verify the customer records**

![Query 5.2: Customers at address 606](assets/Q5.2.png)

### Query 6: Update Individual Customer Records

Update customer IDs `600` and `601` to store ID `2` and assign their email addresses. Verify both records using address ID `606`.

**Part 6.1: Update the first customer**

![Query 6.1: Update customer 600](assets/Q6.1.png)

**Part 6.2: Update the second customer**

![Query 6.2: Update customer 601](assets/Q6.2.png)

**Part 6.3: Verify both updates**

![Query 6.3: Verify customer updates](assets/Q6.3.png)

### Query 7: Update Multiple Customer Records

Use one `UPDATE` statement to change both customers' address IDs from `606` to `605`, then retrieve the records to verify the change.

**Part 7.1: Update both customers' addresses**

![Query 7.1: Update address IDs](assets/Q7.1.png)

**Part 7.2: Verify the address changes**

![Query 7.2: Customers at address 605](assets/Q7.2.png)

### Query 8: Delete Records and Verify Results

Attempt to delete the new city, remove the related address and customer records, and verify that customer IDs `600` and `601` have been deleted.

**Part 8.1.A: Attempt to delete the city**

![Query 8.1.A: Delete city record](assets/Q8.1.A.png)

**Part 8.1.B: Delete the address**

![Query 8.1.B: Delete address record](assets/Q8.1.B%20.png)

**Part 8.1.C: Delete the customers**

![Query 8.1.C: Delete customer records](assets/Q8.1.C%20.png)

**Part 8.2: Verify the customer deletion**

![Query 8.2: Verify deleted customer records](assets/Q8.2.png)

**Part 8.3: Foreign Key Issue and Resolution**

MySQL prevented the city from being deleted while an address still referenced it. After moving the two customers to address ID `605`, the new address at ID `606` could be removed before deleting city ID `601`. The assignment also deletes customer IDs `600` and `601` and uses a `SELECT` query to check that those customer records no longer exist.

---

## Author

**Jay Meesala**  
GitHub: [@shakoooni](https://github.com/shakoooni)

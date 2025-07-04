🧾 Test Data – Registration Form (Ticket Service)

📌 Description
This document provides test cases for the **registration form** of the Ticket Service project.  
The goal is to validate input fields using the techniques of **Equivalence Partitioning (EP)** and **Boundary Value Analysis (BVA)**.

The tested fields include:
- Name
- Surname
- Email
- Password
- Phone Number

Each test case checks both valid and invalid inputs to ensure the form handles data correctly and securely.

🧪 Test Cases – Registration Form

| TC ID | Field      | Input                          | Expected Result                  | Class/Boundary          |
|-------|------------|--------------------------------|----------------------------------|-------------------------|
| TC01  | Name       | Alice                          | ✅ Valid                         | EC Positive             |
| TC02  | Name       | A                              | ❌ Invalid (too short)           | BVA -1                  |
| TC03  | Name       | Al                             | ✅ Valid                         | BVA Lower Bound         |
| TC04  | Name       | Alexander                      | ✅ Valid                         | BVA Upper Bound (20)    |
| TC05  | Name       | AlexanderTheGreat123           | ❌ Invalid (too long)            | BVA +1                  |
| TC06  | Name       | Al!ce                          | ❌ Invalid (special chars)       | EC Negative             |
| TC07  | Surname    | Smith                          | ✅ Valid                         | EC Positive             |
| TC08  | Surname    | S                              | ❌ Invalid (too short)           | BVA -1                  |
| TC09  | Surname    | Sm                             | ✅ Valid                         | BVA Lower Bound         |
| TC10  | Surname    | Smithsonian                    | ✅ Valid                         | BVA Upper Bound         |
| TC11  | Surname    | Smithsonian123456789           | ❌ Invalid (too long)            | BVA +1                  |
| TC12  | Surname    | Sm!th                          | ❌ Invalid (special chars)       | EC Negative             |
| TC13  | Email      | test@test.com                  | ✅ Valid                         | EC Positive             |
| TC14  | Email      | test.com                       | ❌ Invalid (missing @)           | EC Negative             |
| TC15  | Email      | test@.com                      | ❌ Invalid (missing domain)      | EC Negative             |
| TC16  | Email      | te st@gmail.com                | ❌ Invalid (space)               | EC Negative             |
| TC17  | Password   | Pass123!                       | ✅ Valid                         | EC Positive             |
| TC18  | Password   | password                       | ❌ Invalid (no digit/symbol)     | EC Negative             |
| TC19  | Password   | pass1234                       | ❌ Invalid (no uppercase/symbol) | EC Negative             |
| TC20  | Password   | PASS1234                       | ❌ Invalid (no symbol)           | EC Negative             |
| TC21  | Password   | P1!abcde                       | ✅ Valid                         | BVA Lower Bound (8)     |
| TC22  | Password   | A1b2C3d4E5f6G7h8I9j!           | ✅ Valid                         | BVA Upper Bound (20)    |
| TC23  | Password   | A1!b2c3d4e5f6g7h8i9j0K         | ❌ Invalid (21 chars)            | BVA +1                  |
| TC24  | Phone      | 0501234567                     | ✅ Valid                         | EC Positive             |
| TC25  | Phone      | 123456789                      | ❌ Invalid (9 digits)            | BVA -1                  |
| TC26  | Phone      | 12345678901                    | ❌ Invalid (11 digits)           | BVA +1                  |
| TC27  | Phone      | 05012abc67                     | ❌ Invalid (letters inside)      | EC Negative             |

🔄 Combined Input Test Cases – Registration Form

✅ Valid Combinations

These test combinations use valid data in all fields.

| Combo ID | Name       | Surname      | Email               | Password                  | Phone        | 
|----------|------------|--------------|---------------------|---------------------------|--------------|
| VC01     | Alice      | Smith        | test@test.com       | Pass123!                  | 0501234567   |
| VC02     | Al         | Sm           | test1@test.com      | P1!abcde                  | 0501234567   | 
| VC03     | Alexander  | Smithsonian  | test2@test.com      | A1b2C3d4E5f6G7h8I9j!      | 0501234567   | 

---

❌ Invalid Combinations

These test combinations include at least one invalid input and are expected to fail.

| Combo ID | Name       | Surname      | Email               | Password                  | Phone        | Invalid Field(s)              | 
|----------|------------|--------------|---------------------|---------------------------|--------------|-------------------------------|
| IC01     | A          | Smith        | test3@test.com      | Pass123!                  | 0501234567   | Name (too short)              | 
| IC02     | Alice      | S            | test4@test.com      | Pass123!                  | 0501234567   | Surname (too short)           | 
| IC03     | Alice      | Smith        | test.com            | Pass123!                  | 0501234567   | Email (missing @)             | 
| IC04     | Alice      | Smith        | test5@test.com      | password                  | 0501234567   | Password (no digits/symbols)  | 
| IC05     | Alice      | Smith        | test6@test.com      | Pass123!                  | 123456789    | Phone (too short)             | 
| IC06     | Al!ce      | Smith        | test7@test.com      | Pass123!                  | 0501234567   | Name (special char)           | 
| IC07     | Alice      | Sm!th        | test8@test.com      | Pass123!                  | 0501234567   | Surname (special char)        | 
| IC08     | Alice      | Smith        | test@.com           | Pass123!                  | 0501234567   | Email (missing domain)        | 
| IC09     | Alice      | Smith        | test9@test.com      | A1!b2c3d4e5f6g7h8i9j0K    | 0501234567   | Password (too long)           | 
| IC10     | Alice      | Smith        | test10@test.com     | Pass123!                  | 05012abc67   | Phone (letters inside)        | 
| IC11     | A          | S            | te st@gmail.com     | pass1234                  | 12345678901  | All fields invalid            | 


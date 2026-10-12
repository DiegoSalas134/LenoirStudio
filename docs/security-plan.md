## Security Requirements (Sprint 1)

To protect the system and ensure it works correctly, we will implement the following basic security measures:

### 1. Data Validations
Before saving anything to the database, the server will check that (validations are always done on the server, not only in the frontend):
*   **Customer details:** The name is not empty, and the phone number has exactly 10 digits.
*   **Booking rules:** The requested date is between 24 hours and 14 days in the future.
*   **File uploads:** The payment receipt is strictly an image file (JPG or PNG) and not larger than 5 MB.
*   **Admin actions:** When confirming an appointment, the administrator must input a total price greater than 0.
*   **Inventory:** Stock numbers cannot be negative.
*   **SQL injection:** All database queries use parameters, so user input is never inserted directly into a query.

### 2. Role-Based Access Control
The system has two types of users:
*   **Customers (Public):** They do not need an account. They can only see available time slots and send appointment requests. They cannot see other clients' information or any financial data.
*   **Administrator:** The administrator needs to log in with a username and password. Only the administrator can access the private dashboard to view the calendar, approve payments, edit inventory, and generate income reports. We will use tokens to keep the session secure.

### 3. Secrets Protection
*   **Hidden Credentials:** Passwords for our database and secret keys will be stored locally in a `.env` file. We added this file to our `.gitignore` so we never accidentally upload our passwords to GitHub.
*   **Encrypted Passwords:** We will not save the administrator's password as plain text in the database. We will encrypt/hash it (using a library like bcrypt) so nobody can read it.

### 4. Security Test Cases
We will test these scenarios in the next sprints to prove our security works:
*   **Test 1 (Login):** Try to log in with the wrong password. *Expected result: The system shows an error message and denies access.*
*   **Test 2 (Missing file):** Try to book an appointment without attaching the payment image. *Expected result: The server rejects the request and does not save the appointment.*
*   **Test 3 (Wrong file):** Try to upload a `.pdf` file as a payment receipt. *Expected result: The server rejects the file because it only accepts images.*
*   **Test 4 (Double booking):** Try to book a time slot that is already taken by another client. *Expected result: The server shows an error and prevents the double booking.*
*   **Test 5 (Protected routes):** Try to open the financial reports without logging in first. *Expected result: The server responds with 401 Unauthorized and the frontend sends the user to the login screen.*
*   **Test 6 (GitHub):** Review our GitHub repository online. *Expected result: No database passwords or `.env` files are visible to the public.*
*   **Test 7 (Phone):** Submit a form where the phone has 8 or 12 digits instead of 10. *Expected result: The server rejects the request and does not save the appointment.*
*   **Test 8 (SQL injection):** Try to log in using `' OR 1=1 --` as the username. *Expected result: The system denies access.*
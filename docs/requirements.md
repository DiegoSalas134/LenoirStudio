# System Requirements

## Functional Requirements (FR)

- RF-01: The system must allow for dynamic pricing of nail application, filling, and removal services.
- RF-02: The system must allow appointments to be scheduled in 3 or 1-hour blocks depending on the service that was choosen, within a range of 24 hours to 14 days in the future, while preventing overlapping time slots.
- RF-03: The system must capture the client's name and phone number, and require the upload of a payment receipt (in JPG or PNG format) to register the appointment as "Pending". It must also allow an optional design reference image to be uploaded and stored.
- RF-04: The system must have a dedicated login screen for administrators.
- RF-05 The system must encrypt passwords in the database and validate access attempts by displaying generic error messages for security purposes.
- RF-06: The system must allow the administrator to view the calendar, approve payments, input the total price, and change the status of appointments (Confirmed, Canceled, Rescheduled, and Completed).
- RF-07: The system must generate dynamic WhatsApp links to notify the customer of the status of their appointment or if there was a modification on the price.
- RF-08: The system must allow the administrator to block entire days or 1 to 3-hour blocks to prevent reservations.
- RF-09: The system must allow the administrator to add, view, edit, and delete inventory items (including their unit cost), and must include a search bar and filters.
- RF-10: The system must generate automatic visual alerts on the inventory screen when a product's quantity reaches its minimum threshold.
- RF-11: The system must generate dynamic on-screen financial reports filtered by date, displaying the Net Profit calculated by subtracting Total Expenses from the Total Revenue of "Completed" appointments.
- RF-12: The system must allow the administrator to manually register general business expenses (e.g., inventory restocks, rent, supplies) to maintain accurate financial records.
## Non-Functional Requirements (NFR)

- RNF-01 Response Time: The system must process user requests and load the main views (quote generator, calendar, inventory) within a reasonable amount of time (less than 2 seconds).
- RNF-02 Browser and Device Compatibility: The system must be a responsive web application accessible from standard web browsers on both mobile devices (smartphones) and desktop computers.
- RNF-03 Data Backups: The system must generate automatic, periodic backups of appointment, customer, and inventory data to prevent data loss in the event of a system failure.
- RNF-04 Availability: The system must be available for public online scheduling at all times (99% of operating time).
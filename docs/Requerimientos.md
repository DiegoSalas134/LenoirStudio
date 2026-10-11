# System Requirements

## Functional Requirements (FR)

- RF-01: The system must allow for dynamic pricing of nail application, filling, and removal services.
- RF-02: The system must allow appointments to be scheduled in 3-hour blocks, within a range of 24 hours to 14 days in the future, while preventing overlapping time slots.
- RF-03: The system must capture the client's name and phone number, and require the upload of a payment receipt (in JPG or PNG format) to register the appointment as "Pending". It must also allow an optional design reference image to be uploaded and stored.
- RF-04: The system must have a dedicated login screen for administrators.
- RF-05 The system must encrypt passwords in the database and validate access attempts by displaying generic error messages for security purposes.
- RF-06: The system must allow the administrator to view the calendar, approve payments, and change the status of appointments (Confirmed, Canceled, Rescheduled)
- RF-07: The system must generate dynamic WhatsApp links to notify the customer of the status of their appointment.
- RF-08: The system must allow the administrator to block entire days or 3-hour blocks to prevent reservations.
- RF-09: The system must allow users to add, view, edit, and delete inventory items, and must include a search bar and filters.
- RF-10: The system must generate automatic visual alerts on the inventory screen when a product's quantity reaches its minimum threshold.
- RF-11: The system must generate dynamic on-screen financial reports filtered by date, breaking down the total advance payments and outstanding balances receivable.

## Non-Functional Requirements (NFR)

- RNF-01 Response Time: The system must process user requests and load the main views (quote generator, calendar, inventory) within a reasonable amount of time (less than 2 seconds).
- RNF-02 Browser and Device Compatibility: The system must be a responsive web application accessible from standard web browsers on both mobile devices (smartphones) and desktop computers.
- RNF-03 Data Backups: The system must generate automatic, periodic backups of appointment, customer, and inventory data to prevent data loss in the event of a system failure.
- RNF-04 Availability: The system must be available for public online scheduling at all times (99% of operating time).


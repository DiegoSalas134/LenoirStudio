## Architecture Design (Sprint 1)

### 1.Folder Structure
```
LenoirStudio/
|--- docs/
|--- backend/
|   |---src/
|   |   |--- routes/
|   |   |--- controllers/
|   |   |--- models/
|   |   |--- middlewares/
|   |   |--- config/
|   |--- tests/
|   |---.env.example
|---frontend/
```

### 2. Responsibilities
*   **Routes:** Define the API URLs and send each request to the right controller. They contain no business logic.
*   **Middlewares:** Run before the controller. They validate the input, verify the administrator's token and handle the uploaded images.
*   **Controllers:** Contain the business rules (booking window, quote calculation, status changes, report totals).
*   **Models:** The only layer that talks to the database, using parameterized queries.
*   **Config:** Reads the `.env` variables and sets up the database connection.

### 3. Routes
*   **Public:** `GET /api/availability`, `POST /api/appointments`, `POST /api/auth/login`
*   **Administrator (token required):** `/api/appointments`, `/api/blocks`, `/api/inventory`, `/api/expenses`, `/api/reports`

### 4. Middlewares
*   **auth:** Checks the token on administrator routes and answers 401 if it is missing, invalid or expired.
*   **validate:** Checks the body, params and query before the controller runs.
*   **upload:** Accepts only JPG and PNG images up to 5 MB.
*   **errorHandler:** Returns clear errors with the correct HTTP status code.
  # Expense Tracker – Personal Finance Dashboard

  This project is a full-stack **Expense Management System** built using **FastAPI**, **Streamlit**, and **MySQL**.  
  It allows users to record daily expenses, visualize category-wise spending, and analyze trends — all in a clean, intuitive interface.

  The goal was to build a **simple yet powerful personal finance app** that helps individuals or small teams make data-driven budgeting decisions.

  ---

  ## Project Objective

  Managing daily expenses manually can be time-consuming and error-prone.  
  The goal of this project was to:
  - Build a lightweight backend using **FastAPI + MySQL**  
  - Create an interactive **Streamlit dashboard** for expense entry and analytics  
  - Track daily, weekly, or monthly spending patterns  
  - Understand where the majority of money is going through visual analytics  

  In short — a clean and efficient personal finance tracker with live analytics.

  ---

  ## Data Structure

  The system revolves around one central table in the MySQL database:

  **Table: `expenses`**
  | Column        | Type         | Description                    |
  |----------------|--------------|--------------------------------|
  | expense_date   | DATE         | Date of expense                |
  | amount         | FLOAT        | Amount spent                   |
  | category       | VARCHAR(50)  | Expense category (e.g., Food)  |
  | notes          | TEXT         | Optional notes                 |

  Data operations include:
  - Fetching daily expenses  
  - Deleting and re-inserting expenses for updates  
  - Summarizing expenses by category and date range  

  ---

  ## Architecture Overview
  
```
Expense Tracker/
│
├── backend/
│   ├── server.py              # FastAPI server & endpoints
│   ├── db_helper.py           # MySQL queries (CRUD)
│   ├── logging_setup.py       # Logger for backend operations
│   └── server.log             # Runtime logs
│
├── frontend/
│   ├── app.py                 # Main Streamlit entry
│   ├── add_update_ui.py       # Add/Update Expense tab
│   └── analytics_ui.py        # Analytics tab
│
├── database/
│   └── expense_manager.sql    # SQL script to create DB and table
│
├── tests/
│   ├── backend/
│   │   └── test_db_helper.py  # Unit tests for db_helper
│   └── conftest.py            # Path configuration for tests
│
├── requirements.txt
└── .gitignore
```



---

## Key Features & Insights

### 1. Add or Update Daily Expenses  
- Add multiple expense entries per date.  
- Edit or replace previous entries easily.  

### 2. Real-time Analytics Dashboard  
- Choose a custom date range and view total spend per category.  
- Auto-calculates category-wise percentages of total spending.  
- Displays a **bar chart** of expense distribution.  

### 3. Logging and Transparency  
- Every backend operation (insert, delete, fetch) is logged in `server.log`.  
- Helps in debugging and understanding database interactions.  

### 4. Modular and Scalable Design  
- Backend and frontend are decoupled.  
- Can be extended to include authentication, reports, or recurring payments.  

---

## Data Visualizations

- **Bar Chart:** Category-wise expense percentage  
- **Expense Table:** Clean formatted view of spending  
- **Dynamic Filters:** Analyze custom time ranges  
- **Summary Metrics:** Total spend, category contribution  

---

## Tools & Technologies Used
- **Frontend:** Streamlit  
- **Backend:** FastAPI  
- **Database:** MySQL  
- **Data Handling:** Pandas  
- **Testing:** Pytest  
- **Language:** Python 3.11+  

---

## Value of the Application

This project provides a **simple yet extensible foundation** for personal finance tracking.  
Users can:
- Identify spending leaks in real-time  
- Visualize spending habits across categories  
- Use insights for better monthly budgeting  

In simple words:
- **FastAPI keeps the backend clean.**  
- **Streamlit keeps the frontend beautiful.**  
- **You keep your finances under control.**

---

## How to Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/expense-tracker.git
   cd expense-tracker
   ```

2. **Set Up Virtual Environment**
   ```bash
   python -m venv .venv
   # Windows
   .venv\Scripts\activate
   # macOS/Linux
   source .venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure MySQL Database**
   - Create a new database:
     ```sql
     CREATE DATABASE expense_manager;
     ```
   - Run the SQL script inside `database/expense_manager.sql`  
   - Update credentials in `backend/db_helper.py` if needed.

5. **Run the Backend**
   ```bash
   cd backend
   uvicorn server:app --reload
   ```

6. **Run the Frontend**
   ```bash
   cd frontend
   streamlit run app.py
   ```

- Backend: http://127.0.0.1:8000  
- Frontend: http://localhost:8501  

---

## Running Tests
From the project root:
```bash
pytest
```

---

## Author

**Kushal Samani**  
- Email: [kushalsamani04@gmail.com](mailto:kushalsamani04@gmail.com)  
- LinkedIn: [https://www.linkedin.com/in/kushalsamani](https://www.linkedin.com/in/kushalsamani)


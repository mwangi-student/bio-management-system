# Bio Management System - author [ Mwangi Brian]

A web application designed to help instructors manage data related to themselves, students, and courses efficiently. The system is built using **FastAPI** for the backend, **Alembic** and **SQLAlchemy** for database management, **Vite React** for the frontend, and **Tailwind CSS** for styling.

---

## Table of Contents

1. [Features](#features)
2. [Technologies Used](#technologies-used)
3. [Installation](#installation)
4. [Set-Up Migrations](#set-up-migrations)
5. [Running the Project](#running-the-project)
6. [Future Plans](#future-plans)
7. [Live Demo](#live-demo)
8. [GitHub Repository](#github-repository)

---

## Features

- Manage instructors, students, and courses.
- User-friendly interface styled with **Tailwind CSS**.
- Database version control using **Alembic**.

---

## Technologies Used

- **FastAPI**: Backend framework for building APIs.
- **SQLAlchemy**: ORM for database management.
- **Alembic**: Database migration tool.
- **React** (via Vite): Frontend framework for building the user interface.
- **Tailwind CSS**: Utility-first CSS framework for styling.

---

## Installation

### Prerequisites

Ensure you have the following installed:

- Python (>= 3.8)
- Node.js (>= 14)
- npm or yarn
- SQLite (or your database of choice)

### Backend Setup

1. Clone the repository:

   ```bash
   git clone <repository-link>
   cd bio-management-system
   ```

2. Set up a virtual environment and install dependencies:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```

3. Create your SQLite database file:
   ```bash
   touch school.db
   ```

### Frontend Setup

1. Navigate to the frontend directory:

   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

---

## Set-Up Migrations

### Initial Setup

1. Initialize Alembic for database migrations:

   ```bash
   alembic init migrations
   ```

   _(Run this command only once.)_

2. Open the `alembic.ini` file and configure the database URL:

   ```ini
   sqlalchemy.url = sqlite:///school.db
   ```

   _(Replace `school.db` with your database name, if different.)_

3. Update the `env.py` file in the `migrations` folder:
   - Import the `Base` class from your `models` file.
   - Update the `target_metadata` variable with your `Base` metadata.

### Running Migrations

1. Create a new migration file:

   ```bash
   alembic revision --autogenerate -m "initial migration"
   ```

2. Apply the migration:
   ```bash
   alembic upgrade head
   ```

---

## Running the Project

### Backend

1. Start the FastAPI server:

   ```bash
   uvicorn app:app --reload
   ```

   ```
   fastapi dev app.py
   ```

2. Access the API documentation at `http://127.0.0.1:8000/docs`.

### Frontend

1. Navigate to the `frontend` directory:

   ```bash
   cd frontend
   ```

2. Start the development server:

   ```bash
   npm run dev
   ```

3. Open the application in your browser at `http://localhost:3000`.

---

## Future Plans

1. **Authentication System**:
   - Add user roles such as admin, instructor, and student.
   - Secure access to various parts of the application using JWT-based authentication.
2. **Report Writing Capabilities**:
   - Enable instructors to generate and download reports for courses, students, and grades.

---

## Live Demo

Check out therecoring of the  live application: [Demo recording Link](https://drive.google.com/drive/my-drive)

---

## GitHub Repository

Clone or explore the source code: [GitHub Repo Link](https://github.com/mwangi-student/bio-management-system)

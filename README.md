# FastAPI + PostgreSQL CRUD API

A hands-on backend learning project built to understand REST API development, database integration, and CRUD operations using FastAPI, SQLAlchemy, and PostgreSQL.

The backend was written from scratch as a learning exercise. The repository also includes a React frontend developed with AI assistance to explore frontend-backend integration.

## What I Learned

- Building REST API endpoints with FastAPI
- Defining request models and validating data with Pydantic
- Connecting a Python application to PostgreSQL using SQLAlchemy
- Managing database sessions and performing CRUD operations
- Using environment variables to keep database credentials out of source code
- Configuring and using a Python virtual environment
- Testing API endpoints using Swagger UI and verifying database changes in pgAdmin
- Using Git to track project changes and maintain version history

## Tech Stack

**Backend**
- Python
- FastAPI
- Pydantic
- SQLAlchemy
- Uvicorn

**Database**
- PostgreSQL
- pgAdmin

**Frontend**
- React (AI-assisted implementation)

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Returns a welcome message |
| GET | `/products` | Retrieves all products |
| GET | `/products/{id}` | Retrieves a product by ID |
| POST | `/products` | Creates a new product |
| PUT | `/products/{id}` | Updates an existing product |
| DELETE | `/products/{id}` | Deletes a product |

The API uses PostgreSQL to persist product data. Interactive API documentation is available through Swagger UI at `/docs` when the backend is running.

## Project Structure

```text
fastapi-postgresql-react/
├── frontend/             # React frontend
├── main.py               # FastAPI application and routes
├── models.py             # Pydantic request models
├── database.py           # Database connection and sessions
├── database_models.py    # SQLAlchemy database models
├── requirements.txt      # Python dependencies
├── .gitignore            # Files excluded from Git
└── README.md             # Project documentation
```

## Getting Started

### Prerequisites

- Python 3.10 or a compatible version
- PostgreSQL
- Git
- PowerShell on Windows

### 1. Clone the repository

```powershell
git clone https://github.com/Nandinii-22/fastapi-postgresql-react.git
cd fastapi-postgresql-react
```

### 2. Create and activate a virtual environment

```powershell
python -m venv myenv
.\myenv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can run the environment's Python executable directly instead.

### 3. Install dependencies

```powershell
python -m pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root, alongside `main.py`.

Add the following configuration and replace the example values with your own PostgreSQL credentials:

```dotenv
DB_USER=postgres
DB_PASSWORD=your_postgresql_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=FastApi_db
```

Before starting the application:

- Ensure PostgreSQL is running.
- Create the `FastApi_db` database in PostgreSQL.
- Ensure the database username and password match your local configuration.

**Security:** Never commit your `.env` file or real database credentials to GitHub. The `.gitignore` file is configured to exclude environment files.

### 5. Start the backend

```powershell
python -m uvicorn main:app --reload
```

Once the server starts, open these URLs in your browser:

- **API root:** http://127.0.0.1:8000/
- **Swagger UI:** http://127.0.0.1:8000/docs
- **ReDoc:** http://127.0.0.1:8000/redoc

You can use Swagger UI to send requests to the product endpoints and inspect their responses.

## Testing

The API endpoints were tested using Swagger UI, and database changes were verified in pgAdmin.

The project includes operations to create, retrieve, update, and delete products, with changes persisted in PostgreSQL.

## Project Scope

This project focuses on learning backend fundamentals, REST API development, database connectivity, SQLAlchemy ORM operations, request validation, and CRUD functionality.

The React frontend is included to explore frontend-backend integration. Its implementation was developed with AI assistance.

## Future Improvements

- Add automated API tests using Pytest
- Improve request and response validation
- Introduce Alembic for database migrations
- Add Docker support
- Improve error handling and API response consistency
- Improve frontend-backend integration and documentation
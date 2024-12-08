# Current Pod: 4 – Database

## Usage

Our feature is a SQLite database that implements tables needed to store data for our touchless kiosk built with Python and SQLAlchemy.

## Installation

* SQLAlchemy (`pip install SQLAlchemy` and `pip install SQLAlchemy-Utils`) - With SQLAlchemy, you can use classes and Python code to create a database and run queries instead of directly using SQL queries.
* Faker (`pip install Faker`) - With Faker, you can generate random mock data that can either stay in the database permanently (static) or be recreated every time the program is run. Not all the mock data should be randomly generated, so be sure to double check.
* Uvicorn (`pip install "fastapi[standard]"`) - Uvicorn should be included in FastAPI, which is required to build and use our API. Uvicorn is the production server that the database, API, and application will be hosted on. To launch the app from the project root, run the command `uvicorn backend.main:app --reload`.
* Pytest (`pip install pytest`) - With Pytest, you can write and run tests on Python code. Be sure to run `pytest` before committing and pushing your changes to assure that you are not breaking previous code.

You can also install all of these except "fastapi[standard]" by simply running `pip install --upgrade -r requirements.txt`.


## Contributors

* Leila Lewis
* Momin Asif
* Omar Essa
* Peter Kopylov

## Suggestions/comments (optional)

### Accessing Relationships in Python SQLAlchemy Classes

When working with our Python classes/tables, you can access associated table information directly through the relationship property of the Python class. This avoids the need for using SQL joins when accessing the data.

### Two Tables: `User` and `Role`

#### Accessing Roles Belonging to a User

To access the roles belonging to a `User`, utilize the `user_roles` relationship property inside the `User` class:

```python
for role in user.user_roles:
    print(f"Role: {role.role_name}")
```

To access the users belonging to a `Role`, utilize our `users` relationship property inside the `Role` Class:

```python
for user in role.users:
    print(f"User: {user.name}")
```
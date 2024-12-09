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
### Reference Table Values

#### User Role IDs:
1. **Student**: "Someone who attends classes and pays tuition."
2. **Admin**: "Administrator with full access to all features."
3. **Tutor**: "Responsible for guiding and assisting students in their learning process."
4. **Teaching Assistant**: "Helps teach newer students."
5. **Teacher**: "Responsible for planning, delivering lessons, and assessing student progress."
6. **Staff Member**: "Support and manage institutional operations and administrative tasks."

#### Tag IDs:
1. **Hackathon**: "Tag for Hackathon events."
2. **ACM**: "Tag for ACM events."
3. **ACMW**: "Tag for ACMW events."
4. **CTF**: "Tag for CTF events."
5. **GDSC**: "Tag for GDSC events."
6. **ICPC**: "Tag for ICPC events."
7. **IEEE**: "Tag for IEEE events."
8. **IGDA**: "Tag for IGDA events."
9. **Robotics**: "Tag for Robotics events."
10. **WebDev**: "Tag for WebDev events."
11. **Workshops**: "Tag for Workshops events."
12. **Jobs**: "Tag for Jobs events."
13. **Research**: "Tag for Research events."

#### Club IDs:
1. **ACM**: "Tag for ACM events."
2. **ACMW**: "Tag for ACMW events."
3. **CTF**: "Tag for CTF events."
4. **GDSC**: "Tag for GDSC events."
5. **ICPC**: "Tag for ICPC events."
6. **IEEE**: "Tag for IEEE events."
7. **IGDA**: "Tag for IGDA events."
8. **Robotics**: "Tag for Robotics events."

#### Schedule Type IDs:
1. **Availability**: "Indicates availability for rooms or tutors."
2. **Booking**: "Indicates a booking event."
3. **Request**: "Indicates a time request awaiting approval."

#### Repeat Rule IDs:
1. **No Repeat**: "No repetition."
2. **Daily**: "Repeats daily."
3. **Weekly**: "Repeats weekly."
4. **Bi-weekly**: "Repeats every two weeks."
5. **Monthly**: "Repeats monthly on the same date."
6. **Yearly**: "Repeats yearly on the same date."

---

### Information on Scheduling

#### Schedule Class Relationships:
- **`schedule_type`**: Each instance of the Schedule class has one schedule type (e.g., Booking, Availability, Request).
- **`repeat_rule`**: Each instance has one repeat rule (e.g., "No Repeat", "Daily", "Weekly", "Monthly", "Yearly").
- **`booking_rooms`**: Each instance can have more than one room booked for a specific schedule.
- **`booking_tutors`**: Each instance can have more than one tutor booked for a specific schedule.
- **`availability_rooms`**: Each instance can have multiple rooms available for a specific schedule.
- **`availability_tutors`**: Each instance can have multiple tutors available for a specific schedule.

#### Booking and Availability Relationships:
Each instance of `BookingTutor`, `BookingRoom`, `AvailabilityTutor`, or `AvailabilityRoom` can have multiple schedule instances. For example, a tutor can have an availability schedule on:
- **Monday 3 PM - 5 PM**
- **Tuesday 4 PM - 6 PM**

#### Code Examples:
**Retrieve Tutor Availability Schedules with Repeats:**
```python
def get_tutoravailabilityschedules_with_repeats(tutor_id, start_date, end_date):
    availability_tutor = db.query(AvailabilityTutor).filter(
        AvailabilityTutor.availabilitytutor_tutorid == tutor_id
    )
    results = []

    for schedule in availability_tutor.schedules:
        current_start = schedule.schedule_start_time
        repeat_rule = schedule.repeat_rule

        while current_start <= end_date:
            if current_start >= start_date:
                results.append({
                    "name": schedule.name,
                    "start_time": current_start,
                    "end_time": current_start + (schedule.schedule_end_time - schedule.schedule_start_time)
                })

            # Calculate the next occurrence based on the repeat rule
            if repeat_rule.name == "No Repeat":
                break  # No repeat
            elif repeat_rule.name in {"Daily", "Weekly", "Monthly", "Yearly"}:
                current_start += timedelta(days=repeat_rule.interval)
            elif repeat_rule.name == "Bi_weekly":
                current_start += timedelta(days=14)
            else:
                raise ValueError(f"Unknown or invalid repeat rule: {repeat_rule.name}")

    return results
```
**To add instances of an availability schedule to a Tutor:**
```python
availability_tutor.schedules = [
    Schedule(
        schedule_name="Monday_Sched", 
        schedule_start_time=datetime(2024, 12, 22, 14, 30, 0), 
        schedule_end_time=datetime(2024, 12, 22, 16, 30, 0), 
        schedule_scheduletype_id=1, 
        schedule_repeatrule_id=3
    ),
    Schedule(
        schedule_name="Wednesday_Sched", 
        schedule_start_time=datetime(2024, 12, 24, 14, 30, 0), 
        schedule_end_time=datetime(2024, 12, 24, 16, 30, 0), 
        schedule_scheduletype_id=1, 
        schedule_repeatrule_id=3
    ),
]
db.commit()
```

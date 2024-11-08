# Roadmap Document: Pod 1

## 1. Overview of Systems
### Shared Systems
- **User Management System**: Manage users, enable secure login and session.
- **Remote System**: Let entire system be accessible remotely via browser/app.

### User-Specific Systems
- **Information System**: Provides general information
- **Student-Tutor System**: Schedules & Appointments

## 2. Systems Breakdown: Milestones & Tasks
### Shared Systems
#### User Management System
- **Milestone 1**: Basic user management functionality.
  - **Sprint 1**: Implement user database with different rights (priority: high, complexity: medium)
  - **Sprint 2**: Develop login API (priority: high, complexity: medium).
  - **Sprint 3**: Implement session management (priority: high, complexity: medium).

#### Remote System
- **Milestone 1**: Basic remote access functionality.
  - **Sprint 1**: Make browser/app version of Kiosk (priority: medium, difficulty: hard)
  - **Sprint 2**: Make backend accessible from any device (priority: medium, difficulty: medium)

### User-Specific Systems
#### Information System
- **Milestone 1**: Campus Map
  - **Sprint 1**: Create campus file in backend. This has to be updated with future sprints (Priority: Critical, Difficulty: Medium)
  - **Sprint 2**: Let frontend fetch campus file periodically/look for updates (Priority: Critical , Difficulty: Easy)
  - **Sprint 3**: Frontend: Implement static campus maps for campus, buildings, rooms (Priority: Critical, Difficulty: Easy)
  - **Sprint 4**: Frontend: Implement campus map with light interactivity: Display building/room information by clicking on it (Priority: High, Difficulty: Medium)
  - **Sprint 5**: Frontend: Implement fully interactive, user-friendly campus and buildings maps with search option, e.g. scrollable, zoomable, complete (Priority: Medium, Difficulty: Hard)
- **Milestone 2** Bulletin Board
  - **Sprint 1**: Implement database for bulletin board. Connect it to users (Priority: Medium, Difficulty: Easy)
  - **Sprint 2**: Implement API endpoints to create, change, delete entries (Priority: Medium, Difficulty: Easy)
  - **Sprint 3**: Create GUI for frontend (Priority: Medium, Difficulty: Medium)
  - **Sprint 4**: Let frontend communicate with backend (Priority: Medium, Difficultly: Easy)
- **Milestone 3**: Dining Menus
  - **Sprint 1**: Create database for dining menus (Priority: Critical, Difficulty: Easy)
  - **Sprint 2**: Keep database uptodate, preferably by fetching data uptodate data from dining venues (Priority: Critical, Difficulty: Medium)
  - **Sprint 3**: Design frontend (Priority: Critical, Difficulty: Medium)
  - **Sprint 4**: Keep frontend data updated (Priority: Critical, Difficulty: Easy)
- **Milestone 4**: University 101
  - **Sprint 1**: Create necessary files in backend (Priority: High, Difficulty: Medium)
  - **Sprint 2**: Keep frontend updated (Priority: High, Difficulty: Easy)
  - **Sprint 3**: Design GUI (Priority: High, Difficultly: Medium)
  - **Sprint 4**: Implement feature to call support from kiosk (Priority: Low, Difficulty: Hard)
- **Milestone 5**: Emergency 
  - **Sprint 1**: Design GUI (Priority: Critical, Difficulty: Medium)
  - **Sprint 2**: Give ability to fetch advice etc. from official resources (Priority: Critical, Difficulty: Medium)
  - **Sprint 3**: Let it activate automatically in case of emergency and overlay other application in this case (Priority: Critical, Difficulty: Medium)
- **Milestone 6**: Events
  - **Sprint 1**: Create event database, connected to users and/or user groups (Priority: Medium, Difficulty: Easy)
  - **Sprint 2**: Allow creation, modification, deletion (Priority: Medium, Difficulty: Medium)
  - **Sprint 3**: Design frontend and keep it up to date (Priority: Medium, Difficulty: Medium)
  - **Sprint 4**: Make past events accessible (Priority: Low, Difficulty: Easy)
- **Milestone 7**: Announcements
  - **Sprint 1**: Create database and make users with according rights able to post and modify (Priority: High, Difficulty: Easy)
  - **Sprint 2**: Design GUI, make it display on main screen (Priority: High, Difficulty: Easy)
  - **Sprint 3**: Keep frontend uptodate with backend and database (Priority: HIgh, Difficulty: Easy)
- **Milestone 8**: Rules and Resources
  - **Sprint 1**: Design GUI (Priority: Low, Difficulty: Easy)
  - **Sprint 2**: Let fetch from official resources (Priority: Low, Difficulty: Easy)
- **Milestone 9**: Main Screen
  - **Sprint 1**: Implement a screen to select which information to display (Priority: High, Difficulty: Easy)

#### Student-Tutor System
- **Milestone 1:** Course Schedule
  - **Sprint 1:** Create database and make it accessible to appropriate users (Priority: Critical, Difficulty: Medium)
  - **Sprint 2:** Design student frontend and keep it uptodate with backend (Priority: Critical, Difficulty: Easy)
  - **Sprint 3:** Give appropriate users (e.g. teachers) rights to modify their courses (Priority: Critical, Difficulty: Easy)
  - **Sprint 4:** Design teacher frontend (Priority: Critical, Difficulty: Easy)
  - **Sprint 5:** Give teachers the ability to post announcements for each course (Priority: Critical, Difficulty: Easy)
  - **Sprint 6:** Student should receive notification about changes and announcements (Priority: High, Difficulty: Medium)
  - **Sprint 7:** Students should see course location (Priority: Medium, Difficulty: Easy)
  - **Sprint 8:** Link this location to campus map (Priority: Low, Difficulty: Medium)
  - **Sprint 9:** Give teachers to track attendance (Priority: Low, Difficulty: Medium)
- **Milestone 2:** Appointment Booking
  - **Sprint 1:** Design database and give appropriate users appropriate access (Priority: High, Difficulty: Medium)
  - **Sprint 2:** Design frontend and communicate with backend (Priority: High, Difficulty: Medium)
  - **Sprint 3:** Do not allow invalid appointment booking in backend and user-friendly solution in frontend (Priority: High, Difficulty: Easy)
- **Milestone 3:** Tutor Schedules
  - **Sprint 1:** Design database and give appropriate users appropriate access (Priority: High, Difficulty: Medium)
  - **Sprint 2:** Design frontends for different user types (Priority: High, Difficulty: Medium)
  - **Sprint 3:** Link room information to campus map (Priority: Low, Difficulty: Medium)

## 3. Incremental Cycles
### Cycle 1: Minimum Viable Product (MVP)
- **Information System**:
  - Milestone 1, Sprint 1 (priority: critical).
  - Milestone 1, Sprint 2 (priority: critical).
  - Milestone 1, Sprint 3 (priority: critical).
  - Milestone 3, Sprint 1 (priority: critical).
  - Milestone 3, Sprint 2 (priority: critical).
  - Milestone 3, Sprint 3 (priority: critical).
  - Milestone 3, Sprint 4 (priority: critical).
  - Milestone 5, Sprint 1 (priority: critical).
  - Milestone 5, Sprint 2 (priority: critical).
  - Milestone 5, Sprint 3 (priority: critical).
- **Student-Tutor System**:
  - Milestone 1, Sprint 1 (priority: critical).
  - Milestone 1, Sprint 2 (priority: critical).
  - Milestone 1, Sprint 3 (priority: critical).
  - Milestone 1, Sprint 4 (priority: critical).
  - Milestone 1, Sprint 5 (priority: critical).

### Cycle 2: High Priority Features
- **User Management System**:
  - Milestone 1, Sprint 1 (priority: high).
  - Milestone 1, Sprint 2 (priority: high).
  - Milestone 1, Sprint 3 (priority: high).
- **Information System**:
  - Milestone 1, Sprint 4 (priority: high).
  - Milestone 4, Sprint 1 (priority: high).
  - Milestone 4, Sprint 2 (priority: high).
  - Milestone 4, Sprint 3 (priority: high).
  - Milestone 7, Sprint 1 (priority: high).
  - Milestone 7, Sprint 2 (priority: high).
  - Milestone 7, Sprint 3 (priority: high).
  - Milestone 9, Sprint 1 (priority: high).
- **Student-Tutor System**:
  - Milestone 2, Sprint 1 (priority: high).
  - Milestone 2, Sprint 2 (priority: high).
  - Milestone 2, Sprint 3 (priority: high).
  - Milestone 3, Sprint 1 (priority: high).
  - Milestone 3, Sprint 2 (priority: high).
  - Milestone 1, Sprint 6 (priority: high).

### Cycle 3: Medium and Low Priority Features
- **Remote System**:
  - Milestone 1, Sprint 1 (priority: medium).
  - Milestone 1, Sprint 2 (priority: medium).
- **Information System**:
  - Milestone 1, Sprint 5 (priority: medium).
  - Milestone 2, Sprint 1 (priority: medium).
  - Milestone 2, Sprint 2 (priority: medium).
  - Milestone 2, Sprint 3 (priority: medium).
  - Milestone 2, Sprint 4 (priority: medium).
  - Milestone 6, Sprint 1 (priority: medium).
  - Milestone 6, Sprint 2 (priority: medium).
  - Milestone 6, Sprint 3 (priority: medium).
  - Milestone 7, Sprint 1 (priority: medium).
  - Milestone 7, Sprint 2 (priority: medium).
  - Milestone 7, Sprint 3 (priority: medium).
  - Milestone 8, Sprint 1 (priority: low).
  - Milestone 8, Sprint 2 (priority: low).
- **Student-Tutor System**:
  - Milestone 1, Sprint 7 (priority: medium).
  - Milestone 1, Sprint 8 (priority: low).
  - Milestone 1, Sprint 9 (priority: low).
  - Milestone 3, Sprint 3 (priority: low).

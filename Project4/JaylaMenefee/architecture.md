
# Project 4: Software Architecture

**Name:** Jayla Menefee  
**Group:** 5  
**Project:** Study Habit Tracker  
**Sprint:** 4  
**Assigned Component:** Logging Study Sessions

## Section 1: Description of My Container

The Study Habit Tracker is designed as a cloud-based application that helps students create study goals, record study sessions, and monitor their academic progress.

For my assigned feature, Logging Study Sessions, I propose using a Docker container to run the application service responsible for recording and managing study sessions.

Docker allows the application and its required software to run in a consistent environment. The container will include the backend application, required dependencies, and the code needed to process study session requests.

The application will communicate with a shared database that stores student information, study sessions, and progress toward study goals.

### Container Contents

- Node.js runtime environment
- Express.js backend framework
- Study Session Logging application code
- Required application dependencies
- Database connection configuration
- Dockerfile for building the container

The shared database will run separately from the application container so that study records remain available even if the container is restarted or replaced.

### Proposed System Architecture

Student Web Interface
        |
        v
Cloud-Based Application
        |
        v
Docker Container
        |
        v
Study Session Logging Service
        |
        v
Shared Database

The student enters study information through the web interface. The backend validates the information and saves it to the database.

## Section 2: Component and Necessary Files

### Component: Logging Study Sessions

The Logging Study Sessions component allows students to record and review their study activities.

Students can enter the course they studied, the date, the length of the session, and optional notes.

The component saves this information so students can review their study history and track their progress.

### Main Functions

1. Allow students to enter study session information.
2. Validate the information entered by students.
3. Save study sessions in the shared database.
4. Retrieve previously recorded study sessions.
5. Display study history.
6. Provide study time information to the progress tracking component.

### Proposed Subcomponents

**Study Session Form:** Collects the course, date, duration, and notes.

**Session Validation:** Checks that required fields are completed and study duration is valid.

**Session Management:** Processes requests to create and retrieve study sessions.

**Database Access:** Communicates with the shared database.

**Study History:** Displays previously recorded sessions.

### Necessary Files

| File | Purpose |
| --- | --- |
| server.js | Starts the backend application |
| package.json | Lists application dependencies |
| Dockerfile | Defines the Docker container |
| routes/studySessions.js | Handles study session requests |
| controllers/sessionController.js | Processes study session information |
| models/studySession.js | Defines study session data operations |
| db/database.js | Manages the database connection |
| public/log-session.html | Provides the study session entry form |
| public/study-history.html | Displays saved study sessions |

These are proposed files for the architecture design. They do not all need to be implemented during this sprint.

### Communication Between Components

The Logging Study Sessions component communicates with the shared database to store and retrieve records.

It can also provide completed study time information to the Show Progress Toward Goals component.

For example, when a student records a 60-minute study session, the session is stored in the database. The progress component can use that information to update the student's progress toward a study goal.

## Section 3: Structure of the Related Database Table

### Database Design

The Study Habit Tracker will use a shared relational database.

The database will store information for the different application components, including student accounts, study goals, and study sessions.

My component will use a table named `study_sessions`.

### Table: study_sessions

| Field Name | Data Type | Description |
| --- | --- | --- |
| session_id | INTEGER | Primary key identifying each study session |
| student_id | INTEGER | Identifies the student who recorded the session |
| goal_id | INTEGER | Optional reference to a study goal |
| course_name | VARCHAR(100) | Name of the course studied |
| study_date | DATE | Date of the study session |
| duration_minutes | INTEGER | Length of the study session in minutes |
| notes | TEXT | Optional notes about the session |
| created_at | TIMESTAMP | Time the record was created |

### Database Relationships

- `session_id` is the primary key.
- `student_id` links the session to a student account.
- `goal_id` can link the session to a study goal.
- One student can have multiple study sessions.
- One study goal can be associated with multiple study sessions.

### Example Study Session Record

| session_id | student_id | goal_id | course_name | study_date | duration_minutes | notes |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 101 | 5 | Computer Science | 2026-10-22 | 60 | Reviewed Java programming |

### Data Storage and Security

Study session records will be stored in the shared database rather than inside the Docker container.

The application will validate incoming data and use database access controls to protect student information.

Students should only be able to view or modify their own study session records.

### Conclusion

The proposed Logging Study Sessions architecture provides a way for students to record study time and review their study history.

Using a Docker container supports consistent application deployment, while a shared database allows study session information to be accessed by other authorized components.

This design supports the overall purpose of the Study Habit Tracker by helping students organize their study activities and monitor progress toward their academic goals.

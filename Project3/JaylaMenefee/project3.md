# Study Habit Tracker: Project 3

## Section 1: Feature

### Logging Study Sessions

My assigned feature is logging study sessions. This feature allows students to select a course, enter the study date, and record the amount of time they studied.

From the Goal Progress screen, the student selects Log Study Session. After the student saves a valid session, the recorded time counts toward the selected course goal. Students can also view their previous study sessions.

The course, date, and study duration are required. The duration must be greater than zero. If required information is missing or invalid, the app displays a message asking the student to correct it.

## Section 2: Persona

### Maya — A Student Balancing School and Work

Maya is a fictional 22-year-old college student who works part-time. She wants to build consistent study habits, but her work schedule changes throughout the week.

Her goal is to track how much time she studies for each course. She needs a simple way to record short study sessions and see how they contribute toward her study goals.

## Section 3: Scenario

### Recording Study Time Before Work

Maya has a goal to study Software Engineering for five hours this week. Before leaving for work, she studies for 45 minutes.

She opens Study Habit Tracker and selects her Software Engineering goal. From the Goal Progress screen, she selects Log Study Session. She enters the study date and 45 minutes, then selects Save Session.

The app saves the session and adds 45 minutes to her completed study time. Maya can view the saved session and return to Goal Progress to check her updated progress.

## Section 4: User Story

As a student, I want to log my study sessions so that I can track my completed study time toward my course goals.

### Steps

1. Open Study Habit Tracker.
2. Select a course goal.
3. Select Log Study Session.
4. Enter the study date.
5. Enter the duration in minutes.
6. Select Save Session.
7. View the saved session and updated goal progress.

### Acceptance Criteria

- The student can save a session with a selected course, valid date, and duration greater than zero.
- The saved session appears in the student's study history.
- The recorded time is added to the selected goal's completed study time.
- Missing or invalid information produces a clear message and is not saved.

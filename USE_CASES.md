## Use Case

### 1. Generate System Activity Report
Primary Actor: System Administrator
Supporting Actor: Database Server
Goal: To view, export, and analyze usage and performance reports for Study Bird.
Preconditions: Administrator has authenticated with valid admin credentials. The database is accessible and up-to-date.

Main Flow:
1. Administrator navigates to “Reports → System Activity.”
2. The system queries data on active users, quizzes completed, tasks created, and system uptime.
3. Admin selects report filters (date range, user groups, activity type).
4. The system compiles and displays data in charts and tables.

### 2. Create and Review Flashcards
Primary Actor: Student
Goal: To create, edit, delete, and review digital flashcards for studying.
Preconditions: The student must be logged in.

Main Flow:
1. The student selects “Create Flashcard.”
2. Enters question, answer, subject, and optional tags/media.
3. The system validates input and assigns a unique ID.
4. Flashcard is saved to the database.
5. The student can later review flashcards.
Postconditions: Flashcard is stored and available for review or quizzes.

### 3. Manage Study Tasks and Reminders

Primary Actor: Student
Goal: To create and track study tasks and receive timely reminders.
Preconditions: Student is authenticated and has enabled notifications.

Main Flow:
1. Student adds a new task with title, deadline, and priority.
2. System schedules reminders according to user preferences.
3. When due, the system sends notifications via selected channels.
4. Task is updated in the database; reminders are adjusted accordingly.

### 4.Manage User Accounts
Primary Actor: System Administrator
Goal: Maintain user access, security, and data integrity.
Preconditions: Administrator is authenticated with admin privileges.

Main Flow:
1. Admin logs in via the admin panel.
2. Views user list and activity reports.
3. Can create, suspend, or delete user accounts.
4. The system updates the database accordingly.
5. Admin receives confirmation of each action.

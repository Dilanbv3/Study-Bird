## 1. Requirment Elicitation process 

### 1.1 Techniques Used
Two elicitation techniques were used to gather information from possible users and stakeholders:

1. Online Survey: 
To learn more about study habits, challenges and desired features Google Forms were distributed to students all over Erbil.

2. Interviews:
To gain deeper understanding one-on-one interviews with stuudents both from UKH and other universities to get deeper insights.

### 1.2 Summary of the data collected:
- Most students struggle with staying motivated and not getting distracted.
- Most frequently requested features were flashcards, weekly quizzes, study reminders and progress charts.
- 84% of students believe that they would benefit from weekly quizzes to help them retain information and they are interested in controlling how frequently they take the quizzes.
- 84% of students were interested in study reminders and to-do lists with real time alerts.
- Students are interested in tracking how long they've been studying but only 38% are interested in sharing their progress with other peers while the rest prefer to keep it private.
- Students are interested in redeeming points for gift cards and/or in app customization features.

### 2. Team brainstorming session
A brainstorming session was conducted during the early stages to refine initial ideas and each member shared their opinions on which ideas would provide the most value and how we can implement these ideas to best benefit students. 

### 3. Raw requirments list
| ID | Requirement Description | Source |
|----|--------------------------|------------------------------------------|
| R1 | Users should be able to create and review digital flashcards. | Survey |
| R2 | The system should generate daily/weekly/monthly quizzes. | Survey + Interview |
| R3 | The app should send reminders for upcoming deadlines or tasks. | Survey + Interview |
| R4 | Users should be able to manage a to-do list with time-based alerts. | Brainstorm |
| R5 | Users should earn rewards or points for completing study goals. | Interview + Brainstorm |
| R6 | The app should allow users to track how long they’ve studied and provite progress charts. | Survey |
| R7 | An optional leaderboard to encourage competition for those intereasted. | Survey + Interview |
| R8 | Gifts to reedem with collected points. | Interview |

## 2. Requirment Classification

### 1.1 Functional vs. Non-Functional Requirements

| ID | Functional Requirements |
|----|--------------------------|
| R1 | Users should be able to create and review digital flashcards. |
| R2 | The system should generate daily/weekly/monthly quizzes. |
| R3 | The app should send reminders for upcoming deadlines or tasks. |
| R4 | Users should be able to manage a to-do list with time-based alerts. |
| R5 | Users should earn rewards or points for completing study goals. |
| R6 | The app should allow users to track how long they’ve studied and provide progress charts. |
| R7 | An optional leaderboard to encourage competition for those interested. |
| R8 | Gifts to redeem with collected points. |

| ID | Non-Functional Requirements |
|----|--------------------------|
| NF1 | The app should have an intuitive and user-friendly interface free from distractions. |
| NF2 | Notifications and reminders should be delivered in real-time. |
| NF3 | The system should ensure data privacy and security for users. |
| NF4 | The app should be responsive and accessible on multiple devices. |
| NF5 | The system should handle up to 1,000 active users without performance degradation. |

### 1.2 User Requirements vs. System Requirements

| ID | User Requirements |
|----|--------------------------|
| UR1 | Users want to create, edit, and review digital flashcards easily. |
| UR2 | Users want to receive regular quizzes to reinforce their learning. |
| UR3 | Users want reminders for upcoming deadlines or study sessions. |
| UR4 | Users want a visible reward or progress system to stay motivated. |
| UR5 | Users want to compare their study time with friends for motivation and have the option to keep it private. |

| ID | System Requirements |
|----|--------------------------|
| SR1 | The system must store and retrieve flashcard data securely. |
| SR2 | The system must automatically generate quizzes based on flashcards. |
| SR3 | The system must send push notifications or email reminders. |
| SR4 | The system must track study durations and generate progress analytics. |
| SR5 | The system must update the leaderboard in real-time based on user activity. |

## 4. Structured Specifications 

### 1. Digital Flashcard Management System

| Component | Specification |
|----|--------------------------|
| Function | Create and manage digital flashcards for student purposes. |
| Description | Provides a diverse interface where users can create, edit, delete and organzie these digital flashcards. Each flashcard contains a question on the front and an answer on the back and they can be organized into subject specific deacks.Users can add additional tags and image attachments to help them more with their studies. |
| Inputs | Flashcard question front text (string, 1-500 char), answer back text (string, 1-1000 char), subject/deck category (string, from existing list or new entry), optional tags (array, max 5 tags), optional media files (images, max 5MB). |
| Source | User input via web interface forms, keyboard, moouse, file upload. |
| Outputs | Interactive flashcard presentation with reveal functionality, action confirmation alerts, updated collection statistics. |
| Destination | Web browser display. |
| Action | The system checks to see if everything is filled out correctly and comletely, additionally it adds a special number to the flashcard so no two flashcards have the same ID, also puts it in a way where only you can have access to it. Saves the flashcard permanently with data/time. If you want to change anything, the system first shows you what you already have, makes sure your edits are okay, saves the new version of your edits, and can also remember the old version. For deletion, system triggers user comfirmation before actually deleting anything, only deletes after user approval, refreshes deck totals after every change, and allows 30-second recovery period. During reviews, the system presents the question first, then with a click the answer is revealed, it also records your studying history, and lastly the system is aware of how you did in your previous quizzes and figures out the best time to quiz you on the same material again using a learning algorithm. |
| Requires | User must be authenticated and logged into the system. Database server must be active. |
| Precondition | The user needs to be logged in with a working session, and they need to have the right permission to edit these flashcards. |
| Postcondition | The flashcard is permenently saved in the database, and the users deck is continuously edited and changed up-to-date, the total number of flashcards are recalculated everytime to stay accurate, and the study progress is updated everytime anything is applicable. |
| Side Effects | The database will use more storage space to store the incoming new flashcards, the user's flashcard count goes up, the newly updated flashcards becomes part of the next generated quiz automatically. |

### 2. Automated Quiz Engine
| Component | Specification |
|----|--------------------------|
| Function | Creates automated quizzes based on your learning progress. |
| Description | Study Bird produces automated quizzes on its own at certain timestamps that the user can set according to their personal preferences. Furthermore, the system doesnt just randomly choose flashcards-its uses smart algorithms to choose the best questions for you at the moment. The systems pretty smart about which flashcards to use depending on which subject you've been struggling with and makes sure to include those, plus it mixes different topics and levels of difficulty so you dont get bored. Quizzes can be anywhere between 5-20 questions and you can take them anytime during your two day duration period. |
| Inputs | Schedule frequency (daily/weekly/monthly), number of questions per quiz(int, 5-20, default 10), subject filter(optional array of subjects, default all), difficulty preference(mixed/easy/medium/hard, optional), selects from the flashcards the user has created or studied, tracks how well the user has done in past quizzes, record when each flashcard has been last viewed. |
| Source | The system uses the users personal settings, checks and reviews the database, runs scheduled tasks, and calculates review timing using spaced repetition. |
| Outputs | The system creates quizzes with distinct ID and timestamps, the selected flashcard questions include information about the subject and level of difficulty, sets an expiration date that notifies the user via the app, email or push alerts. |
| Destination | MySQL database storage, notification service queue, user interface dashboard, email server, mobile push norification service. |
| Action | At a scheduled time, the system reviews the flashcards and chooses at least 5 suitable ones. Spaced repitition is used to review which ones are lacking, and then creates a quiz with 70% previously reviewed flashcards and 30% new ones. The questions are shuffled and balanced between subjects. A unique quiz ID is created, and the quiz is saved with a 48 hour expiartion date where it notifies you. After the user finishes the quiz, the system calculates the scores, updates their stats and gives the overall performance evaluation. |
| Requires | Minimum 5 saved flashcards, quiz settings are either modified or set to default, the program running comfortably, the database is available and active, background tasks are available to be run and support these quizzes. |
| Precondition | User has created at least 5 flashcards, the user has chosen their preferable notification settings, and the system scheduler is running without errors. |
| Postcondition | The quiz is saved and marked as ready. The user gets sent a notification and can access it through the website. If the quiz is not finished within its expiration date then you cant access it. Finished quizzes are saved for the users progress and their study stats get updated. |
| Side Effects | Study Bird gets notified through an email or push alert whenever a new quiz is enabled. The database storage increases whenever a new quiz is created. When many quizzes are created at once, the system activity expands. If the user ever skips a quiz, their stydying streak might get affected. After finishing the quiz, review timing for flashcard is updated. |

### 3. Task Management with Intelligent Reminders
| Components | Specification |
|----|--------------------------|
| Function | Study Bird keeps your study tasks organized and gives reminders automatically. |
| Description | You can creat and organize all your study tasks, assignments and deadlines in one place. Th eysstem sends the users reminders based on the user's preferences as their deadlines approach. The system allows you to prioritize tasks, group them based on their subject, and estimate how long each activity will take. Visual cues will help you see which task is most important and comes first while also shows you whats in the queue. |
| Input | Task title(5-100 char, mandatory), task description(string, 0-1000 char, optional), due time and date(datetime, mandatory, must be future), priority level(low/medium/high/critical), subject(string, optional), estimated time to complete(int minutes, optional), reminder times(array of datetime), reminder presets(1 week/3 days/1 day/1 hour before), notification channels(in-app/email/push, minimum one required). |
| Source | User inputh through a form, keyboard and mouse, with a date widget to select deadlines. |
| Outputs | The system shows your tasks in a list view, a calender view with deadlines, and detailed view for each of your tasks. You'll see which task is more important than the other and also alerts your upcoming deadlines. Reminders come through the app, email and push notifications. You'll also get completion confirmations, progress updates, and red flags for overdue tasks. |
| Destination | Web browser interface, MySQL database, notification service queue, email server, mobile device notification tray. |
| Action | The system checks to see if all the task information is rational and to make sure that all due dates are in the future. A unique ID is created for each task, reminders are set up, saves everything as "pending", and all your notifications will be scheduled. When you want to edit a task, you can chnage any of the information and your stats will immediately be updated. Additionally, if you delete a task, it ask you for a confirmation, then all your reminders will be cancelled and removed. Furthermore, when you finish up a task, it will be confirmed as done, archived, remaining reminders will be removed and your progress stats will be upgraded. Behind the scenes, a background service monitors all of the reminder. When its time for a reminder, it checks if the pending task is still active, creates the notification with task details, sends it through your preferred channels, and logs everything. The system also checks every hour for overdue tasks, sends you alerts if they're still incomplete, and updates you completion stats. |
| Requires | User authenticated with valid session. The user must also be granted notification permissions. The  systems's time service must be accurate, the background scheduler must be active, and the database connection must be stable. If the email notifactions were enabled, the email service must be configured. |
| Precondition | The user is logged in, has turned on notification on at least one channel, the system scheduler is working correctly and the system time is precise. |
| Postcondition |  The tasks you've put as reminders are all saved in the database, they're set into their right reminder times, and made sure the task shows up in your task list. The calender updates with the new deadline and your queue increments by one. |
| Side Affects | The database storage expands every time tasks and reminders are added. The email and notification list fill up with more reminders and the scheduler handles more jobs. Your productivity gets recalculated and if you pass your deadlines your completion rate may drop. The calender gets more crowded with items and each reminder uses system resources when its sent. |

## 5. Requirements Prioritization Analyst

Sorting the requirements based upon the following priorities:
### (Mandatory, Nice To Have, Superfluous) 
### 1.1 Prioritization Justification Criteria
The three priority stasuses listed above must go hand in hand with the vision set by us along with the feedback that students gave when asked through the means of interviews and surveys. The requirements that would be deemed (Mandatory) as the definition suggests would be the requirements that Study Bird would not be complete without the presence of, these requirements have been chosen in accordance to the feedback of students and careful consideration with in the team in regards to its feasability, taking into account the time needed along with deadline to implement and our ability to make them happen. Secondly, (Nice to Have) features are features that also have a majority of the students voting in favor of their implementation however said features may not have a direct effect on the core goal of Study Bird but rather they are a means of enhancing and better serving students experience in usuage. Their feasibility analysis is also do-able but without getting into the work first is not predictable if there will be any issues down the line being able to implement these features. Lastly, (Superfluous) features are said features that are not of any importance to the said goals of Study Bird or of too much relevance to students based on the surveys and interviews but could be implemented in such a way that may be optional for students to use and in regards to its feasibility it could be cut down to one or two features of this priority being implemented in Study Bird in order to not go off track or cause any issues.

### 1.2 Prioritization Table
| Requirement | Priority | Reasoning |
|------------------------------------------------------------------|-----------------|-----------------------------------------------------------------------------|
| Sending users study reminder notifications and alerts of upcoming quizzes/tests | Mandatory | As a core part of Study Bird, notifications about study reminders and alerting students of upcoming quizzes/tests should be implemented additionally based upon the surey filled by students a majority were in favor of such a feature being implemented. |
| Users should be able to create and review digital flashcards | Mandatory | To set apart Study Bird with other apps such as Moodle such features that can further be of use to students must be implemented to give yet another reason to use and utilize study bird over alternatives that lack these certain features or a combination of them, users also answered heavily in favor to this feature being apart of Study Bird. |
| System generated daily/weekly/monthly based quizzes | Mandatory | Yet another leading feature that may set apart Study Bird from alternatives while also benefitting users by helping retain studied materials through quizzes after certain time periods. | 
| Implementation of a point based reward system | Nice to Have | Being a quirky fun feature this can be deemed as quite advantageous to have in Study Bird to motivate students through a reward based system which based upon the student may get them to put more effort in to their studies. However, this cannot be deemed mandatory but rather Nice to Have with students also answering postively in regards to implementing it in Study bird based on the survey.| 
| Statistical Information such as progress reports recording amount of time studied | Nice to Have | As this requirement doesnt have a direct effect on students study quality/efficiency its not necessarily a mandatory requirement but rather nice to have and could be implemented as a optional feature that students can toggle on/off if they feel the need to use it. |
| Peer leaderboards recording and ranking highest point earners in groups of students | Superfluous | This feature was thought of to aim at students competitive minded motivation in order to better push them to achieve more. Although being a feature that is not present in most other alternatives, students survey answers a majority would rather not share their progress information with peers therefor this requirement would be superfluous. | 
| Point redeeming in exchange for rewards | Superfluous | This feature is a good and can make for a unique feature that is not present in any other alternatives in the region where a student who collects points through engagement with Study Bird such as completing quizzes, tasks etc. and can then use these points to get rewards such as apparel from the university gift shop. This feature is not on the top of the list to get implemented but would be a plus to have in Study Bird. |
 

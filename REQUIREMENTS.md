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

## 5. Requirements Prioritization Analyst

Sorting the requirements based upon the following priorities:
### (Mandatory, Nice To Have, Superfluous) 
### 1.1 Prioritization Justification Criteria
The three priority stasuses listed above must go hand in hand with the vision set by us along with the feedback that students gave when asked through the means of interviews and surveys. The requirements that would be deemed (Mandatory) as the definition suggests would be the requirements that Study Bird would not be complete without the presence of, these requirements have been chosen in accordance to the feedback of students and careful consideration with in the team in regards to its feasability, taking into account the time needed along with deadline to implement and our ability to make them happen. Secondly, (Nice to Have) features are features that also 

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



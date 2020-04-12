# System Implementation

## System Architecture
WeTell is formed by three components, which are application for users to access the system, server for handling requests and database for storing data records.

![System architecture \label{system_architecture}](source/figures/system_architecture.png){ width=100% }

### Mobile application
Flutter is an open-source and cross-platform mobile SDK created by Google. It can be used to build both iOS and Android apps from the same code base. [@flutterdev] Flutter apps are built using dart, which is an object-oriented programming language, therefore it is dynamic and extensible. Also, Flutter eliminates JavaScript bridge and is complied to native machine code, so that the performance Flutter apps . mdeIt can be used to build both iOS and Android apps from the same code base. [@flutterdev] Flutter apps are built using dart, which is an object-oriented programming language, therefore it is dynamic and extensible. 

### Server
Sails.js is the most trendy MVC framework for Node.js, which helps build custom and enterprise-grade apps. It is built on Node.js, uses Express for handling HTTP requests. [@sailsjs] Sails bundles a powerful Object-Relational-Mapper(ORM), waterline, which provides a simple data access layer to any database. [@sailsjs]

### Database
MongoDB is a document database with the scalability and flexibility, which is a non-relational database engine. MongoDB stores data in flexible, JSON-like documents, meaning fields can vary from document to document and data structure can be changed over time. [@mongodb]

## Features

### Login/ Sign up

![Authentication page (enterprise) \label{feature(E)-login_signup}](source/figures/feature(E)-login_signup.png){ width=100% }

When WeTell is started, a welcome page is shown. Users are allowed to select their roles, either an enterprise or an inspector. When a user clicks "Enterprise" button, WeTell navigates to the login page of enterprise portal. The user can input his/her registered email and password for login. If the user has not created an account yet, he/she can tap "Sign up for new account" to move to "Enterprise Signup" page. To create a new account, the email input must not be taken. Also, the password input must have more than 5 digits. When the account is created, a notification with welcoming message sends to the enterprise, when the "Thank you for signing up" page is shown. The user interface of login and signup pages in inspector portal are similar.

### View Profile 

![My profile page (enterprise) \label{feature(E)-my_profile}](source/figures/feature(E)-my_profile.png){ width=100% }

By tapping the last tab of bottom bar, a profile page is presented, which demonstrates the user information. For enterprise portal, the name, email, industry, and balance are shown. The enteprise can tap "Edit Profile" button to edit his/her information. When the submit button is tapped, the profile page with updated information is navigated.

### Notification

![Notification page (enterprise) \label{feature(E)-notification}](source/figures/feature(E)-notification.png){ width=100% }

If an enterprise or an inspector login successfully, a notificaiton page is shown, which is the homepage of both portals. User can also tap the first tab of bottom bar to enter this page. The user interfaces of two portals are similar. When the user clicks a notification on the notification list, the details of the notification is introduced. 

### Search and Reserve Task (Inspector)

![Search task page - sort by price (inspector) \label{feature(I)-search_task_sorting}](source/figures/feature(I)-search_task_sorting.png){ width=100% }

When inspectors tap on the "Search Task" tab, a list of filtered tasks is shown. If the inspector has reserved 6 or more tasks, no search results are shown. WeTell will show a message that the number of reserved tasks reached the quota, and remind the inspector to complete tasks. Also, the system matches the type of inspector and tasks' requirements. When enterprises create tasks, they can select a type of inspector. Therefore, if the inspectors do not satisfy the requirement, the task will not be sent from the server. When inspectors click the "Sort by Price" button, the list of tasks is sorted from high price to low price. In contrast, when inspectors click the "Sort by Distance" button, the list of tasks is sorted from low distance to high distance.

![Search task page - map marker (inspector) \label{feature(I)-search_task_marker}](source/figures/feature(I)-search_task_marker.png){ width=100% }

Moreover, WeTell applies Google Maps plugins to present the locations of tasks, which are located by the red markers. When an inspector clicks a marker, an information window with the task's title and address is shown over the marker. The camera position will then focus on the task's location. If the user clicks the information window, the detail of the task is shown.

![Search task page - details page (inspector) \label{feature(I)-search_task_detail}](source/figures/feature(I)-search_task_detail.png){ width=100% }

In the "Task Detail" page, not only can user get the detail information, but user can also click the "Reserve the task" button to reserve the task. If inspectors click "Back" button, WeTell navigates back to the "Search Task" page.

![Search task page - reservation (inspector) \label{feature(I)-search_task_reserve}](source/figures/feature(I)-search_task_reserve.png){ width=100% }
When an inspector clicks the "Reserve the task" button, a pop-up window is shown. If the inspector clicks the "Regret" button, WeTell navigates back to the "Task Detail" page. If the inspector clicks the "Confirm" button, the server will update the user record and task record. A completion of reservation message will be shown on the page.

![Search task page - reservation (inspector) \label{feature(I)-search_task_done}](source/figures/feature(I)-search_task_done.png){ width=100% }
Tapping the "Return to Search Page" button, WeTell routes to the "Search Page".

### Complete Task (Inspector)

![My tasks page (inspector) \label{feature(I)-my_tasks}](source/figures/feature(I)-my_tasks.png){ width=100% }

When inspecotors click "My Tasks" tab, a list of reserved tasks of the inspectors is presented. A brief information of each reserved task is described in a list view. The thrumbnail at the left side represents the industry of each task. If the inspectors click one of the list item, a page with the task information is demonstrated. Scrolling down, a "Give up Task" button is at the bottom of the page. In case the inspectors intend to cancel the task reservation, they can simply click it. Then they can click "Confirm" button in the pop up window. As a result, the task will be removed in the list of reserved tasks. WeTell returns to view list of reserved tasks. On the other hand, inspectors are allowed to start the evaluation on a task by tapping "Start Task" button.

![Start task page (inspector) \label{feature(I)-start_task}](source/figures/feature(I)-start_task.png){ width=100% }

When an inspector clicks "Start Task" button, WeTell navigates to the "Start Task" page. In the "Start task" page, the content of the card view is the reminder for inspectors before they start the task. It will be generated dynamicly depends on the task information. If the inspector clicks "Start Task" button, he/sne will move on the nezt stage. Otherwise he/she can click "Back" button to go back.

![Task question page (inspector) \label{feature(I)-start_task_question}](source/figures/feature(I)-start_task_question.png){ width=100% }

For all tasks, inspectors are asked to confirm the shop name and the address in order to avoid mistakes. If the answer is "No", WeTell returns a message showing that the task is invalid, then inspectors can click "Return" button to go back to "My Tasks" page. At the same time, a notification is sent to the corresponding enterprise to ask for the verification of the address and shop name. If the answer is "Yes", WeTell navigates to next question. 

![Task question page (inspector) \label{feature(I)-start_task_opinion}](source/figures/feature(I)-start_task_opinion.png){ width=100% }

When all evaluation questions are answered, inspectors are asked to fill the text field if they have any extra information related to the task. If they do not have any, the field should be empty. Clicking "Next" button, a review of answers is shown. Inspectors can edit their answers in the page. To submit the evaluation, inspectors tap "Submit" button. The tasks points are added into inspectors’ balance, which can be redeeemed. The user record and task record are updated.


<!-- ### Redeem Points (Inspector)

![Redeem points \label{feature(I)-redeem_points}](source/figures/feature(I)-redeem_points.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor. -->

### Create Task (Enterprise)

There are 6 steps in total for task creation.

![Create task page - step 1 address (enterprise) \label{feature(E)-create_task1}](source/figures/feature(E)-create_task_address.png){ width=100% }

![Create task page - step 1 autocomplete address (enterprise) \label{feature(E)-create_task1.1}](source/figures/feature(E)-create_task_address2.png){ width=100% }

When enterprise tap "New Task" tab on the bottom bar, the "Address" page is shown. Using Google Maps plugins, WeTell applies autocomplete function for enterprises to search their target address. When enterprise types some characters, it provides some choices for user to select. In "Address" page, if enteprises have not inputted the address yet, when they click "Submit" button, a snackbar with error message is presented. After submitting the address of tasks, enterprises can proceed to the second stage. 

![Create task page - step 2 Form (enterprise) \label{feature(E)-create_task2}](source/figures/feature(E)-create_task_form.png){ width=100% }

Enterprises are asked to fill in task information, which is task name, number of inspectors, inspector type, start date and end date, before they proceed to the third stage. The range of start date is from current date to a year after the current date. The range of end date is from the start date to a year after the current date. The end date must be at least 30 days after the start date. If there is no error, enteprises can click "Submit" button to proceed to the third stage.

![Create task page - step 3 & 4 category and plan (enterprise) \label{feature(E)-create_task3_4}](source/figures/feature(E)-create_task_plan.png){ width=100% }

There are some templates provided for enterprises, therefore WeTell does not require too much user input, which is efficient. Clicking an item in "Category" page, WeTell routes to the plan page. The corresponding plans in the category is illustrated. There are some brief descriptions for each plan, therefore enterprises will understand the plan before their selections. Click an item in "Plan" page, enterprises proceed to the fifth stage.

![Create task page - step 5 questions (enterprise) \label{feature(E)-create_task5}](source/figures/feature(E)-questions.png){ width=100% }

In "Questions" page, the sample questions of the plan are presented in card view. It contains a text view and text field for each card. The text field is filled with sample question in default, therefore enterprises can simply edit partial content to create tailor-made questions for their tasks. 

<!-- ### Comment and Rate (Enterprise)

![Commet and rate evaluation (enterprise) \label{feature(E)-comment_rate}](source/figures/feature(E)-comment_rate.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor. -->

### View Task Results (Enterprise)

![View task (enterprise) \label{feature(E)-view_task}](source/figures/feature(E)-view_task.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor.

## Impletmentation of Task filtering


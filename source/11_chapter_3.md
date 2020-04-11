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

### Login/ Sign up

![Authentication (enterprise) \label{feature(E)-login_signup}](source/figures/feature(E)-login_signup.png){ width=100% }

When WeTell is started, a welcome page is shown. Users are allowed to select their roles, either an enterprise or an inspector. When a user clicks "Enterprise" button, WeTell navigates to the login page of enterprise portal. The user can input his/her registered email and password for login. If the user has not created an account yet, he/she can tap "Sign up for new account" to move to "Enterprise Signup" page. To create a new account, the email input must not be taken. Also, the password input must have more than 5 digits. When the account is created, a notification with welcoming message sends to the enterprise, when the "Thank you for signing up" page is shown. The user interface of login and signup pages in inspector portal are similar.

### View Profile 

![My profile (enterprise) \label{feature(E)-my_profile}](source/figures/feature(E)-my_profile.png){ width=100% }

By tapping the last tab of bottom bar, a profile page is presented, which demonstrates the user information. For enterprise portal, the name, email, industry, and balance are shown. The enteprise can tap "Edit Profile" button to edit his/her information. When the submit button is tapped, the profile page with updated information is navigated.

### Notification

![Notification (enterprise) \label{feature(E)-notification}](source/figures/feature(E)-notification.png){ width=100% }

If an enterprise or an inspector login successfully, a notificaiton page is shown, which is the homepage of both portals. User can also tap the first tab of bottom bar to enter this page. The user interfaces of two portals are similar. When the user clicks on a notification on the notification list, the details of the notification is introduced. 

### Search and Reserve Task (Inspector)

![Search task - map marker (inspector) \label{feature(I)-search_task_marker}](source/figures/feature(I)-search_task_marker.png){ width=100% }

When inspectos tap on "Search Task" tab, a list of filtered tasks is shown. If the inspector has reserved 6 or more tasks, no search results are shown. WeTell will show a message that the number of reserved tasks reached the quota, and remind the inspector to complete tasks. Also, the system matches the type of inspector and task's requirement. When enterprises create tasks, they can select type of inspectors. Therefore, if the inspectors do not satisfiy the requirement, the task will not be sent from server. Moreover, WeTell applies Google Maps plugins to present the locations of tasks, which are located by the red markers. When an inspector clicks a marker, a information window with task's title and address is shown over the marker. The camera position will then be the task's location.

![Search task - sorting (inspector) \label{feature(I)-search_task_sorting}](source/figures/feature(I)-search_task_sorting.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor.

![Search task - details and reservation (inspector) \label{feature(I)-search_task_reserve}](source/figures/feature(I)-search_task_reserve.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor.

<!-- ### Complete Task (Inspector)

![Complete task \label{feature(I)-complete_task}](source/figures/feature(I)-complete_task.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor. -->

<!-- ### Redeem Points (Inspector)

![Redeem points \label{feature(I)-redeem_points}](source/figures/feature(I)-redeem_points.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor. -->

### Create Task (Enterprise)

![Create task (enterprise) \label{feature(E)-create_task}](source/figures/feature(E)-create_task.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor.

<!-- ### Comment and Rate (Enterprise)

![Commet and rate evaluation (enterprise) \label{feature(E)-comment_rate}](source/figures/feature(E)-comment_rate.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor. -->

### View Task Results (Enterprise)

![View task (enterprise) \label{feature(E)-view_task}](source/figures/feature(E)-view_task.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor.

## Impletmentation of Task filtering


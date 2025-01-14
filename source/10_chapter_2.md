# System Overview

## Overview

WeTell provides a platform between enterprises and inspectors. There are two different systems for inspectors and enterprises, since they have particular user behaviors, which will be described below. Users are allowed to register as an enterprise or an inspector. After registration as an enterprise, the enterprise can create a task. Inspectors can reserve and complete tasks, the evaluation results will then store in tasks record. After an inspector complete a task, task points will be added to his/her balance and a notification will be sent to the enterprise. The enterprise can also view the evaluation records even the whole task is not completed yet. 

## System Design

### Use Case Diagram

![Use case diagram \label{usecase}](source/figures/usecase.png){ width=100% } \

| Use Case [number 1] | Sign |
|--|----|
| Goal in Context | This use case allows user to register as an enterprise or an inspector |
| Preconditions | - Inspector has attained the age of 18 \newline - Enterprise or inspector has valid email account|
| Success End Condition | A notification is sent to user and enterprise/ inspector login page is redirected |
| Failed End Condition | Sign up failure message is shown |
| Actor | Enterprise, Inspector |
| Description | 1. User clicks "Enterprise" or "Inspector" button \newline 2. User clicks "Sign up for new account" button \newline 3. User inputs account information, e.g. email, password, name \newline4. User clicks "Submit" button|
| Extensions or Variations | The email has been taken already \newline The length of password is less than 6 charaters \newline A required field is empty |

| Use Case [number 2] | Login |
|--|----|
| Goal in Context | The use case allows user to login as an enterpirse or inspector|
| Preconditions | User has an existing account |
| Success End Condition | Enterprise or inspector homepage is redirected |
| Failed End Condition | A login failure message is shown |
| Actor | Enterprise, inspector |
| Description | 1. User clicks "Enterprise" or "Inspector" button \newline 2. User inputs email and password \newline 3. User clicks "Submit" button|
| Extensions or Variations | Inputted email does not exist in user records \newline Inputted password does not matched in user record |

| Use Case [number 3] | Logout |
|--|----|
| Goal in Context | The use case allows user to logout current account |
| Preconditions | User has already logged in |
| Success End Condition | An app start page is redirected |
| Failed End Condition | - |
| Actor | Enterprise, inspector |
| Description | 1. User clicks "My Profile" tab \newline 2. User clicks “Logout” button \newline 3. An alert message is shown \newline 4. User clicks “Confirm” button |
| Extensions or Variations | - |

| Use Case [number 4] | View and edit profile |
|--|----|
| Goal in Context | The use case allows user to view and edit his/ her information |
| Preconditions | User has already logged in |
| Success End Condition | A successful updated message is shown   |
| Failed End Condition | - |
| Actor | Enterprise/ Inspector |
| Description | 1. User clicks "My Profile" tab \newline 2. User clicks "Edit my profile" \newline 3. User inputs new information \newline 4. User clicks "Confirm" button|
| Extensions or Variations | - |

| Use Case [number 5] | Get notifications |
|--|--|
| Goal in Context | The use case allows user to get his/ her notifications |
| Preconditions | User has already logged in |
| Success End Condition | A notification page is shown |
| Failed End Condition | - |
| Actor | Enterprise/ Inspector |
| Description | 1. User clicks "Notifications" |
| Extensions or Variations | - |

| Use Case [number 6] | Search task and reserve task |
|--|----|
| Goal in Context | The use case allows user to search and reserve a task |
| Preconditions | User has logged in as an inspector \newline User has less than 6 current tasks \newline User has score of 3 in ratings \newline User type fits available task |
| Success End Condition | A reserved successful message is shown |
| Failed End Condition | No available task for user |
| Actor | Inspector|
| Description | 1. User clicks "Search Task" tab \newline 2. Users select a location \newline 3. User sorts task by type \newline 4. User clicks a task \newline 5. User clicks "Reserve" button |
| Extensions or Variations | The task is out of quota |

| Use Case [number 7] | Complete task |
|--|----|
| Goal in Context | The use case allows user to complete a task |
| Preconditions | User has logged in as an inspector \newline User has reserved at least one task \newline User's current location is in shop area \newline User can take photo by his/ her device|
| Success End Condition | A complete message is shown |
| Failed End Condition | An error message is shown |
| Actor | Inspector |
| Description | 1. User clicks "My Profile" tab \newline 2. User clicks "My tasks" button \newline 3. User clicks a task \newline 4. User clicks "Start" button \newline5. User submits answers \newline 6. User edit answers on preview section (optional) |
| Extensions or Variations | If user's current location is out of shop area for 2 minutes \newline Answers are not valid |

| Use Case [number 8] | Redeem points |
|--|----|
| Goal in Context | The use case allows user to redeem points to cash |
| Preconditions | User logged in as an inspector |
| Success End Condition | Successful message of payment to user's paypal account is shown |
| Failed End Condition | A payment failure message is shown |
| Actor | Inspector |
| Description | 1. User clicks "My Profile" tab \newline 2. User clicks "Redeem Points" button \newline 3. User selects a price \newline 4. User clicks "Confirm" button |
| Extensions or Variations | User does not have enough points to redeem the price \newline User's email and his/ her account are not matched \newline Paypal has no response |

| Use Case [number 9] | Create task |
|--|----|
| Goal in Context | The use case allows user to create a task, then the task can be searched and completed by inspectors |
| Preconditions | User has logged in as an enterprise |
| Success End Condition | A successful creation page is shown \newline "End date" of the task must be at least 29 days after "Start date" of the task|
| Failed End Condition | An error message is shown |
| Actor | Enterprise |
| Description | 1. User clicks "New Task" tab \newline 2. User inputs task information \newline 3. User clicks "Next" button \newline 4. User selects a category \newline 5. User selects a template \newline 6. User edits questions from template (optional) \newline 7. User clicks "Next" button \newline 8. User clicks "Next" button \newline 9. User clicks "Confirm" button \newline 10. User proceeds payment througth Apple Pay/ Android Pay |
| Extensions or Variations | Payment fails|

| Use Case [number 10] | Comment and Rate results |
|--|----|
| Goal in Context | The use case allows user to comment and rate the evaluation results which are inputted by  inspectors |
| Preconditions | User logged in as an enterprise \newline User's task is evaluated by at least one inspector \newline User has not commented and rated the evaluation |
| Success End Condition | A updated message is shown |
| Failed End Condition | - |
| Actor | Enterprise |
| Description | 1. User clicks "My Tasks" tab \newline 2. User clicks a task \newline 3. User clicks "Evaluation Details" button \newline 4. User clicks an evaluation record \newline 5. User clicks "Next" button \newline 6. User inputs comments and ratings \newline 7. User clicks "Submit" button |
| Extensions or Variations | - |

| Use Case [number 11] | View task results |
|--|----|
| Goal in Context | The use case allows user to view on results on his/ her task, which includes statistics, evaluation records, and average results  |
| Preconditions | User logged in as an enterprise \newline User's task is evaluated by at least one inspector |
| Success End Condition | Detail results are shown|
| Failed End Condition | - |
| Actor | Enterprise |
| Description | 1. User clicks "My Tasks" tab \newline 2. User selects a task \newline 3. User clicks "More results" button \newline 4. Users selects a question category \newline 5. User selects a question |
| Extensions or Variations | - |

### Activity Diagram

#### CreateLogin and Signup
![Login and signup \label{FUN01_LoginAndSignup}](source/figures/FUN01_LoginAndSignup.png){ width=95% } \

#### Edit Profile
![Edit profile \label{FUN02_EditProfile}](source/figures/FUN02_EditProfile.png){ width=100% } \

#### Get Notification
![Get notification \label{FUN03_GetNotification}](source/figures/FUN03_GetNotification.png){ width=100% } \

#### Reserve Task (Inspector)
![Reserve task (inspector) \label{FUN04_ReserveTask(I)}](source/figures/FUN04_ReserveTask(I).png){ width=100% } \

#### Complete Task (Inspector)
![Complete task (inspector) \label{FUN05_CompleteTask(I)}](source/figures/FUN05_CompleteTask(I).png){ width=80% } \

#### Redeem Points (Inspector)
![Redeem points (inspector) \label{FUN06_RedeemPoints(I)}](source/figures/FUN06_RedeemPoints(I).png){ width=100% } \

#### Create Tasks (Enterprise)
![Create tasks (enterprise) \label{FUN07_CreateTask(E)}](source/figures/FUN07_CreateTask(E).png){ width=90% } \

#### Comment And Rate Result (Enterprise)
![Comment and rate result (enterprise) \label{FUN08_CommentAndRateResult(E)}](source/figures/FUN08_CommentAndRateResult(E).png){ width=100% } \

#### View Tasks Result (Enterprise)
![View tasks result (enterprise) \label{FUN09_ViewTaskResults(E)}](source/figures/FUN09_ViewTaskResults(E).png){ width=100% } \

#### Logout
![Logout \label{FUN10_Logout}](source/figures/FUN10_Logout.png){ width=100% } \

### State Diagram

![State diagram \label{stateDiagram-loginState}](source/figures/stateDiagram-loginState.png){ width=100% } \

### Entity Relationship Diagram

![Entity Relationship  diagram \label{ERDiagram}](source/figures/ERDiagram.png){ width=100% } \

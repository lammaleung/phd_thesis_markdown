# System Implementation

## System Architecture
WeTell is formed by three components, which are the application for users to access the system, server for handling requests and database for storing data records.

![System architecture \label{system_architecture}](source/figures/system_architecture.png){ width=100% } \

### Mobile application
Flutter is an open-source and cross-platform mobile SDK created by Google. It can be used to build both iOS and Android apps from the same code base[1]. Flutter apps are built using dart, which is an object-oriented programming language, therefore it is dynamic and extensible. Also, Flutter eliminates JavaScript bridge and is complied to native machine code, so that the performance Flutter apps . mdeIt can be used to build both iOS and Android apps from the same code base[1]. Flutter apps are built using dart, which is an object-oriented programming language, therefore it is dynamic and extensible. 

### Server
Sails.js is the most trendy MVC framework for Node.js, which helps build custom and enterprise-grade apps. It is built on Node.js, uses Express for handling HTTP requests[2]. Sails bundles a powerful Object-Relational-Mapper(ORM), waterline, which provides a simple data access layer to any database[2]. 

### Database
MongoDB is a document database with the scalability and flexibility, which is a non-relational database engine. MongoDB stores data in flexible, JSON-like documents, meaning fields can vary from document to document and data structure can be changed over time[3].

## Features

### Login/ Sign up

![Authentication page (enterprise) \label{feature(E)-login_signup}](source/figures/feature(E)-login_signup.png){ width=100% } \

When WeTell is started, a welcome page is shown. Users are allowed to select their roles, either an enterprise or an inspector. When a user clicks the "Enterprise" button, WeTell navigates to the login page of the enterprise portal. The user can input his/her registered email and password for login. If the user has not created an account yet, he/she can tap "Sign up for new account" to move to the "Enterprise Signup" page. To create a new account, the email input must not be taken. Also, the password input must have more than 5 digits. When the account is created, a notification with a welcoming message sends to the enterprise, when the "Thank you for signing up" page is shown. The user interface of login and signup pages in the inspector portal are similar.

### View Profile 

![My profile page (enterprise) \label{feature(E)-my_profile}](source/figures/feature(E)-my_profile.png){ width=100% } \

By tapping the last tab of the bottom bar, a profile page is presented, which demonstrates the user information. For the enterprise portal, the name, email, industry, and balance are shown. The enterprise can tap the "Edit Profile" button to edit his/her information. When the submit button is tapped, the profile page with updated information is navigated.

### Notification

![Notification page (enterprise) \label{feature(E)-notification}](source/figures/feature(E)-notification.png){ width=100% } \

If an enterprise or an inspector login successfully, a notification page is shown, which is the homepage of both portals. Users can also tap the first tab of the bottom bar to enter this page. The user interfaces of the two portals are similar. When the user clicks a notification on the notification list, the details of the notification are introduced. 

### Create Task (Enterprise)

There are 6 steps in total for task creation.

![Create task page - step 1 address (enterprise) \label{feature(E)-create_task1}](source/figures/feature(E)-create_task_address.png){width=50%} ![Create task page - step 1 autocomplete address (enterprise) \label{feature(E)-create_task1.1}](source/figures/feature(E)-create_task_address2.png){width=50%}

When the enterprise tap "New Task" tab on the bottom bar, the "Address" page is shown. Using Google Maps plugins, WeTell applies to autocomplete function for enterprises to search their target address. When enterprise types some characters, it provides some choices for the user to select. In the "Address" page, if enterprises have not inputted the address yet, when they click the "Submit" button, a snack bar with an error message is presented. After submitting the address of tasks, enterprises can proceed to the second stage. 

![Create task page - step 2 Form (enterprise) \label{feature(E)-create_task2}](source/figures/feature(E)-create_task_form.png){ width=100% } \

Enterprises are asked to fill in task information, which is task name, number of inspectors, inspector type, start date, and end date before they proceed to the third stage. The range of start date is from the current date to a year after the current date. The range of end date is from the start date to a year after the current date. The end date must be at least 30 days after the start date. If there is no error, enterprises can click the "Submit" button to proceed to the third stage.

![Create task page - step 3 & 4 category and plan (enterprise) \label{feature(E)-create_task3_4}](source/figures/feature(E)-create_task_plan.png){ width=100% } \

There are some templates provided for enterprises, therefore WeTell does not require too much user input, which is efficient. Clicking an item in the "Category" page, WeTell routes to the plan page. The corresponding plans in the category are illustrated. There are some brief descriptions for each plan, therefore enterprises will understand the plan before their selections. Click an item in the "Plan" page, enterprises proceed to the fifth stage.

![Create task page - step 5 questions (enterprise) \label{feature(E)-create_task5}](source/figures/feature(E)-create_task_questions.png){ width=100% } \

In the "Questions" page, the sample questions of the plan are presented in the card view. It contains a text view and text field for each card. The text field is filled with sample questions in default, therefore enterprises can simply edit partial content to create tailor-made questions for their tasks. After creating questions, enterprises can click the "Submit" button at the bottom of the page to proceed to the sixth stage. 


![Create task page - step 6 payment (enterprise) \label{feature(E)-create_task6}](source/figures/feature(E)-create_task_payment.png){ width=100% } \

In the "Payment" page, the task details are presented for enterprises to review if the content is correct. The price of a task depends on the number of inspectors and the number of questions. The current price is the number of inspectors multiply by 20 and the number of questions multiplies by 5. Enterprises can press "Proceed payment" at the end of the page. There is two payment method which is Paypal and credit/debit card provided by Braintree. If the payment procedure is successful, a pop-up window is shown. The task creation is completed. The task can be searched and reserved by inspectors.

### Search and Reserve Task (Inspector)

![Search task page - sort by price (inspector) \label{feature(I)-search_task_sorting}](source/figures/feature(I)-search_task_sorting.png){ width=50% } \

When inspectors tap on the "Search Task" tab, a list of filtered tasks is shown. If the inspector has reserved 6 or more tasks, no search results are shown. WeTell will show a message that the number of reserved tasks reached the quota, and remind the inspector to complete tasks. Also, the system matches the type of inspector and tasks' requirements. When enterprises create tasks, they can select a type of inspector. Therefore, if the inspectors do not satisfy the requirement, the task will not be sent from the server. When inspectors click the "Sort by Price" button, the list of tasks is sorted from high price to low price. In contrast, when inspectors click the "Sort by Distance" button, the list of tasks is sorted from low distance to high distance.

![Search task page - map marker (inspector) \label{feature(I)-search_task_marker}](source/figures/feature(I)-search_task_marker.png){ width=50% } \

Moreover, WeTell applies Google Maps plugins to present the locations of tasks, which are located by the red markers. When an inspector clicks a marker, an information window with the task's title and address is shown over the marker. The camera position will then focus on the task's location. If the user clicks the information window, the detail of the task is shown.

![Search task page - details page (inspector) \label{feature(I)-search_task_detail}](source/figures/feature(I)-search_task_detail.png){ width=50% } \

In the "Task Detail" page, not only can users get detailed information, but users can also click the "Reserve the task" button to reserve the task. If inspectors click the "Back" button, WeTell navigates back to the "Search Task" page.

![Search task page - reservation (inspector) \label{feature(I)-search_task_reserve}](source/figures/feature(I)-search_task_reserve.png){ width=50% } \

When an inspector clicks the "Reserve the task" button, a pop-up window is shown. If the inspector clicks the "Regret" button, WeTell navigates back to the "Task Detail" page. If the inspector clicks the "Confirm" button, the server will update the user record and task record. Completion of the reservation message will be shown on the page.

![Search task page - reservation (inspector) \label{feature(I)-search_task_done}](source/figures/feature(I)-search_task_done.png){ width=50% } \

Tapping the "Return to Search Page" button, WeTell routes to the "Search Page".

### Complete Task (Inspector)

![My tasks page (inspector) \label{feature(I)-my_tasks}](source/figures/feature(I)-my_tasks.png){ width=100% } \

When inspectors click the "My Tasks" tab, a list of reserved tasks of the inspectors is presented. Brief information on each reserved task is described in a list view. The thumbnail on the left side represents the industry of each task. If the inspectors click one of the list items, a page with the task information is demonstrated. Scrolling down, a "Give up Task" button is at the bottom of the page. In case the inspectors intend to cancel the task reservation, they can simply click it. Then they can click the "Confirm" button in the pop-up window. As a result, the task will be removed in the list of reserved tasks. WeTell returns to view the list of reserved tasks. On the other hand, inspectors are allowed to start the evaluation on a task by tapping the "Start Task" button.

![Start task page (inspector) \label{feature(I)-start_task}](source/figures/feature(I)-start_task.png){ width=50% } \

When an inspector clicks the "Start Task" button, WeTell navigates to the "Start Task" page. In the "Start task" page, the content of the card view is the reminder for inspectors before they start the task. It will be generated dynamically depends on the task information. If the inspector clicks the "Start Task" button, he/she will move on to the next stage. Otherwise, he/she can click the "Back" button to go back.

![Task question page (inspector) \label{feature(I)-start_task_question}](source/figures/feature(I)-start_task_question.png){ width=50% } \

For all tasks, inspectors are asked to confirm the shop name and the address to avoid mistakes. If the answer is "No", WeTell returns a message showing that the task is invalid, then inspectors can click the "Return" button to go back to the "My Tasks" page. At the same time, a notification is sent to the corresponding enterprise to ask for the verification of the address and shop name. If the answer is "Yes", WeTell navigates to the next question. 

![Task question page (inspector) \label{feature(I)-start_task_opinion}](source/figures/feature(I)-start_task_opinion.png){ width=50% } \

When all evaluation questions are answered, inspectors are asked to fill the text field if they have any extra information related to the task. If they do not have any, the field should be empty. Clicking the "Next" button, a review of answers is shown. Inspectors can edit their answers on the page. To submit the evaluation, inspectors tap the "Submit" button. The task points are added into inspectors’ balance, which can be redeemed. The user record and task record are updated.

<!-- ### Redeem Points (Inspector)

![Redeem points \label{feature(I)-redeem_points}](source/figures/feature(I)-redeem_points.png){ width=100% }

Suspendisse iaculis in lacus ut dignissim. Cras dignissim dictum eleifend. Suspendisse potenti. Suspendisse et nisi suscipit, vestibulum est at, maximus sapien. Sed ut diam tortor. -->

### View Task Results (Enterprise)

![View task (enterprise) \label{feature(E)-my_tasks}](source/figures/feature(E)-my_tasks.png){ width=100% } \

When enterprises click the "My Task" button, the tasks created by enterprises are presented. The format of the list view is similar to the "My Task" page in the inspector portal. Clicking one of the tasks, the details of the tasks are shown. Sliding down to the bottom of the page, there are two buttons, which are the "Result" button and the "Evaluation Results" button. The "Result" button is not clickable if the task is not completed yet, in other words, the task has not been completed by the number of inspectors yet. When the current date is after the end date of the task, the "Result" button is clickable but the output of the result is not complete. Moreover, clicking the "Evaluation Results" button, a list of evaluation records is shown. Enterprises are allowed to click the record and view the detail of the evaluation.

![View task results (enterprise) \label{feature(E)-view_results_all}](source/figures/feature(E)-view_results_all.png){ width=100% } \

When enterprises click the "Results" button, all the handled results are shown. The results are the average of answers represented by star ratings. Scrolling down to the bottom of the page, enterprises can click "Return" and go back to the previous page.

![View task individual results (enterprise) \label{feature(E)-view_results}](source/figures/feature(E)-view_results.png){ width=100% } \

When enterprises click the "Evaluation Results" button, a list of individual evaluation results is shown, which contains the inspector number and the completed time. Clicking one of the items, the evaluation results inputted by the inspector are presented. If the enterprise has not commented and rated the result, a reminder message is shown at the top of the page. Also, the "Comment and Rate" button is at the bottom of the page as well. Otherwise, the message and the button are not presented. Tapping the "Comment and Rate" button, the enterprise can rate and comment on the result.

## Implementation of Maps Searching

In WeTell, when users search their locations, they are allowed to search by the destination. To implement this function, Google Places plugins through Flutter is used. 

``` java
Future<Null> displayPrediction(Prediction p, ScaffoldState scaffold) async {
    if (p != null) {
      // get detail (lat/lng)
      PlacesDetailsResponse detail =
          await _places.getDetailsByPlaceId(p.placeId);
      final lat = detail.result.geometry.location.lat;
      final lng = detail.result.geometry.location.lng;
      final GoogleMapController controller = await _controller.future;
      _destination = p.description;
      initPosition = CameraPosition(
        target: LatLng(lat, lng),
        zoom: 15.0,
      );
      _goToThePlace(CameraPosition(
        target: LatLng(lat, lng),
        zoom: 15.0,
      ));
    }
  }
```

Then, when users select a location, the maps view is changed.

``` java
 Future<void> _goToTheCurrentPlace() async {
    final GoogleMapController controller = await _controller.future;
    Position position = await Geolocator()
        .getCurrentPosition(desiredAccuracy: LocationAccuracy.high);
    CameraPosition _cameraPosition = CameraPosition(
      target: LatLng(position.latitude, position.longitude),
      zoom: 15.0,
    );
    controller.animateCamera(CameraUpdate.newCameraPosition(_cameraPosition));
  }

  Future<void> _goToThePlace(CameraPosition cameraPosition) async {
    final GoogleMapController controller = await _controller.future;
    BitmapDescriptor pinLocationIcon = await BitmapDescriptor.fromAssetImage(
        ImageConfiguration(devicePixelRatio: 2.5), 'assets/mark.png');
    setState(() {
      this._markers.add(Marker(
          markerId: MarkerId('temparary'),
          position: cameraPosition.target,
          icon: pinLocationIcon));
    });
    controller.animateCamera(CameraUpdate.newCameraPosition(cameraPosition));
  }
```

In order to visualize the location of the tasks when inspectors are searching for a new task, markers and info window are applied. 
``` java
void addMarkers() async {
    if (tasks != null) {
      this.isLoading = false;
      tasks.forEach((f) async {
        BitmapDescriptor onValue = await BitmapDescriptor.fromAssetImage(
            ImageConfiguration(size: Size(48, 48)), 'assets/icon.png');
        Marker marker = Marker(
          markerId: MarkerId(f.id),
          position: LatLng(f.latitude, f.longitude),
          icon: onValue,
          infoWindow: new InfoWindow(
              title: f.name,
              snippet: f.name +" "+f.address,
              onTap: () {
                BlocProvider.of<SearchTaskBloc>(context)
                    .add(SearchTaskDetailButtonPressed(task: f));
                _goToThePlace(LatLng(f.latitude, f.longitude));
              }),
        );
        setState(() {
          markers[MarkerId(f.id)] = marker;
        });
      });
    }
  }
```

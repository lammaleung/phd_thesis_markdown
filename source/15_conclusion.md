# Discussion and Conclusion 

## Difficulties and Limitations

Since Flutter is a new technology compared to other mobile application frameworks, which is released in May 2017 and the current version is 1.12.13 [1]. Therefore, it lacks third-party libraries and packages. For example, for In-App payments in Flutter, it requires third-party libraries. However, the resources are mostly not well-documented, therefore it is difficult to implement the libraries. Comparing to Flutter, it is easy to search modules for the React Native framework on Google. Flutter's official resource of free packages is getting better, however, its list of tools is still improving.

Moreover, there are some potential problems in mystery shopping. In WeTell, mystery shoppers are allowed to edit their profiles. They can select their gender, education, employment status, and age. For example, a beauty center wants to choose an 18 years old female as its mystery shopper, when WeTell currently cannot ensure the identity of the mystery shoppers, WeTell may not trustable. Therefore identity certification is needed. 

Besides, there is no verification of the correctness of evaluations currently, therefore fraudsters may gain the points by inputting irrelevant data. Verification in the system is needed. WeTell may guide enterprises to set up questions to ensure that the mystery shoppers visited their shops. Also, WeTell should also track on the mystery shopper's location when the user start a task. If the shopper is not in the shop area, the task should be terminated.

## Future Development

### Enhancement on Security Issues
Since WeTell involves the transmission of sensitive data, such as personal data, credentials, and payment information, therefore security issues are important. Encryption is necessary to communicate securely over the internet. Implementing Secure Sockets Layer (SSL) certificates is needed. SSL is a standard security technology for establishing an encrypted link between a server and a client. [4] All data transmitted across sites will have encryption deployed on the core switch level. 

### Enhancement on User Experience (UX)
The enterprise portal and inspector portal should be built in two separate apps. Also, for the "New Task" page on the enterprise portal, WeTell should allow users to custom their questions. Since the users may want to design a mystery shopper plan instead of using the template, WeTell should provide a flexible choice. Furthermore, the testing of the experience of the end-user is needed. A test plan and test cases should be applied to WeTell. Finally, the compatibility of the mobile is important. Although Flutter applies widgets to develop the user interface, the view of different devices may be different. For example, comparing iPhone X and iPhone SE, the layout of the "Task Detail" page may not fit iPhone SE, which may affect the user experience.

### Enhancement on User Interface (UI)
The user interface in both the enterprise portal and the inspector portal is similar. It is hard to differentiate two portals. Moreover, the UI design of the functions is not clear enough. When the enterprises click the "New Task" button, it should be a clear description so that the user can understand the usage of the "New Task" page. Collecting opinions on WeTell from the end-user, WeTell user interface would be enhanced in user perspectives. 
Moreover, WeTell should provide graphical statistics for data analysis, so that enterprises can have a clear view of the evaluation.

## Conclusion
WeTell provides a platform between enterprises and inspectors, so agents are no longer needed. Also, WeTell reduces manual operations. When enterprises create tasks on the platform, the inspectors can actively reserve and complete tasks. The process does not involve too many manual operations. WeTell can solve the problem of the process of a mystery shopping program, which is time, money, manpower consuming, and cost-ineffective. 
Moreover, WeTell also combined the advantages of existing applications, such as the user interface. WeTell also learned the weakness points from the existing applications, which as the process of creating an account and getting tasks. 
Nevertheless, WeTell needs enhancement on security issues, functional issues, and user interface before deployment to the market. I hope that WeTell would be well-developed in the near future.

## Architecture summary
This Spring Boot application combines MVC controllers for web pages and REST controllers for JSON APIs. Thymeleaf templates are used to render server-side pages for the Admin and Doctor dashboards, while the rest of the modules are exposes through REST APIs. The application uses two databases. MySQL for structructre data such as patients, doctors, appointments, and admins. MOngoDB for unstructured data such prescriptions. All controllers handle incoming requests and route them to the service layer, where business logic and validations are applied. The service layer also communicates repositories to retrieve and persit data using either JPA entites for MySQL or document models for MongoDB.

## Numbered flow of data and control
1. <b>User Interface Layer:</b> User interact with the application through dashboards (Admin and Doctor) or through API-based modules (Appointments, Patient Dashboard and Patient Records).
2. <b>Controller Layer:</b> Requests are routed to the appropiate controller. MVC for such as for server-redered views using Thymeleaf or REST controller for JSON data.
3. <b>Service Layer:</b> Services are called by controllers to handle business rules and validations.
4. <b>Repository Layer:</b> Services communicate with MySQL and MongoDB repositories to retrieve and persist data.
5. <b>Databases Access:</b> Repositories interact with MySQL and MongoDB databases.
6. <b>Model Binding:</b> Data is mapped using JPA Entities for MySQL and Documents for MongoDB.
7. <b>Response Delivery:</b> Models sent to controllers to be render on the user's interface or returned via JSON.
# airtribe
This project is a backend application built using Node.js and Express.js for managing courses, instructors, leads, and comments within a learning management system (LMS). The application provides a set of API endpoints to perform various operations such as adding instructors and courses, registering leads for courses, updating course details and lead statuses, searching for leads, and adding comments.

Features:
Instructor Management:

Add new instructors with their details such as name, email, and LinkedIn profile.
Course Management:

Create new courses with information like name, maximum seats, start date, and status (e.g., active, inactive).
Update course details including name, maximum seats, start date, and status.
Lead Management:

Register leads for courses by providing their name, email, phone number, LinkedIn profile, and status.
Update lead status based on their progress (e.g., applied, accepted, rejected).
Search for leads by name or email.
Comment Management:

Add comments related to leads or instructors with a timestamp.
Dockerized Deployment:

Dockerfile provided for containerization of the application and MySQL database.
Instructions included in the README for building and running the Docker container.
Technologies Used:
Node.js: JavaScript runtime for server-side development.
Express.js: Web framework for building RESTful APIs.
MySQL: Relational database management system for storing application data.
Docker: Containerization platform for packaging the application and database.
Body-parser: Middleware for parsing incoming request bodies.
This project aims to provide a scalable and efficient solution for managing courses and leads within an educational platform. It can be further extended with additional features such as user authentication, role-based access control, and analytics to enhance its functionality and usability.


# installation
git clone:- git clone https://github.com/manav-132/airtribe
install dependencies:npm install

# start
npm run devstart :-start the server using nodemon

# API Endpoints
1.GET /:
Description: Server status endpoint.
Response: "Server started".

2.POST /addinstructor:
Description: Add a new instructor to the database.
Request Body:
```
{ 
"ins_id": 1, 
"name": "John Doe",
"email": "john@example.com", 
"linked_in": "https://www.linkedin.com/in/johndoe" 
}.
```
Response:
```
{ 
"message": "Instructor created successfully"
}.
```
![WhatsApp Image 2024-03-10 at 17 33 06_9779da92](https://github.com/manav-132/airtribe/assets/103658463/3cbf28d5-8c71-45ea-8bdb-854d5db88a4f)

3.POST /addcourse:
Description: Add a new course to the database.
Request Body: 
```
{ 
"course_id": 1, 
"ins_id": 1,
"name": "Course Name",
"max_seat": 20,
"startdate": "2024-03-10",
"status": "Active"
}.
```

Response: 
```
{ 
"message": "Course created successfully" 
}.
```
![WhatsApp Image 2024-03-10 at 17 33 05_909caa55](https://github.com/manav-132/airtribe/assets/103658463/28409a7c-ee81-4bd4-9b46-138155aed62d)


4.PUT /updatecourse/:courseId:
Description: Update details of a course.
Request Body: 
```
{ "name": "New Course Name"
, "max_seat": 30,
"startdate": "2024-03-15",
"status": "Inactive"
}.
```

Response:
```
 { 
"message": "Course updated successfully" 
}.
```
![WhatsApp Image 2024-03-10 at 17 33 05_651ee755](https://github.com/manav-132/airtribe/assets/103658463/23373acd-032e-4a95-80c8-8ea41a78d6c5)


5.POST /register/:courseId:
Description: Register for a course.
Request Body: 
```
{ 
"lead_id": 1,
"name": "Lead Name",
"email": "lead@example.com",
"ph_number": "1234567890",
"linked_in": "https://www.linkedin.com/in/leadname" 
}.
```

Response:
```
{
"message": "Course Applied successfully"
}.
```
![WhatsApp Image 2024-03-10 at 17 33 22_23927438](https://github.com/manav-132/airtribe/assets/103658463/86a594f0-c4c4-48cd-b0fe-3631c1762975)

6.PUT /updateleads/:leadId:
Description: Update status of a lead.
Request Body: 
```
{ 
"status": "Accepted"
}.
```
Response: 
```
{ 
"message": "Lead updated successfully" 
}.
```
![WhatsApp Image 2024-03-10 at 17 33 23_9af028b0](https://github.com/manav-132/airtribe/assets/103658463/802545c3-b952-4a04-98ce-1b5c9dc0921b)

7.GET /searchleads:
Description: Search leads by name or email.
Query Parameters: name (string), email (string).
Response: List of leads matching the search criteria.
![WhatsApp Image 2024-03-10 at 17 33 22_f498173b](https://github.com/manav-132/airtribe/assets/103658463/1ec5597c-20f3-4b9e-9f5d-03a512827b91)

8.POST /comments:
Description: Add a comment.
Request Body:
```
{ 
"comment_id": 1,
"lead_id": 1, 
"instructor_id": 1,
"comment": "This is a comment"
}.
```
Response:
```
{ 
"message": "Comment added successfully"
}.
```
![WhatsApp Image 2024-03-10 at 17 33 23_af2ae21b](https://github.com/manav-132/airtribe/assets/103658463/62dc4ed1-eec6-499d-a6fa-5fcd36ffb67f)


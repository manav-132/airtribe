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
git clone:-git clone 



# API Endpoints
GET /:
Description: Server status endpoint.
Response: "Server started".

POST /addinstructor:
Description: Add a new instructor to the database.
Request Body: { "ins_id": 1, "name": "John Doe", "email": "john@example.com", "linked_in": "https://www.linkedin.com/in/johndoe" }.
Response: { "message": "Instructor created successfully" }.

POST /addcourse:
Description: Add a new course to the database.
Request Body: { "course_id": 1, "ins_id": 1, "name": "Course Name", "max_seat": 20, "startdate": "2024-03-10", "status": "Active" }.
Response: { "message": "Course created successfully" }.

PUT /updatecourse/:courseId:
Description: Update details of a course.
Request Body: { "name": "New Course Name", "max_seat": 30, "startdate": "2024-03-15", "status": "Inactive" }.
Response: { "message": "Course updated successfully" }.

POST /register/:courseId:
Description: Register for a course.
Request Body: { "lead_id": 1, "name": "Lead Name", "email": "lead@example.com", "ph_number": "1234567890", "linked_in": "https://www.linkedin.com/in/leadname" }.
Response: { "message": "Course Applied successfully" }.

PUT /updateleads/:leadId:
Description: Update status of a lead.
Request Body: { "status": "Accepted" }.
Response: { "message": "Lead updated successfully" }.

GET /searchleads:
Description: Search leads by name or email.
Query Parameters: name (string), email (string).
Response: List of leads matching the search criteria.

POST /comments:
Description: Add a comment.
Request Body: { "comment_id": 1, "lead_id": 1, "instructor_id": 1, "comment": "This is a comment" }.
Response: { "message": "Comment added successfully" }.

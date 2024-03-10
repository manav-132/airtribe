# airtribe

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

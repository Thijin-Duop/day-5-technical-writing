DAY 5 ASSIGNMENT – TECHNICAL WRITING
Student Name: Thijin Simon Duop
Assignment: Day 5 – Technical Writing Practical Exercises

EXERCISE A: USER MANUAL PROCEDURE
Topic: How to Create a GitHub Repository and Make Your First Commit
1. Introduction
GitHub is an online platform that allows developers to store, manage, and share their coding projects. It uses Git to track changes made to files.
This guide explains how a beginner can create a GitHub repository, add a project file, make the first commit, and upload the project to GitHub.
2. Prerequisites
Before starting, the user needs:
A computer (Windows, macOS, or Linux).
A stable internet connection.
A GitHub account.
Git installed on the computer.
A code editor such as Visual Studio Code.
Basic computer knowledge.
3. Step-by-Step Instructions
Step 1: Open a web browser.
Action: Open Google Chrome or another web browser.
Expected result: The browser opens successfully.
Step 2: Visit the GitHub website.
Action: Enter https://github.com in the browser's address bar.
Expected result: The GitHub homepage appears.
Step 3: Sign in to GitHub.
Action: Enter your GitHub username and password.
Expected result: Your GitHub dashboard appears.
Step 4: Start creating a repository.
Action: Click the New repository button.
Expected result: The repository creation page opens.
Step 5: Enter the repository name.
Action: Type my-first-project in the repository name field.
Expected result: The repository name appears in the form.
Step 6: Create the repository.
Action: Click the Create repository button.
Expected result: Your new GitHub repository is created.
Step 7: Open the computer terminal.
Action: Open Command Prompt or the VS Code terminal.
Expected result: A terminal window appears.
Step 8: Check Git installation.
Action: Type git --version and press Enter.
Expected result: The installed Git version appears.
Step 9: Create a project folder.
Action: Type mkdir my-first-project and press Enter.
Expected result: A new project folder is created.
Step 10: Enter the project folder.
Action: Type cd my-first-project and press Enter.
Expected result: The terminal enters the project folder.
Step 11: Initialize Git.
Action: Type git init and press Enter.
Expected result: Git initializes a local repository.
Step 12: Create a README file.
Action: Create a file named README.md inside the project folder.
Expected result: The README file appears in the project folder.
Step 13: Add project information.
Action: Write a short description of your project in the README file and save it.
Expected result: The README file contains the project information.
Step 14: Stage the README file.
Action: Type git add README.md and press Enter.
Expected result: Git stages the README file for the first commit.
Step 15: Make the first commit.
Action: Type git commit -m "Initial commit" and press Enter.
Expected result: Git saves the first version of the project.
Step 16: Rename the branch.
Action: Type git branch -M main and press Enter.
Expected result: The current branch is named main.
Step 17: Connect the local repository to GitHub.
Action: Type git remote add origin https://github.com/YOUR-USERNAME/my-first-project.git, replacing YOUR-USERNAME with your GitHub username.
Expected result: The local repository is connected to GitHub.
Step 18: Upload the project.
Action: Type git push -u origin main and press Enter.
Expected result: Your project files are uploaded to GitHub.
4. Screenshot Descriptions
Screenshot 1: GitHub Homepage
The screenshot should show the GitHub homepage with the Sign in and Sign up options.
Screenshot 2: Repository Creation Page
The screenshot should show the repository name field containing my-first-project and the Create repository button.
Screenshot 3: Terminal Showing the First Commit
The screenshot should show the terminal with the git commit -m "Initial commit" command and its successful result.
Screenshot 4: Completed GitHub Repository
The screenshot should show the created repository with the README.md file displayed on GitHub.
5. Troubleshooting
Common Problem: Git is not recognized as an internal or external command.
Cause:
This problem usually happens when Git is not installed or its installation directory is missing from the system PATH.
Solution:
Visit https://git-scm.com/downloads.
Download Git for your operating system.
Install Git using the recommended settings.
Close and reopen the terminal.
Run git --version again.
Expected result: The Git version should appear, showing that Git is ready to use.
6. Conclusion
Creating a GitHub repository and making the first commit are important skills for software developers. By following these instructions, beginners can create repositories, save their project changes, and upload their work online. GitHub also makes it easier to collaborate with other developers.


EXERCISE B: API REFERENCE ENTRY
Topic: Create a New Task in a Project Management Application
1. Introduction
An API (Application Programming Interface) allows two software applications to communicate with each other.
The Create Task API allows an authenticated user to create a new task inside an existing project management application.
The user provides the task title, description, assignee, due date, and priority level. The server processes the information and returns a response showing whether the task was successfully created.
2. Endpoint Information
Property
Description
API Name
Create Task API
HTTP Method
POST
Endpoint Path
/v1/projects/{projectId}/tasks
Content Type
application/json
Authentication
Bearer Token
Successful Response
201 Created

3. Request Parameters
Request parameters are the pieces of information sent to the server when creating a task.
A. Path Parameters
Parameter
Data Type
Required
Description
projectId
String (UUID)
Yes
Identifies the project where the task will be created.

B. Query Parameters
This endpoint does not require query parameters.
C. Request Body Parameters
Parameter
Data Type
Required
Description
title
String
Yes
The name of the task.
description
String
No
Additional information about the task.
assigneeId
String (UUID)
Yes
Identifies the user assigned to complete the task.
dueDate
String (Date)
Yes
The deadline for completing the task.
priority
String (Enum)
Yes
The importance of the task: low, medium, or high.

4. Required Request Headers
Headers provide additional information about the request.
Header
Required
Description
Authorization
Yes
Contains the authentication token used to identify the user.
Content-Type
Yes
Specifies that the request data is in JSON format.
Accept
No
Indicates that the client expects a JSON response.

Authentication Example:
Authorization: Bearer YOUR_ACCESS_TOKEN
5. Example API Request
The following example demonstrates how a user can send a request to create a new task.
HTTP Method: POST
Endpoint:
/v1/projects/550e8400-e29b-41d4-a716-446655440000/tasks
Request Headers:
Authorization: Bearer YOUR_ACCESS_TOKEN
Content-Type: application/json
Accept: application/json
Request Body:
{
  "title": "Complete Project Documentation",
  "description": "Prepare and review the technical documentation for the project.",
  "assigneeId": "123e4567-e89b-12d3-a456-426614174000",
  "dueDate": "2026-12-15",
  "priority": "high"
}
6. Successful API Response
When the request is valid and the task is successfully created, the server returns the HTTP status code 201 Created.
Example Response Body:
{
  "success": true,
  "message": "Task created successfully.",
  "data": {
    "id": "987e6543-e21b-12d3-a456-426614174999",
    "projectId": "550e8400-e29b-41d4-a716-446655440000",
    "title": "Complete Project Documentation",
    "description": "Prepare and review the technical documentation for the project.",
    "assigneeId": "123e4567-e89b-12d3-a456-426614174000",
    "dueDate": "2026-12-15",
    "priority": "high",
    "status": "pending",
    "createdAt": "2026-11-24T08:30:00Z"
  }
}
7. HTTP Response Codes
HTTP response codes tell the user whether the request was successful or whether an error occurred.
Status Code
Name
Explanation
201
Created
The task was successfully created.
400
Bad Request
The request contains invalid JSON or incorrect parameters.
401
Unauthorized
The user has not provided a valid authentication token.
403
Forbidden
The authenticated user does not have permission to create tasks in the project.
404
Not Found
The specified project or assignee does not exist.
409
Conflict
The request conflicts with a project restriction or another existing resource.
415
Unsupported Media Type
The request uses an unsupported content type.
422
Unprocessable Entity
The submitted information contains invalid values, such as an unsupported priority level.
429
Too Many Requests
The user has exceeded the allowed number of API requests.
500
Internal Server Error
An unexpected server problem prevented the task from being created.

8. Validation Rules
Before creating a task, the server must check that:
The title is provided and is not empty.
The description is optional.
The assignee ID belongs to an existing user.
The project ID belongs to an existing project.
The due date is provided in a valid date format.
The priority is either low, medium, or high.
The user has valid authentication.
The user has permission to create tasks in the selected project.
If any required information is missing or invalid, the server returns an appropriate error response.
9. Additional Information
The API uses JSON for communication.
Authentication is required to create a task.
The server automatically generates a unique task ID.
The default task status is pending.
The server automatically records the task creation date and time.
A task should only be created after all required validations are successful.
10. Conclusion
The Create Task API provides a simple and organized way for users to create tasks in a project management application. By understanding the endpoint, request parameters, authentication headers, response codes, and JSON examples, developers can successfully integrate the API into their applications.


EXERCISE C: TECHNICAL REPORT SECTION

PEER CRITIQUE
Peer critique is the process of reviewing another person's work and providing helpful feedback.
1. Purpose of Peer Critique
The purpose is to improve technical writing by identifying strengths, weaknesses, and areas that need improvement.
2. What I Will Check When Reviewing Another Student's Work
Clarity: Are the instructions easy to understand?
Accuracy: Is the technical information correct?
Organization: Are the sections arranged properly?
Completeness: Are all required details included?
Grammar: Are spelling and sentences correct?
3. Example of Constructive Feedback
Positive feedback:
The document is well organized and the instructions are easy to follow. The examples make the technical information easier to understand.
Areas for improvement:
Some steps could include more detailed expected results. The document could also benefit from additional screenshots to help beginners understand the process.
4. Conclusion
Peer critique helps technical writers improve their communication skills, identify mistakes, and produce better documentation. Giving and receiving feedback is an important part of professional development.


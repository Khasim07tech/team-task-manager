TEAM TASK MANAGER

Team Task Manager is a full-stack web application for managing team projects, assigning tasks, tracking task progress, and controlling access with Admin and Member roles.


LIVE PROJECT

Live URL: Add your Railway deployment URL here
GitHub Repository: https://github.com/Khasim07tech/team-task-manager


AUTHOR

Name: Pinjari Khasim
Program: B.Tech AIML Student
Institute: Sreenidhi Institute of Science and Technology


PROJECT OVERVIEW

This application helps teams organize work by creating projects, adding team members, assigning tasks, and monitoring task status from a dashboard.

It includes authentication, project-level relationships, task assignment rules, role-based access control, and a responsive futuristic user interface.


KEY FEATURES

- User signup and login
- Password hashing for secure authentication
- Token-based protected API access
- First registered user automatically becomes Admin
- Later users become Members
- Admin and Member role-based access control
- Project creation and project member management
- Task creation, assignment, status update, and deletion
- Task assignment only to project members
- Dashboard with project count, task count, completed tasks, status summary, overdue tasks, and personal open tasks
- Responsive dark futuristic UI
- Railway-ready deployment configuration


TECH STACK

Frontend:
- HTML
- CSS
- JavaScript

Backend:
- Node.js HTTP server

Database:
- File-backed JSON document storage

Authentication:
- Password hashing
- Signed tokens

Version Control:
- Git
- GitHub

Deployment:
- Railway


FOLDER STRUCTURE

team-task-manager/
  public/
    index.html
    styles.css
    app.js
  server.js
  package.json
  railway.json
  README.md
  README.txt


HOW IT WORKS

The backend in server.js serves both the REST APIs and the frontend files.

API routes start with /api/.
Normal browser requests serve files from the public/ folder.

Users authenticate through signup and login APIs. Passwords are hashed before storage. After login, the server returns a signed token. The frontend stores this token and sends it with future API requests.

Projects store an owner ID and a list of member IDs.
Tasks store a project ID and assignee ID.

The backend validates these relationships so a task can only be assigned to a user who belongs to the selected project.


ROLE-BASED ACCESS CONTROL

Admin:
- Can manage users
- Can update roles
- Can manage all projects
- Can manage all tasks

Member:
- Can access only projects where they are included as a member
- Can view and update allowed tasks

Project Owner:
- Can manage their own project

Task Assignee:
- Can update task status


MAIN API ROUTES

Auth:
- POST /api/auth/signup
- POST /api/auth/login
- GET /api/me

Users:
- GET /api/users
- PATCH /api/users/:id/role

Projects:
- GET /api/projects
- POST /api/projects
- PATCH /api/projects/:id
- DELETE /api/projects/:id

Tasks:
- GET /api/tasks
- POST /api/tasks
- PATCH /api/tasks/:id
- DELETE /api/tasks/:id

Dashboard:
- GET /api/dashboard


LOCAL SETUP

Run these commands:

npm install
npm start

Open this URL:

http://localhost:3000


RAILWAY DEPLOYMENT

1. Push the project to GitHub.
2. Open Railway.
3. Create a new project.
4. Select "Deploy from GitHub repo".
5. Choose this repository.
6. Add this environment variable:

JWT_SECRET=use-a-long-random-secret

7. Railway will automatically run:

npm start

8. Generate a Railway domain and use it as the live URL.


EXPLANATION

This project demonstrates full-stack development, REST API design, authentication, validations, relationships between data entities, role-based authorization, deployment preparation, and Git/GitHub workflow.

In a production version, the file-backed JSON storage can be replaced with PostgreSQL or MongoDB on Railway while keeping the same API structure.
